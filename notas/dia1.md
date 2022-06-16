# DEVOPS?

Cultura/Moviento en pro de la AUTOMATIZACION. 
Qué quiero automatizar ? Todo lo que pueda desde el DEV hasta la OPS.

Por qué quiero automatizar?
- Ahorro de tiempo
- Sistematización
- Mayor calidad
- Ahorro de costes
- Mayor satisfacción clientes
- Disaster/recovery
- Calidad procesos

Que problemas trae consigo la automatización?
- Quién sabe de esto? 
- Hay que saber de mochas cosas nuevas
- Las organizaciones tardan años en adoptar una cultura devops

---

# Desarrollo de software / Metodologías de desarrollo de software

## Metodologías en Cascada:

Fases secuenciales:
- Toma de requisitos
- Análisis
- Programación - project: Diagramas de gantt
- Desarrollo
        
        xxxxxx                                                xxxxxxxx
        xxxxxx                 Aguajero negro temporal     xxxxxxxxxxxx
        xxxxxxx                                            xxxxxxxxxxxx
         50%xxxxxxx.      x.     x.     x.    x            XXXXXXXXXXXX
        Fecha inicio                                        Fecha fin

    HITO = Fecha en la que entrego unas funcionalidades
           ----->                       ---------------


- Pruebas
- Documentación
- Instalación / Implantación

¿Qué problemas teníamos?
- Adaptación al cambio
- Entendimiento de los requisitos
- Calidad


## Manifiesto agil -> SCRUM, Xtreme Programming

### Metodologías ágiles

Entrega del software de forma incremental: Cada 15 días - 2 meses
Entrega 1 (10 dias de comenzar el proyecto): 100% funcional - 10% de la funcionalidad
Entrega 2 (10 dias de comenzar el proyecto): 100% funcional - 15% de la funcionalidad
Entrega 3 (10 dias de comenzar el proyecto): 100% funcional - 25% de la funcionalidad
...
Entrega N (10 dias de comenzar el proyecto): 100% funcional - 100% de la funcionalidad

Iteraciones -> Sprints(Scrum)

Sprint = Fecha en la que entrego unas funcionalidades
         -----                        >-------------<
         
20 instalaciones en producción > 20 instalaciones en preproducción          --   AUTOMATIZAR
                    PRUEBAS !!! > 20 veces las pruebas ? NOOO MUCHO PEOR    /
---

Planificación
    Requisitos(lenguaje humano) -> Esqueleto del Codigo y pruebas          GUERKIN + CUCUMBER
Desarrollo
    Queries SQL -> Hibernate
Compilación/Empaquetado
    Backend Spring (JAVA) .java .xml -> .war .ear                           MAVEN, Gradle, sbt < Desarrollador
    .net Microsoft                                                          MSBUILD
    Frontend: js                                                            webpack, npm, 
  ------------------------------------------------------------------------------->            Desarrollo ágil
Pruebas
    Diseño
    Ejecución       Automatizar
                                                                            JUNIT
                                                                            SELENIUM
                                                                            APPIUM
                                                                            LOADRUNNER
                                                                            SOAPUI
                                                                            POSTMAN
                                                                            JMETER
        Tipos de pruebas:                                                                    
            Estáticas - NO es necesario poner el producto en funcionamiento
                Desarrollador Senior - Calidad de Código                    SONARQUBE
            Dinámicas - SI es necesario poner el producto en funcionamiento
                Funcionales
                    Unitarias
                    Integración
                    Sistema
                    Aceptación
                No funcionales
                    UI
                    UX
                    Rendimiento
                    Carga
                    Estress
                    HA
                    Escalabildiad
        Donde instalo el software para probarlo?
            Pruebas, Pre-producción, Integración
                Y ese entorno existe? Alguien lo ha creado
                    - Costó mucho?
                    - Tuve que esperar mucho?
                    - Se me malea el entorno entre pruebas?
                    - Cuanto cuesta mantenerlo?
        Puedo automatizar la creación de un entorno / Infra
            Computadoras nuevas conectadas a una red     <     Clouds (alquiler)
                Automatiza la adquisición y provisionamiento de infra
                    Cada cloud tiene su herramienta-cliente que permite hacer automatizaciones
                                                                            TERRAFORM
                                                                            VAGRANT
                                                                            ANSIBLE, PUPPET, CHEF
            Mi entorno de integración sea un entorno de usar y tirar
    --------------------------------------------------------------------------->    Integración Continua
                                                                                        Continuous Integration - CI
    
Entrega del producto: Puesta en mano de mi software
        Nexus
        Artifactory
    --------------------------------------------------------------------------->    Entrega Continua:         \
                                                                                        Continuous Delivery.   \
Despliegue/Instalación.                                                                                         CD
    --------------------------------------------------------------------------->    Despliege Continua:        /
                                                                                        Continuous Deployment /
Monitorización/Operación
        KUBERNETES/OPENSHIFT
---

        Automatizar el manejo de cualquier código
        Complemento al métodologías ágiles                                                  √
        Relacionado con Integración Continua / Entrega Continua / Despliegue Continuo       √
        Automatizar los procesos de desarrollo, prueba, integración y puesta en producción  √
        Cloud?                                                                              √
        Openshift, Kubernetes. -> Contenedorización < Docker                                √
---

Modelos de crecimiento de una app:

App1: App departamental/empresariales
    Dia 1:      100 usuarios
    Dia 100:     98 usuarios
    Dia 1000:   103 usuarios

App2: 
    Dia 1:      100 usuarios
    Dia 100:    1000 usuarios         Tengo que ir actualizando la infra
    Dia 1000:   10000 usuarios
    
