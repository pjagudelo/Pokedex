Guía para la Creación de Cuenta en Azure y Despliegue de Aplicación Pokédex

Este documento describe el proceso de creación de una cuenta en Microsoft Azure utilizando un correo institucional, así como el despliegue de una aplicación web estática (Pokédex) mediante la integración con GitHub.

1. Acceso a Microsoft Azure

- Ingresar al sitio oficial de Azure: https://azure.microsoft.com
- Hacer clic en "Iniciar sesión" (parte superior derecha).
- Iniciar sesión con el correo y contraseña del correo institucional.

2. Inicio de sesión en GitHub

- Ir al sitio web de GitHub: https://github.com
- Iniciar sesión con la cuenta que contiene el repositorio del proyecto Pokédex.

3. Vinculación entre Azure y GitHub

- En el portal de Azure, buscar y seleccionar "Static Web Apps".
- Hacer clic en "Crear".
- Seleccionar GitHub como origen del código.
- Iniciar sesión en GitHub si es necesario y autorizar los permisos para vincular ambas cuentas.

4. Configuración del Proyecto para Despliegue

Completar los campos del formulario con los siguientes datos:

- Suscripción: Seleccionar la que esté activa.
- Grupo de recursos: Crear uno nuevo o seleccionar uno existente.
- Nombre: Especificar un nombre único para la aplicación (ejemplo: pokedex-app).
- Plan de hospedaje: Seleccionar "Estándar (para aplicaciones de producción de uso general)".
- Origen del código: GitHub.
- Organización: Escribir el nombre de usuario u organización del repositorio.
- Repositorio: Seleccionar el repositorio del proyecto.
- Rama: Seleccionar "master".
- Framework detectado: Angular (detecto automático).
- Ubicación de la aplicación: Reemplazar la ruta por defecto y escribir:
  sistemas-distribuidos/poke-dex-lab/source/pokedex-angular

Luego de completar el formulario, hacer clic en "Revisar + crear" y después en "Crear".

5. Despliegue de la Aplicación

- Azure iniciará el despliegue automático de la aplicación.
- Una vez finalizado, se generará una URL pública donde se podrá acceder a la página web.

En mi caso es:
https://zealous-cliff-09216a41e.6.azurestaticapps.net/
