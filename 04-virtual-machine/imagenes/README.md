# Laboratorio 04
En este laboratorio quiero empezar a trabajar con infraestructura dentro de Azure creando alguna maquina virtual.

## Objetivos
1. Creación de un Virtual Machine
2. Configuración de una red virtual
3. Acceso mediante SSh
4. Administracion de VM mediante Azure CLI
5. Instalacion de un servicio web

## Conceptos
Como en los labpratorios anteriores, quiero poner en esta secion los terminos que vamos a utilizar durante el laboratorio, para en caso de ser necesario consulta la informacion.<br>
1. **Virtua Machine** = Dispositivo virtualizado
2. **Image (Imagen)** = Indica u sistema operativo
3. **VM Sieze** = Recursos asignados

## Arquitectura
```
                Azure
                  |
              Suscripcion
                  |
            RG_Lab04_LinuxVM
                  |
    ┌─────────────┴────────────────┐
    |                              |
    VM                      Virtual Network
    |                              |
Ubuntu Linux                     Subnet
    |                              |
Apache/Nginx             Network Security Group
                                   |
                          SSH :22  |
                         HTTP :80  | 
                                   |
                                Public IP
                                   |
                                Internet

```
<br>

**IMPORTANTE:** Como este laboratorio puede crear costes, para evitarlo voy a crear maquinas virtuales de pequenio tamanio, no agregar discos innecesarios, no usar servicios como Bastion y eliminar todo lo creado al terminar.<br>

## Configuracion
Para el entorno de este laboratorio crearemos el Resource Group `RG_Lab04_LinuxVM` con region en `spaincentral` y las etiquetas: `Project : Azure_labs` y `Lab : 04-LinuxVM`.

## Procedimiento
### 1.- Crear una VM