App3: INTERNET
    Dia n:      100 usuarios
    Dia n+1:    100000 usuarios       Tengo que ir actualizando la infra
    Dia n+2:    10 usuarios
    Dia n+3:    1000000 usuarios
    
---

Qué es un Cloud:

Conjunto de los servicios IT que ofrece una empresa a través de internet (de forma automatizada) 

---

Qué es un contenedor? o en qué consiste este mundo de la contenedorización?


---

Distribución / Instalaciones /Ejecución de apps

## Modelo tradicional

      App1   +  App2   +   App3           Problemas: - Incompatibilidad del software con el SO
    -----------------------------                    - Incompatibilidad entre dependencias de distintas apps
          Sistema Operativo                          - Incompatibilidad entre configuraciones a nivel de SO
    -----------------------------                    - Qué pasa si App1 se vuelve loca (bug) y toma el 100% CPU
                HIERRO                                      APP1 OUT.... APP2 y APP3 si no hay CPU OUT
                                                     - Seguridad. APP1 podría acceder alos ficheros de APP2
                                                     
## Virtualización + Máquinas virtuales

      App1 |   App2   +   App3            Resuelto:  - Incompatibilidad del software con el SO
    -----------------------------                    - Incompatibilidad entre dependencias de distintas apps
      SO1  |        SO2                              - Incompatibilidad entre configuraciones a nivel de SO
    -----------------------------                    - Qué pasa si App1 se vuelve loca (bug) y toma el 100% CPU
      MV1  |        MV2                                      APP1 OUT.... APP2 y APP3 si no hay CPU OUT
    -----------------------------                    - Seguridad. APP1 podría acceder alos ficheros de APP2
     HIPERVISOR: VMWARE, HYPERV
       KVM, VirtualBOX, Citrix            Problemas: - Estabilidad:  Más puntos potenciales de fallo
    -----------------------------                    - Muchos SO: Más complejidad: Instalaciones, configuraciones
                SO                                            mantenimiento
    -----------------------------                    - Peor rendimiento 
              HIERRO                                 - Merma en los recursos

## Contenedores

                                          Resuelto:  X Incompatibilidad del software con el SO
    -----------------------------                    √ Incompatibilidad entre dependencias de distintas apps
      APP1  |   App2   +   App3                      √ Incompatibilidad entre configuraciones a nivel de SO
    -----------------------------                    √ Qué pasa si App1 se vuelve loca (bug) y toma el 100% CPU
      C1   |        C2                                      APP1 OUT.... APP2 y APP3 si no hay CPU OUT
    -----------------------------                    √ Seguridad. APP1 podría acceder a los ficheros de APP2
     Gestor de contenedores:
      Docker, Podman, CRIO, Container.d   Problemas: X Estabilidad:  Más puntos potenciales de fallo
    -----------------------------                    X Muchos SO: Más complejidad: Instalaciones, configuraciones
             SO Linux                                             mantenimiento
    -----------------------------                    X Peor rendimiento 
              HIERRO                                 X Merma en los recursos              

## Kernel de Sistema Operativo más usado en el mundo? Linux

## Sistema Operativo más usado en el mundo? Android


## Qué es un contenedor?

Un entorno aislado dentro de un SO Linux donde ejecutar procesos. Aislado en cuanto a qué?
Ese entorno (dentro de un ordenador con Linux), tiene:
- Su propia conf de red + Su propia IP
- Limitación de acceso a recursos HW
- Tiene su propio sistema de archivos (HDD)
- Sus propias variables de entorno

Docker desktop for windows  ->  crear una maquina virtual con hyperV (subsistema de linux para windows)
Docker desktop for mac      ->  crear una maquina virtual donde corremos un linux


Da igual el programa que venga allí dentro:
 TODOS SE OPERAN DE LA MISMA FORMA:
    Se instalan                             DEVOPS (AUTOMATIZAR)
    Se desisinstalan
    Se arrancan
    Se paran
    Se reinician
    Se configuran
    Se escalan
    Se monitorizan
 
 
---
Instalador -> INSTALACION v
Instalo office en mi computadora -> windows -> c:\archivos de programa\office -> ZIP -> email

ZIP -> c:\archivos de programa\office.     Funciona?
---

Los contenedores se crean desde IMAGENES DE CONTENEDOR

Qué es una IMAGEN DE CONTENEDOR?

Un fichero ZIP (tar) que congtiene un programa YA INSTALADO Y CONFIGURADO por 
alguien... normalmente que sabe 10 huevos más que yo del software que está instalando
No solo tiene el programa... 
+ Tiene todas las dependencias instaladas que mi programa necesita
+ Configuraciones que pueda necesitar mi programa

---

Tipos de software:
- Sistema operativo
- Driver
- Aplicación    Un software que corre en primer plano y está pensado para interactuar con un ser Humano
--------------- De aquí para abajo pueden ejecutar dentro de un contenedor
- Demonios      Un software que corre en segundo plano y que está pensado
    - Servicios     para atender peticiones de otros programas
- Script
- Comando

docker hub < Un registry de repos de imagenes de contenedor
quay.io    < El registry de redhat


# Openshift

Es una distribución de Kubernetes, la de redhat

# Kubernetes

Es un orquestador de gestores de contenedores

Automatizar la operación del entorno de producción de mi empresa.

# Openstack redhat + ubuntu

---

# Entorno de producción

- Alta Disponibilidad (HA)
    - Intentar ofrecer un determinado tiempo de servicio y no perder datos
- Escalabilidad
    - Ajustar la infra a las necesidades puntuales de mi app

Duplicación - Redundancia - Cluster
En los proximos 5 minutos, necesito 4 servidores nuevos.

Terraform -> AWS -> 5 servidores < Ansible
                        ^
                    Contenedor 