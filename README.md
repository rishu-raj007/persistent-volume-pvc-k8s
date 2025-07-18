# 🚀 Kubernetes Pod with Azure Files (PV & PVC)

This repository contains Kubernetes manifests to deploy a Pod that uses an Azure File Share as a volume. It leverages Azure Kubernetes Service (AKS) and Azure Container Registry (ACR) to securely mount persistent storage and run a containerized application.

---

## 📁 Repository Structure


---

## 🛠 Prerequisites

Make sure the following resources are ready before deploying:

- ✅ Azure Kubernetes Service (AKS) cluster
- ✅ Azure File Share (`pvc-docker`) in a Storage Account (`pvc-storage`)
- ✅ Azure Container Registry (ACR) with image:  
  `acrrishupractce.azurecr.io/elearn_frontend:v1`
- ✅ Azure CLI and kubectl configured locally

---

## 🔐 Step 1: Create Secret for Azure File Share Access

The `Secret` stores your Azure Storage Account credentials securely:

```yaml
apiVersion: v1
kind: Secret
metadata:
  name: pvc-secret
type: Opaque
stringData:
  azurestorageaccountname: pvc-storage
  azurestorageaccountkey: <your-storage-account-key>
