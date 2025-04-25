# Publicación de la Aplicación Pokédex en Azure

Este documento explica de manera ordenada el proceso completo para preparar, probar y desplegar la aplicación Pokédex utilizando los servicios en la nube de Microsoft Azure.

---

## 1. Preparación Inicial del Proyecto

- Se descargó el código fuente desde el repositorio en GitHub:  
  [https://github.com/rcuello/ac4dem1a](https://github.com/rcuello/ac4dem1a)

- El código fue ubicado dentro de la estructura de carpetas en:  
  `sistemas-distribuidos/poke-dex-lab/source/pokedex-angular`

---

## 2. Verificación Local

- Se accedió al directorio raíz del proyecto Angular:
  ```bash
  cd ruta/del/proyecto/pokedex-angular
  ```

- Se instalaron las dependencias utilizando el gestor de paquetes.  
- Se ejecutó el servidor de desarrollo localmente.  
- Se comprobó que la aplicación funcionaba correctamente ingresando a:  
  [http://localhost:4200](http://localhost:4200)

---

## 3. Registro en Microsoft Azure

- Se ingresó al portal oficial de Azure: [https://azure.microsoft.com](https://azure.microsoft.com)  
- Se realizó el inicio de sesión utilizando credenciales institucionales.  
- Se buscó el servicio **Static Web Apps** en el panel principal.  
- Se seleccionó la opción **Crear** para comenzar el despliegue.  
- Se eligió GitHub como proveedor del código fuente y se autorizó el acceso correspondiente.  
- Se configuró el plan gratuito **Estándar** para la aplicación.

---

## 4. Implementación en Azure

- Se completaron los campos requeridos para la publicación: suscripción activa, grupo de recursos, nombre único de la aplicación (por ejemplo, `pokedex-app`), organización y repositorio.  
- Se seleccionó la rama `master` y Azure detectó automáticamente el framework Angular.  
- Se especificó la ruta correcta del proyecto:  
  ```
  sistemas-distribuidos/poke-dex-lab/source/pokedex-angular
  ```
- Se revisó la configuración y se procedió con la creación del recurso.  
- Azure llevó a cabo el despliegue de forma automática.  
- Al finalizar, se generó una URL pública para acceder a la aplicación.

---

## 5. Incidencia Durante el Despliegue

Luego de completar el proceso, se observó que las **imágenes no se cargaban correctamente** al acceder al sitio publicado.

**Causa Identificada:**

El error se debía a una configuración incorrecta de la ruta hacia los recursos gráficos. En el archivo `src/environments/environment.prod.ts`, la propiedad `imagesPath` tenía el siguiente valor:

```ts
imagesPath: '/pokedex-angular/assets/images'
```

Dado que en producción los archivos se sirven desde la raíz, esa ruta no era válida.

**Ajuste Realizado:**

Se actualizó el valor de la propiedad a:

```ts
imagesPath: '/assets/images'
```

---

## 6. Fortalecimiento de Seguridad

Para optimizar la seguridad de la aplicación en producción, se recomienda crear el archivo `staticwebapp.config.json` en el directorio del proyecto:

```
sistemas-distribuidos/poke-dex-lab/source/pokedex-angular
```

El contenido del archivo debe ser el siguiente:

```json
{
  "globalHeaders": {
    "Content-Security-Policy": "default-src * 'unsafe-inline' 'unsafe-eval' data: blob:;",
    "X-Frame-Options": "ALLOWALL",
    "Permissions-Policy": "geolocation=*, camera=*, microphone=*"
  }
}
```

Este archivo establece encabezados HTTP globales que fortalecen la seguridad ante accesos externos, controlan los permisos del navegador y regulan el uso de iframes.

> Esta configuración ayuda a obtener una **calificación de seguridad A** en herramientas de evaluación para sitios web.

## 7. Estado Final del Despliegue

- La aplicación quedó operativa en Azure sin inconvenientes.  
- Todos los elementos visuales y funciones se cargan adecuadamente.  
- La URL pública muestra la Pokédex en su versión funcional final.

## URL: [https://zealous-cliff-09216a41e.6.azurestaticapps.net/](https://zealous-cliff-09216a41e.6.azurestaticapps.net/)
---

