pipeline  {

  agent any 

  environment {
      IMAGE_NAME = "karanprajapati/dev-pro:v1"
       }
  
  stages {
     stage('Clone Code') {
      
       steps {
           git 'https://github.com/karankk56/Project_1.git'
           }
         }
    
     stage('Build Docker Image') {
       steps {
         sh 'docker build -t $IMAGE_NAME:$BUILD_NUMBER .'
          }
      }
    
     stage('Push Docker Image') {
       steps {
         
            withCredentials([usernamePassword(
                credentialsId: 'dockerhub',
                usernameVariable: 'DOCKER_USER',
                passwordVariable: 'DOCKER_PASS'
                )]) {
            
            sh 'echo $DOCKER_PASS | docker login -u $DOCKER_USER  --password-stdin'
            
            sh 'docker push $IMAGE_NAME:$BUILD_NUMBER'

       }
     }
   }
        
      stage('Update Kubernetes Deployment') {
       
         steps{ 
             sh '''
               sed -i "s|image:.*|image: $IMAGE_NAME:$BUILD_NUMBER|g" k8s/deployment.yaml
               '''

             }
          }

      stage('Deploy using Ansible'){
         steps{ 

           sh '''
           ansible-playbook -i ansible/inventory.ini ansible/deploy.yaml
           '''

         }
        }
       }
      }


