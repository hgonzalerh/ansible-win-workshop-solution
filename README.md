# Ansible for Windows Demo:

## Preparación

- Tener listo el laboratorio de Windows Automation  https://demo.redhat.com/catalog?search=windows&item=babylon-catalog-prod%2Fansiblebu.aap2-workshop-windows.prod 
- Tener lista la documentación oficial sobre los módulos certificados de la colección Windows en Automation Hub https://console.redhat.com/ansible/automation-hub/repo/published/ansible/windows/

## Actividades
### Automation Controller y ad-hoc commands

No sigas las actividades del Workshop al pie de la letra. Hazlas en este orden

1. Hacer login en Automation Controller
2. Crear credencial de machine - Workshop Credential
4. Mostrar inventarios para el grupo Workshop Inventory -> windows y las variables de grupo para winrm y la conexión
5. Correr win_ping ad-hoc sobre la máquina studentx-win1 y mostrar la salida
6. Correr win_shell ad-hoc con el argumento Get-Service, credencial Workshop Credential
7. Correr win_shell ad-hoc con el argumento Get-Process, credencial Workshop Credential
8. Correr el módulo setup sin argumento, credencial Workshop Credential
9. Regresar a los jobs y explicar los servicios y los resultados
10. Instalar IIS con el módulo win_feature con el argumento	name=Web-Server state=present, mostrar el módulo 
11. Arrancar el servicio de IIS usando el módulo win_service con los argumentos name=W3Svc state=started
12. Probar la página creada en el server studentx-win1 desde la web
13. Apagar el servicio de IIS usando el módulo win_service con los argumentos name=W3Svc state=stopped
14. Probar la página creada y ver que ya no funciona


### Inicio a playbooks
1. Mostrar el mismo código dentro de un playbook en el repositorio https://github.com/hgonzalerh/ansible-win-workshop-solution/blob/main/iis_basic/install_iis.yml
1. Crear credencial de SCM
1. Crear el proyecto
1. Crear el job template con:
    credentials: windows credentials
    playbook: iis_basic/install_iis.yml
1. Correr y dejar fallar, explicar que falta la variable del mensaje y que crearemos un survey para ella.
1. Crear un survey con la variable iis_test_message
1. Mostrar la página resultante 


