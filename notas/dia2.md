# Devops = Automatizar

## Integración continua:

Cuando conseguimos tener la última verisón del código de un programa continuamente
en el entorno de integración, siendo ésta sometida a pruebas autoamtizadas.

## Entrega Continua:

Cuando conseguimos entregar (hacer llegar) a nuestro cliente(s) la última 
versión de nuestro software de forma automatizada

## Despliegue Continuo:

Cuando conseguimos instalar en producción a nuestro cliente(s) la última 
versión de nuestro software de forma automatizada

# Clouds ~ DEVOPS

Hoy en día usamos clouds como proveedores de infra. En ellos querremos crear, 
destruir, configurar infra AUTOMATIZADAMENTE

# Contenedores

Un contenedor es un entorno aislado en el que ejecutar procesos dentro de un SO Linux.

Esto nos viene genial en entorno de producción:
    - Unos procesos no afectan ni pueden ver a otros
    - Las configuraciones / dependencias de una app no van a afectar a otras

Esto nos viene genial en entorno de integración:
    - Nos ofrecen la posibilidad de disponer de entornos de un solo uso.

Los contenedores son un reemplazo de las maquinas virtuales en algunos escenarios.

# Todos los perfiles técnicos del mundo IT los convertimos en programadores a día de hoy.

Administradores de sistemas ->  No administran sistemas
                                Crea programas o configura programas para que administren sistemas
Testers Q&A                 ->  No ejecutan pruebas
                                Crean programas o configuran programas para que nuestros aplicativos
                                
# Código de mi aplicacion/software

Antiguamente el código de una aplicación lo guardábamos en un Sistema de Control de código Fuente: SCM

Hoy en día además, en el SCM guardamos como parte del proyecto:
- Programas de Prueba
- Infraestructura como código: terraform

SCM:
- cvs 
- svn (Subversion)
- mercurial
- git

git: SCM...
Linus Torvalds
    Kernel se SO más usado del mundo: Linux
    Sistema de control de código fuente para poder hacer linux: git 
    
Es un SCM distribuido:
    - Cada persona tiene una copia propia del repositorio (del código)... distingta a la de los demás
    - Entre todas esas copias tenemos todo el código.
    - Los involucrados un un proyecto comparten su código a través de lo que llamamos repositorios remotos.
    
Un repo remoto es una ubicación en RED donde los intervienentes de un proyecto
dejan su código para que otros puedan cogerlo.

Existen varios productos comerciales que nos permiten alojar repos remotos de git:
- gitlab
- bitbucket (Atlassian)
- github (Microsoft)

Atlassian:
- Jira
- Confluence
- BitBucket
- Bamboo: Es el equivalente a Jenkins de la gente de Atlassian


Servidor/Orquestador de CI/CD (Automatización)
Y de donde saca Jenkins... el código de los programas:
    - Código de un playbook de Ansible
    - Código de una prueba con Selenium
    
El conjunto de todas las tareas que deben realizarse por parte de un Servidor de Automatización
con respecto a un proyecto: PipeLines

Hay muchos servidores de automtización: Jenkins, Bamboo, TravisCI, Github CI/CD, Gitlab CI/CD, TeamCity

JetBrains: Fabrica entornos de desarrollo
JAVA: IntelliJ
Python: Pycharm

---

Pruebas
- Estáticas: No requieren poner en marcha (ejecutar) algo para comprobarlo
    - Pruebas estáticas de calidad de código: SonarQube, Findbugs...
    - Revisar un modelo de datos por un equipo o expertos, antes de su puesta en marcha
    - Revisar los requisitos
- Dinámicas
    - Funcionales
        - Unitarias     Prueba diseñada para probar una FUNCIONALIDAD concreta de un sistema
                            Ejemplos: -   Prueba de una conexión a una BBDD
                                      -   Prueba de una query
                                      -   Una función de un programa que calcula una información o hace una gestión
                            Frameworks de pruebas unitarias:
                                JUnit, TestNG, MSTest, TestUnit
        - Integración   Lo que prueba es una Comunicación entre componentes
        - Sistema       Probamos el sistema como un todo: Procesos
            - UI
        - Aceptación    Las que marca el cliente / requisitos           ***** Solo haciamos pruebas de aceptación
                        - GUERKIN > CUCUMBER Generar el esqueleto de las pruebas de aceptación
    - No funcionales
        - Rendimiento               JMeter
        - Alta disponibilidad
        - Carga
        - Estres
        - UX


Libreria:   Colección de funciones y/o programas relacionados con una funcionalidad o tipos de gestión
Framework:  Conjunto de librerias
            + metodologías de eso
            

El objetivo de una prueba 
- no es solo comprobar si algo es como deberia ser, o que lo hemos hecho de una forma suficientemente buena            
- Si no cumplo, informar de cual es el problema que se ha presentado !!!!!!
            
            
      XXXX           Pruebas de aceptación

     XXXXXXX
     XXXXXXX         Pruebas de sistema

  XXXXXXXXXXXXXX
  XXXXXXXXXXXXXX     Pruebas de integración

XXXXXXXXXXXXXXXXXX   Pruebas unitarias
XXXXXXXXXXXXXXXXXX

Metodologias de gestión del desarrollo de software: Ágiles, Scrum, Xtreme programming, Kanban
Metodologias de desarrollo de software:             TDD < BDD < ATDD
                                                    Test Driven Development:
                                                        - Diseña primero las pruebas
                                                        - Escribe el codigo hasta que las pruebas pasen
                                                    

Apps: desde donde se usan:
- Navegador Internet    (app webs)
    - Que funcione en un navegador, no implica que funione en otro
    - Qué funcione en una versión de un navegador, no implica que funcione en la siguiente o en la anterior
    - Depende también de si lo uso desde un portatil, tablet, movil
    - SO: Windows, Android, Linux, MacOS, iOS

    AUTOMATIZAR: Selenium (Script)
                 Selenium grid (Granja de entornos de prueba)

- Movil                 (apps nativas)
    Android tiene la hueva de versiones que cambian un monton entre si
    iOS no tanto, pero algo
    Dispositivos físicos distintos

    AUTOMATIZAR: appium

