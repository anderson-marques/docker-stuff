# 1. Introduction

## 1.1. Continuous Delivery Overview

### Why Continous Delivery
- Release Often (Fast)
- Release Small (Focused)

### Enables MVP (Minimum Viable Product) Approach

- Test ideas in real world
- Build better smarter products

### Reduces Risk
- Smaller Changes = Less Risk
- Continuous Deploy
    - To at least one environment
    - Always deploying means you get much better at deployments
- Small scope of change
    - Easier to deploy
    - Easier to rollback if necessary
    - Easier to fix

### Real Progress
- Each change is real progress
    - You know it is done because you deployed it successfully
- Build Confidence
    - In ability to release new features
    - In ability to detect and fix issues

## 1.2. Continuous Delivery Workflow

- **Dev**
    - Design
    - Code
    - Test
- Continuous Delivery
    - Test
        - Unit and Integration Testing
        - Use Docker to wrap test runners
        - Benefits of Using Docker
            - Predefined environment
            - Portable
            - Consistent
            - Repeatable
    - Build
        - Build Application Artifacts
        - Must represent as tested application state
        - Creates a Deployable Artifact
            - Installation requires no development dependencies
    - Release
        - Build Docker Release Images
            - Includes minimal runtime environment
            - Installs application artifacts
        - Release Environment
            - A production-like environment
            - Use an external test runner to run acceptance tests
        - Tag and Publish
            - Only if acceptances tests pass
            - Docker Registry
    - Deploy
        - Deploy release image to:
            - At least one environment
            - Perhaps even production
        - Fully automated deployments
            - Using orchestration tools such as Ansible
            - Levarages Infrastructure automation tools such as AWS CloudFormation and Terraform
- **Ops**
    - Measurement
    - Monitoring

## 1.3. How to achieve Continuous Delivery?

### Methodology
- Application Agnostic
- Portability
- Separation of Concerns
- Immutable Infrastructure
- Infrastructure as Code

### Automation
- Saves time and money
- Repeatable and consistent results
- Automate as much as possible
    - Tests 
    - Creating environments
    - Deployments
    - Monitoring
    - etc..

### Testing
- Quantitative Measurement
- Production Readiness
- Automation and Consistency

### Cultural Factor
- DevOps are made of **people**

## 1.4. Why Docker?

- Speed
- Portability
- Automation

#
## [Goback](./index.md)