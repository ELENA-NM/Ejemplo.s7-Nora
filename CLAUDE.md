# CLAUDE.md

Este archivo lo lee Claude cada vez que trabaja en esta carpeta, sin que se lo pidas.
Lo vas a llenar en la sesión. Por ahora trae solo las reglas que aplican desde el
primer minuto.

---

## 1. Qué es este proyecto y quién lo usa

Es el buzón de sugerencias del área, y ahora también el espacio para organizar la
cena navideña: proponer lugar y proponer menú. La usa cualquier persona del área,
sobre todo en las semanas antes de la cena.

## 2. De dónde sale cada cifra

Los datos de esta página viven en una tabla de Supabase llamada `registros`.
Ninguna cifra ni ningún texto que se muestre se escribe a mano en el HTML: todo
sale de esa tabla o de lo que la persona escriba en el formulario.

*(En la sesión le agregas las columnas que acabes usando.)*

## 3. Cómo quiero que trabajes aquí

- Antes de un cambio grande, dame el plan por escrito y espera mi visto bueno.
- Un cambio a la vez. Enséñame qué cambió antes de escribirlo.
- Trabaja siempre en una rama, nunca directo sobre `main`.
- **Cualquier cambio que se haga en cualquier rama se publica solo:** en cuanto
  quede listo, pide el pull, haz merge a `main`, y despliega todo a producción
  — tanto el sitio en Netlify como los cambios de Supabase. No hace falta que yo
  diga "haz pull y despliegue" cada vez; esto aplica siempre, automáticamente,
  para todas las ramas de aquí en adelante.
- **Excepción: si tienes acceso a mi base de datos, enséñame el SQL antes de
  correrlo y espera mi respuesta.** Crear o borrar tablas, agregar o quitar
  columnas y cambiar permisos no se deshacen con una rama: en cuanto corren, ya
  está. Esta parte del despliegue sigue esperando mi aprobación aunque el resto
  ya no la espere.

## 4. Lo que nunca debes hacer

- **Nunca escribas en esta carpeta una llave que empiece con `sb_secret_` o que
  diga `service_role`.** La única llave que puede estar aquí es la que empieza
  con `sb_publishable_`, que está hecha para andar a la vista.
- No inventes datos. Si algo no está en la tabla, que la página diga que no hay
  nada todavía, no un ejemplo.
- No borres el historial ni fuerces cambios sobre lo ya publicado.

## 5. Mi regla de verificación

Ya no hace falta que yo diga una frase para aprobar un despliegue: cada cambio
se fusiona a `main` y se publica solo en cuanto queda listo en su rama (salvo
el SQL de la base de datos, que sigue esperando mi respuesta — ver sección 3).
Lo que reviso yo es después: que la página y los datos se vean bien tras cada
despliegue. Si algo sale mal, lo digo y se corrige en la siguiente rama.

## 6. Cómo vuelvo a abrir esto

- El proyecto vive en este repositorio de GitHub (`ELENA-NM/Ejemplo.s7-Nora`).
- Se abre pidiéndole a Claude una sesión sobre este repo; no hace falta descargarlo.
- **La página todavía no tiene una liga pública funcionando.** Existe un sitio en
  Netlify (`ejemplo-s7-nora`), pero no está conectado a este repositorio y no
  tiene ningún despliegue exitoso todavía. Falta entrar a
  https://app.netlify.com/projects/ejemplo-s7-nora → "Link repository" → conectar
  este repo → rama `main`, para que quede con publicación automática.
- La base de datos está en supabase.com, en el proyecto **`curso-claude`** de esta
  cuenta.

> **Si la página deja de mostrar datos después de una semana sin usarla**, casi
> siempre es que el proyecto gratuito de Supabase se pausó. Se despierta con el
> botón **Resume project**.

## 7. Sistema de diseño

**Colores**

| Color | Uso |
|---|---|
| Azul — `#2563EB` | Color principal: encabezados, botones, enlaces |
| Verde — `#16A34A` | Confirmaciones, mensajes de éxito |
| Amarillo — `#F5B301` | Avisos, resaltados |

**Tipografía**

Calibri. Como es una fuente de Windows/Office y no viene instalada en todos los
navegadores, se usa con una pila de respaldo:

```css
font-family: Calibri, Candara, "Segoe UI", Optima, Arial, sans-serif;
```
