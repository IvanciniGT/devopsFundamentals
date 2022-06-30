Kubernetes:

Orquestor de gestores de contenedores

KUBERNETES 1 maquina 32 Gbs RAM 

En kubernetes no trabajamos directamente con CONTENEDORES, sino con:

# POD

Cluster de Kubernetes: Varias maquians con kubernetes instalado
Kubernetes es un programa que toma control de esas maquinas
        Tambien toma control de los gestores de contenedores (DOCKER)
            que haya instaladas en esas maquinas.
            
# Contenedor

Entorno aislado donde ejecutar procesos dentro de un SO Linux

Pod: Grupo de contenedores. Todos los contenedores de un pod:
- Comparten red / IP
- Se despliegan en el mismo host
- Pueden compartir volumenes de almacenamiento (Sistios donde dejar información)
- Escalan juntos / simultaneamente


Al menos requieren 3: BBDD (kubernetes /etcd BBDD)
                      Mensajeria : Kafka, ActimeMQ
                      Redis (cache)
                      ElasticSearch (indexador)
                      
Cluster mariadb con 2 maquinas

Maquina MariaDB y otra maquina con una replica del MariaDB

Varias maquinas con MariaDB dando servicio conjuntamente
Brain Splitting


MariaDB1  ---->---------- MariaDB2* --------------- MariaDB3
  dato1                    dato1
                           dato2                     dato2
  dato4                    dato4                     dato3
    ^                       ^                          ^
    ----------------------------------------------------
                            |
                    Balanceador de carga (IP, fqdn)
                            ^
                            |
                         CLIENTE 
                          dato1
                          dato2
                          dato3
                          dato4
                          
                          
Objetos que configuramos en kubernetes:

POD : Conjuntos de contenedores


Cluster 50 maquinas fisicas, 100 maquinas fisicas: 
Dentro instalo Kubernetes
Le pido a Kubernetes que instale y mantenga/opere mi entorno de producción


El paradigma de lenguaje que usan estas herramientas:
    Puppet,
    Chef
    Ansible
    Kubernetes
    Terraform

Todos estos programas usan lenguaje DECLARATIVO    
    
Pon la silla debajo de la ventana !!!!!!                    Imperativo (bash, sh, powershell, python)
    -> Y Le doy la orden a alguien... y resulta que la silla YA ESTA bajo la ventana
    TE ESTOY DICIENDO LO QUE TIENES QUE HACER... y claro... te tengo que explicar TOOODOS LOS CASITOS
    
    
La silla debe estar debajo de la venta.                     DECLARATIVO
    No te digo lo que tienes que hacer
    
mkdir /tmp/prueba

