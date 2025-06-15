# Edge Disable Occlusion Fix

Desactiva la optimización de ventanas en segundo plano de Microsoft Edge para evitar blur, congelamiento o pantalla negra al compartir pantalla (por ejemplo, en Discord), especialmente al reproducir contenido como YouTube, Crunchyroll o Netflix.

---

## 🧩 ¿Qué causa el problema?

Microsoft Edge, por defecto, deja de renderizar contenido cuando detecta que está en segundo plano o minimizado.  
Esto genera efectos no deseados como:
- Pantalla negra al compartir por Discord
- Blur temporal al volver a enfocar Edge
- Congelamiento de video en streaming (DRM)

Anteriormente, esto se podía desactivar desde `edge://flags` usando opciones como:

- `Calculate window occlusion on Windows`
- `Native window occlusion`

Sin embargo, **desde la versión M130** en adelante, estas opciones quedaron **desatendidas (ya no disponibles)**,  
por lo que esta solución mediante el registro de Windows es actualmente la única forma funcional.

---

## 🛠️ ¿Qué hace esto?

Modifica el registro de Windows para que Edge no pause el renderizado cuando está en segundo plano,  
eliminando el desenfoque, congelamiento o pantalla negra al compartir.

---

## 📦 Archivos incluidos

- `disable_occlusion.reg`: Desactiva la detección de ventana en segundo plano.
- `disable_occlusion_chrome.reg`: Variante para Google Chrome u otros navegadores Chromium.
- `enable_occlusion.reg`: Restaura el comportamiento por defecto (opcional).

---

## ✅ Cómo usar

1. **Descarga** el archivo `.reg` correspondiente.
2. Haz **doble clic** sobre él.
3. Acepta la advertencia del sistema para aplicar los cambios al Registro.
4. **Reinicia tu navegador.**
5. **COMPARTE**.

¡Listo! Ahora tu navegador seguirá compartiendo normalmente aunque esté minimizado o en segundo plano.

---

## 🧯 Revertir los cambios

Si quieres volver al comportamiento original, ejecuta `enable_occlusion.reg` y reinicia tu navegador.  
¿Porque quisieras hacer eso?... pero bueno, lo dejo por si acaso.

---

## ⚠️ Advertencia

Este cambio modifica configuraciones del registro de Windows.  
Solo continúa si sabes lo que estás haciendo o confías en el archivo.  
El cambio es seguro, pero ocasionalmente podría requerir permisos de administrador.

---

## 🔁 Extra: ¿Usas otro navegador basado en Chromium?

También puedes aplicar este mismo método a **otros navegadores Chromium**, como **Google Chrome**, **Opera GX**, **Brave**, **Vivaldi**, etc.

Solo necesitas **modificar el archivo `.reg`** y reemplazar:

```reg
[HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Edge]
```

por:

```reg
[HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Google\Chrome]
```

> 🔄 Cambia `"Microsoft\Edge"` por `"Google\Chrome"` o el nombre correspondiente al navegador que uses.

Esto debería funcionar con cualquier navegador basado en Chromium que respete políticas de grupo de Windows.

**Nota:**  
Algunos navegadores pueden ignorar estas claves si no están compilados para respetar políticas empresariales.  
Aun así, Chrome y la mayoría de variantes modernas suelen aceptar estas configuraciones.
