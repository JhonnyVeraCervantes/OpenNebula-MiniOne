# OpenNebula-MiniOne

** miniONE ** es una herramienta de implementación fácil de usar para crear una nube OpenNebula de evaluación basada en máquinas virtuales (KVM), contenedores del sistema (LXD), micro VM (Firecracker) o implementación de Edge en Packet. Todos los componentes necesarios para administrar y ejecutar las máquinas virtuales o contenedores se instalan y configuran en su sistema dedicado con solo ejecutar un comando.** miniONE ** es una herramienta de implementación fácil de usar para crear una nube OpenNebula de evaluación basada en máquinas virtuales (KVM), contenedores del sistema (LXD), micro VM (Firecracker) o implementación de Edge en Packet. Todos los componentes necesarios para administrar y ejecutar las máquinas virtuales o contenedores se instalan y configuran en su sistema dedicado con solo ejecutar un comando.

**Follow the detailed [tutorial](https://docs.opennebula.io/minione/)**.

## Requirements

Requisitos mínimos comunes:
- 4 GiB RAM
- 20 GiB free space on disk
- instalación predeterminada del sistema operativo con las últimas actualizaciones
- acceso de usuario privilegiado (`root`)
- paquete openssh-server instalado

Para ** evaluación de KVM ** en un servidor físico dedicado tanto para el front-end como para un nodo de hipervisor KVM:
- anfitrión físico
- Procesador Intel o AMD x86-64 con ** virt. capacidades **
- sistema operativo:
  - CentOS 7 (RHEL 7) or CentOS 8 (RHEL 8)
  - Debian 9, 10
  - Ubuntu 16.04, 18.04, 20.04

Para ** evaluación LXD ** en un servidor físico dedicado o máquina virtual tanto para el front-end como para un nodo de hipervisor LXD:
- physical host or virtual machine (e.g., Amazon EC2 VM)
- x86-64 Intel or AMD processor
- operating system:
  - Ubuntu 18.04, 20.04

Para ** evaluación de Firecracker ** en un servidor físico dedicado o máquina virtual para el front-end y un nodo de hipervisor de Firecracker:
- physical host or virtual machine (e.g., Amazon EC2 VM)
- x86-64 Intel or AMD processor
- operating system:
  - CentOS 7 (RHEL 7) or CentOS 8 (RHEL 8)
  - Debian 9, 10
  - Ubuntu 16.04, 18.04, 20.04

Para ** evaluación de borde ** en un servidor físico dedicado o máquina virtual para el front-end y un servidor físico de borde de paquete remoto para un nodo de hipervisor ** KVM o Firecracker **:

- physical host or virtual machine (e.g., Amazon EC2 VM)
- x86-64 Intel or AMD processor
- operating system:
  - CentOS 7 (RHEL 7) or CentOS 8 (RHEL 8)
  - Debian 9, 10
  - Ubuntu 16.04, 18.04, 20.04

## Quickstart

Download the [latest release](https://github.com/OpenNebula/minione/releases/latest) of the **miniONE** tool, run it and follow the instructions on the terminal.

### Get KVM cloud

Ejecute los comandos para implementar la nube de evaluación:

```
wget 'https://github.com/OpenNebula/minione/releases/latest/download/minione'
sudo bash minione
```

### Get LXD cloud

Ejecute los comandos para implementar la nube de evaluación:

```
wget 'https://github.com/OpenNebula/minione/releases/latest/download/minione'
sudo bash minione --lxd
```
### Get Firecracker cloud

Ejecute los comandos para implementar la nube de evaluación:

```
wget 'https://github.com/OpenNebula/minione/releases/latest/download/minione'
sudo bash minione --firecracker
```

### Get Edge cloud on Packet

miniONE instalará la interfaz de OpenNebula en el host donde ejecuta el comando y también implementará y configurará un host de hipervisor en Edge ([Packet] (https://www.packet.com/) en este caso) donde puede generar sus VM .

Ejecute los comandos para implementar la nube de evaluación:

```
wget 'https://github.com/OpenNebula/minione/releases/latest/download/minione'
sudo bash minione --edge packet --edge-packet-token [packet-token] --edge-packet-project [packet-project]
```

Opcionalmente, puede usar elegir implementar en el hipervisor ** Firecracker ** en Edge.

```
wget 'https://github.com/OpenNebula/minione/releases/latest/download/minione'
sudo bash minione --firecracker --edge packet --edge-packet-token [packet-token] --edge-packet-project [packet-project]
```

## License

Copyright 2002-2020, OpenNebula Project, OpenNebula Systems (formerly C12G Labs)

Licensed under the Apache License, Version 2.0 (the "License"); you may
not use this file except in compliance with the License. You may obtain
a copy of the License at http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
