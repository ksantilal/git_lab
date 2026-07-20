# Git Branching and Release Workflow

This repository follows a simple and structured Git branching model for development, releases, and hotfixes.

## Branch Structure

- main
  - Production-ready code
  - Only stable releases are merged here

- release/july26
  - Release branch for July 2026 work

- dev/july26
  - Integration branch for July 2026 development

- release/aug26
  - Release branch for August 2026 work

- dev/aug26
  - Integration branch for August 2026 development

- feature/devops-123
- feature/devops-456
- feature/devops-789
- feature/devops987
- hotfix/devops-654
- hotfix/devops-313

## Sprint 1 Workflow

### Create feature branches from dev/july26

- feature/devops-123
  - Develop Terraform module
- feature/devops-456
  - Develop Ansible module

### Merge flow

1. Merge feature branches into dev/july26
2. Merge dev/july26 into release/july26
3. Merge release/july26 into main
4. Delete or clean up feature branches

## Sprint 2 Workflow

### Create feature branches from dev/aug26

- feature/devops-789
  - Create EKS module in Terraform
- feature/devops987
  - Create Python playbook in Ansible

### Merge flow

1. Merge feature branches into dev/aug26
2. Merge dev/aug26 into release/aug26
3. Merge release/aug26 into main
4. Delete or clean up feature branches

## Hotfix Workflow

### Create hotfix branches from main

- hotfix/devops-654
  - Update EKS module
- hotfix/devops-313
  - Update Python playbook

### Merge flow

1. Merge hotfix branches into main
2. Delete the hotfix branches after merging

## Recommended Git Commands

```bash
git checkout main
git pull origin main

git checkout -b feature/devops-123 dev/july26
git checkout -b feature/devops-456 dev/july26

git checkout -b feature/devops-789 dev/aug26
git checkout -b feature/devops987 dev/aug26

git checkout -b hotfix/devops-654 main
```

## Notes

- Always create feature branches from the correct development branch.
- Merge feature branches into the relevant dev branch first.
- Only merge tested and approved code into release and main branches.
- Delete branches after successful merge to keep the repository clean.
