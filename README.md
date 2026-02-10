# Sistema-de-Historias-Clinicas-Distrubuidas
Es un proyecto universitario que propone un sistema de historias clínicas distribuidas, donde la información de los pacientes puede ser consultada de forma segura desde diferentes lugares. Su objetivo es mejorar la organización de los datos médicos y apoyar una atención más rápida y ordenada.

Nota: Todos los comandos fueron testeados en Debian GNU/Linux 13 (trixie). Se recomienda utilizar esta versión o una compatible.

# Instalación del proyecto.
### 1. Actualizar el sistema.
```
sudo apt update && sudo apt upgrade-y
```
### 2. Instalar utilidades y herramientas de desarrollo.
```
sudo apt install -y curl wget git vim htop unzip ca-certificates python3 python3-pip python3-venv libcairo2 libpango-1.0-0 libgdk-pixbuf-2.0-0 libffi-dev shared-mime-info libjpeg-dev libxml2 libxslt1.1
```
### 3. Crear directorio seguro para claves GPG.}
```
sudo install -m 0755 -d /etc/apt/keyrings
```
### 4. Importar clave GPG de Docker.
```
curl -fsSL https://download.docker.com/linux/debian/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
```
### 5. Agregar repositorio oficial de Docker e instalar.
```
echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/debian $(. /etc/os-release && echo $VERSION_CODENAME) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt update
sudo apt install -y docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
sudo systemctl enable --now docker
sudo usermod -aG docker $USER
newgrp docker
```
