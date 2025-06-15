# 🔧 Solución al blur o pantalla negra al compartir pantalla de Microsoft Edge en Discord (2025)

Desactiva la optimización de ventanas en segundo plano de Microsoft Edge para evitar blur, congelamiento o pantalla negra al compartir pantalla (por ejemplo, en Discord).

Esto ocurre principalmente cuando se reproduce contenido como YouTube, Crunchyroll o Netflix en segundo plano.

---

## 🛠️ ¿Qué hace esto?

Modifica el registro de Windows para que Edge no pause el renderizado cuando está en segundo plano, eliminando el desenfoque o la pantalla negra al compartir.

---

## 📦 Archivos incluidos

- `disable_occlusion.reg`: Desactiva la detección de ventana en segundo plano.
- `enable_occlusion.reg`: Restaura el comportamiento por defecto (opcional).

---

## ✅ Cómo usar

1. **Descarga** el archivo `disable_occlusion.reg`.
2. Haz **doble clic** sobre él.
3. Acepta la advertencia del sistema para aplicar los cambios al Registro.
4. **COMPARTE**.

¡Listo! Ahora Edge seguirá funcionando normalmente aunque esté minimizado o en segundo plano.

---

## 🧯 Revertir los cambios

Si quieres volver al comportamiento original de Edge, ejecuta `enable_occlusion.reg` y reinicia tu PC.

---

## ⚠️ Advertencia

Este cambio modifica configuraciones del registro de Windows. 
Solo continúa si sabes lo que estás haciendo o confías en el archivo
El cambio es seguro, pero ocasionalmente podría requerir permisos de administrador.
