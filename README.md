# Guía para la Creación de Cuenta en Azure y Despliegue de Aplicación Pokédex

Este documento describe el proceso de creación de una cuenta en **Microsoft Azure** utilizando un correo institucional, así como el despliegue de una aplicación web estática (**Pokédex**) mediante la integración con **GitHub**.

---

## Acceso a Microsoft Azure

1. Ingresar al sitio oficial de Azure: [https://azure.microsoft.com](https://azure.microsoft.com)  
2. Hacer clic en **"Iniciar sesión"** (parte superior derecha).  
3. Iniciar sesión con el correo y contraseña del correo institucional.

---

## Inicio de sesión en GitHub

1. Ir al sitio web de GitHub: [https://github.com](https://github.com)  
2. Iniciar sesión con la cuenta que contiene el repositorio del proyecto **Pokédex**.

---

## Vinculación entre Azure y GitHub

1. En el portal de **Azure**, buscar y seleccionar **"Static Web Apps"**.  
2. Hacer clic en **"Crear"**.  
3. Seleccionar **GitHub** como origen del código.  
4. Iniciar sesión en GitHub si es necesario y autorizar los permisos para vincular ambas cuentas.

---

## Configuración del Proyecto para Despliegue

Completar los campos del formulario con los siguientes datos:

- **Suscripción:** Seleccionar la que esté activa.  
- **Grupo de recursos:** Crear uno nuevo o seleccionar uno existente.  
- **Nombre:** Especificar un nombre único para la aplicación (ejemplo: `pokedex-app`).  
- **Plan de hospedaje:** Seleccionar _Estándar (para aplicaciones de producción de uso general)_.  
- **Origen del código:** GitHub  
- **Organización:** Escribir el nombre de usuario u organización del repositorio.  
- **Repositorio:** Seleccionar el repositorio del proyecto.  
- **Rama:** Seleccionar `"master"`.  
- **Framework detectado:** Angular _(detección automática)_.  
- **Ubicación de la aplicación:**  
  ```
  sistemas-distribuidos/poke-dex-lab/source/pokedex-angular
  ```

Luego de completar el formulario:

- Hacer clic en **"Revisar + crear"**  
- Finalmente, hacer clic en **"Crear"**

---

## Despliegue de la Aplicación

- Azure iniciará el **despliegue automático** de la aplicación.  
- Una vez finalizado, se generará una **URL pública** donde se podrá acceder a la página web.

En mi caso es:  
[https://zealous-cliff-09216a41e.6.azurestaticapps.net/](https://zealous-cliff-09216a41e.6.azurestaticapps.net/)
