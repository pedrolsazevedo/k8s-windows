# Guia simples de instalação do Kubernetes (k8s) com Hyper-V



# Hyper-V

## 1. Verificar Hyper-V

```powershell
## Verificar se o computador suporta Hyper-V
systeminfo

## Verificar se o computador suporta o hyper-v
Hyper-V Requirements:     VM Monitor Mode Extensions: Yes  
                          Virtualization Enabled In Firmware: Yes  
                          Second Level Address Translation: Yes  
                          Data Execution Prevention Available: Yes
```

## 2. Ativar o Hyper-V
```powershell
Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Hyper-V -All
```
# Chocolatey


```powershell
Set-ExecutionPolicy Bypass -Scope Process -Force; iwr https://chocolatey.org/install.ps1 -UseBasicParsing | iex
```

# Minukube
## 1. Instalando Minikube

```powershell
choco install minikube
```

## 2.  Configurando para usar o driver do hyper-v

```powershell
## Configurar apenas para o inicio  
minikube start --driver=hyperv

## Configurar como driver padrão  
minikube config set driver hyperv

## Iniciando minikube
minikube start
```

## 3. Minikube Dashboard

```powershell
kubectl apply -f https://raw.githubusercontent.com/kubernetes/dashboard/v2.0.0/aio/deploy/recommended.yaml

kubectl proxy

minikube dashboard
```