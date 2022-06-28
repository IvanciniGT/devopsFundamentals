# DEVOPS

Cultura de AUTOMATIZAR todo lo que pueda (entre el desarrollo y la operación)

Relacionado:
- Metodologías ágiles: simplificar... 
        ayudan a evitar retrasos y mejoran la experiencia de cliente
        nos hacen tener que instalar muchas veces
        nos hacen tener que hacer muuuuuchas pruebas
- Clouds:
    Proveedor de servicios (infraestructura > plataforma > software)    
        - Pago por uso
        - Automatizadamente (sin mediación humana)
    Flexibilidad y la inmediatez
    Clouds: AWS, AZURE, GCP, IBM Cloud, ...
- Contenedores: Ofrecen una alternativa para:
        - Empaquetar
        - Distribuir
        - Instalar
        - Y ejecutar software

Al adoptar una cultura devops, vamos pasando por distintas fases... 
en función de lo que hayamos conseguido automatizar:

TAREAS QUE HACEMOS 
    Planificación
    Desarrollo
    Empaquetado
        JAVA: maven + gradle + sbt
        JS:   npm + webpack
        Microsoft: msbuild, nuget
        Python: poetry
        C, C++, ADA: make
        GENERICA: ant
        
        Artefactos:
            JAVA: .jar , .war , .ear
            JS:   .zip
            Microsoft: .dll .exe
    ---------------------------------> Desarrollo ágil
    Pruebas
        Objetivo de las pruebas:
            - Identificar problemas -> Concreto
            - Probar que algo funciona / cumple con unos estándares
        Estáticas
            Calidad de código < SONARQUBE, Findbugs
        Dinámicas
            Funcionales
                Unitarias       Comprueban que una unidad de código (función, query) esta OK
                    JUNIT, TESTNG, MSUNIT, UNITTEST
                    Muchas pruebas
                Integración     Comunicación entre unidades de código
                Sistema         Que el software hace lo que debe hacer
                    Selenium      Pruebas de funcionamiento en un navegador web
                    Appium        Pruebas de funcionamiento en app un telefono            
                    Postman       Pruebas sobre un servicio web REST
                    SOAPUI        Pruebas sobre un servicio web SOAP
                Aceptación      Las de cliente
                    Muy pocas
                    
            No funcionales
                Alta disponilidad
                Carga
                Estres
                Rendimiento
                    Jmeter, Loadrunner
                UX - Mano
                Escalabilidad
        Para la parte de sistemas: Instalación, aprovisionamiento, configuración
            Provisionamiento: Terraform ~> Clouds
                              Vagrant   ~> VMWARE, CITRIX
            Configurar + instalar :
                Ansible
                    Puppet
                    Chef
                    Salt
    ---------------------------------> Integración Continua - CI
    Distribución
        Imágenes de contenedor < docker, podman
        Donde colocamos las imagenes de contenedor:
            Registry de repos de imagenes de contenedor:
                docker hub
                quay.io
                ECR
                gitlab artifacts
                - artifactory
                - nexus
                jenkins
    ---------------------------------> Entrega Continua - CD(elivery)
    Instalación en producción
        Helm < (Charts)
        
        Docker Swarm - No se usa
        Kubernetes (K8S , K3S, Tanzu, Openshift)
    ---------------------------------> Despliegue Continuo - CD(eployment)
    Operación y monitorización
        Kubernetes (Openshift)



Orquestador (Servidor de automatización, Servidor de CI/CD):
    Jenkins
    Azure Devops (TFS)
    TravisCI
    Gitlab CI/CD
    Github actions
    Bamboo
    TeamCity

SCM: Source code manager
    git. Cada involucrado en un proyecto, guarda su propio repositorio en local (en su pc)
         Pero necesita irlo compartiendo con otros intevinientes
         Repositorios remotos: Sirven para sincronizar el trabajo de un equipo
         Necesitamos entornos donde alojar esos repositorios remotos:
            gitlab < Más usado en las empresas
            github < Más usado en el mundo y especialmente en el mundo opensource
            bitbucket < atlassian (jira + confluence)
    subversion < svn
    cvs 
    mercurial
    
OBJETIVO: FLUJO COMPLETO:

                                                            Jenkins
                                                                V
                                      git                                    
Desarrollador >         codigo + conf. empaquetado    > Empaquetar el codigo
            
SysAdmins     >         codigo (terraform, ansible)   > Creación de un entorno 
                                                        de pruebas
                                                        Instalar la app
                                                        
Tester        >         codigo pruebas                > Solicitar la ejecución
                        conf prog pruebas               de las pruebas
                                                            (INFORME)
Desarrollo    >         conf. de imagen de contenedor > Generar una imagen de contenedor
                                                        Guardar en un registry

Sys Admins    >         codigo (terraform, ansible)   > Crear entorno de prod.
                                                            ENTORNO DE PROD

Desarrollo    >         charts de HELM                > Instalar en un Kub..
 + Devops

Testers       >         smoke test                    > Probar la instalación

        KUBERNETES SE ENCARGA DE OPERARLA Y MONITORIZARLA
                        
INSTALAR JENKINS EN 1 maquina


https://IP:8080/job/Java_Ivan/lastSuccessfulBuild/artifact/target/webapp.war