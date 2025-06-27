# Building a CI/CD Pipeline with GitHub Actions

Welcome! This repository is a hands-on guide to building a modern CI/CD pipeline using GitHub Actions. We'll be building a simple application with a **FastAPI** backend and a **React** frontend, and then creating a series of workflows to automate our development process.

## The Application

Our application is a standard monorepo with two main components:

-   `backend/`: A Python web service built with FastAPI.
-   `frontend/`: A JavaScript single-page application built with React.

This setup is representative of many modern web applications and provides a good basis for demonstrating a real-world CI/CD pipeline.

## The Goal

We will create three distinct GitHub Actions workflows:

1.  **Pre-merge (`premerge.yaml`):** This workflow will run on every push to a non-main branch. It will lint, test, and build our applications to ensure that new code meets our quality standards before it gets merged.
2.  **Post-merge (`postmerge.yaml`):** This workflow will run on every push to the `main` branch. It will do everything the pre-merge workflow does, but will also include a `publish` step to create a releasable artifact.
3.  **Publish (`publish.yaml`):** This is a reusable workflow that can be called by other workflows. Its job is to take the build artifacts and "publish" them. In a real-world scenario, this could mean deploying to a server, uploading to a registry, or creating a GitHub release.

Let's get started!
