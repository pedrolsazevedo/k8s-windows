# Simple walkthrough to install Minikube using Hyper-V


# Hyper-V

## 1. Check Hyper-V

```powershell
## Check if the computer has Hyper-V support
systeminfo

## This will appear if Hyper-V is supported
Hyper-V Requirements:     VM Monitor Mode Extensions: Yes  
                          Virtualization Enabled In Firmware: Yes  
                          Second Level Address Translation: Yes  
                          Data Execution Prevention Available: Yes
```

## 2. Enable Hyper-V
```powershell
Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Hyper-V -All
```
# Chocolatey


```powershell
Set-ExecutionPolicy Bypass -Scope Process -Force; iwr https://chocolatey.org/install.ps1 -UseBasicParsing | iex
```

# Minukube
## 1. Installing Minikube

```powershell
choco install minikube
```

## 2.  Configuring Hyper-V as driver for minikube

```powershell
## If you want to run with hyper-v as driver 
minikube start --driver=hyperv

## if you want to set hyper-v as default driver
minikube config set driver hyperv

## Starting minikube
minikube start
```

## 3. Minikube Dashboard (optional)

MInikube dashboard is an amazing tool that allows you to use an graphical interface in kubernetes administration.

```powershell
kubectl apply -f https://raw.githubusercontent.com/kubernetes/dashboard/v2.0.0/aio/deploy/recommended.yaml

kubectl proxy

minikube dashboard
```