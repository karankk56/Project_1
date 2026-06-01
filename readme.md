# CI/CD Automation Pipeline using Jenkins, Docker, Ansible and Kubernetes

## Overview

This project demonstrates an end-to-end CI/CD automation workflow for deploying a containerized web application.

The pipeline automatically detects code changes from GitHub using Jenkins Poll SCM, builds a Docker image, 
pushes the image to Docker Hub and deploys the latest version to Kubernetes using Ansible.

---

## Architecture

Developer
→ GitHub
→ Jenkins (Poll SCM)
→ Docker Build
→ Docker Hub
→ Ansible
→ Kubernetes (Minikube)
→ Running Application

---

## Technologies Used

* Linux
* Git & GitHub
* Jenkins
* Docker
* Docker Hub
* Ansible
* Kubernetes
* Minikube
* Nginx

---

## Project Workflow

1. Developer pushes code to GitHub.
2. Jenkins Poll SCM detects repository changes.
3. Jenkins triggers CI/CD pipeline.
4. Docker image is built automatically.
5. Image is pushed to Docker Hub.
6. Ansible Playbook executes deployment tasks.
7. Kubernetes updates application deployment.
8. Latest application version becomes available.

---

## Features

* Automated CI/CD Pipeline
* Dockerized Application
* Kubernetes Deployment
* Ansible Automation
* Poll SCM Integration
* Docker Hub Integration
* Rolling Deployment Updates

--

# Architecture Diagram

┌──────────────┐
│  Developer   │
└──────┬───────┘
       │ Git Push
       ▼
┌──────────────┐
│   GitHub     │
└──────┬───────┘
       │ Poll SCM
       ▼
┌──────────────┐
│   Jenkins    │
└──────┬───────┘
       │
       ▼
┌──────────────┐
│ Docker Build │
└──────┬───────┘
       │
       ▼
┌──────────────┐
│ Docker Hub   │
└──────┬───────┘
       │
       ▼
┌──────────────┐
│   Ansible    │
└──────┬───────┘
       │
       ▼
┌──────────────┐
│ Kubernetes   │
└──────┬───────┘
       │
       ▼
┌──────────────┐
│ Application  │
└──────────────┘
