# Rancho Viejo — Sitio web

Sitio de las dos sucursales de Rancho Viejo (Neper y Nores Martínez) y de la Fábrica de Pastas.
Es un sitio estático: solo archivos HTML, imágenes y PDFs. No necesita servidor ni base de datos.

---

## Cómo actualizar la carta o el menú de una sucursal

**Regla de oro: el archivo nuevo tiene que llamarse exactamente igual que el que reemplaza.**
Si el nombre cambia, la página deja de encontrarlo.

| Qué querés cambiar | Archivo a reemplazar |
|---|---|
| Carta de Neper | `neper/carta.pdf` |
| Carta de Nores Martínez | `nores-martinez/carta.pdf` |
| Carta de la Fábrica de Pastas | `pastas/carta.pdf` |
| Menú ejecutivo de Neper | `neper/menu-ejecutivo-neper.png` |
| Menú ejecutivo de Nores Martínez | `nores-martinez/menu-ejecutivo-nores.martinez.png` |
| Foto de portada de Neper | `neper/portada.jpg` |
| Foto de portada de Nores Martínez | `nores-martinez/portada.jpg` |
| Foto de portada de Pastas | `pastas/portada.jpg` |
| Foto de fondo de la franja "Fábrica de Pastas" | `pastas.jpg` (en la raíz) |
| Foto de fondo del encabezado del inicio | `fondo.jpg` (en la raíz) |

### Paso a paso desde la web de GitHub

1. En tu computadora, renombrá el archivo nuevo con el nombre exacto de la tabla
   (respetá minúsculas, guiones y el punto de `nores.martinez`).
2. Entrá al repositorio en GitHub y abrí la carpeta de la sucursal (`neper`, `nores-martinez` o `pastas`).
3. Botón **Add file** → **Upload files**.
4. Arrastrá el archivo nuevo. GitHub va a avisar que ya existe uno con ese nombre: está bien, lo pisa.
5. Abajo, en *Commit changes*, escribí algo corto como `Actualizo carta Neper` y confirmá.
6. Esperá 1 o 2 minutos y recargá el sitio. Si seguís viendo la versión vieja, abrí la página
   con `Ctrl + F5` (o en el celular, recargá desde una pestaña nueva) — es el caché del navegador.

---

## Las imágenes de fondo

Hay dos fotos de fondo que se repiten en varias páginas. Cada una es **un solo archivo**:
lo reemplazás una vez y cambia en todos lados.

**`pastas.jpg`** (en la raíz) es la foto de fondo de la Fábrica de Pastas. Aparece en 4 lugares:
la franja "Conocé también nuestra Fábrica de Pastas" de las dos sucursales, y el encabezado
y el pie de la página de Pastas.

**`fondo.jpg`** (en la raíz) es la textura del encabezado de la página de inicio y del fondo
de las páginas de sucursal.

Al reemplazarlas, tené en cuenta:

**Medida recomendada: 1600 × 1200 px** (o 1920 × 1440, misma proporción 4:3).
Las de ahora son `pastas.jpg` 1600 × 1131 y `fondo.jpg` 1013 × 1800.

No hace falta que sea exacta: la web recorta sola según la pantalla. Pero ojo con esto,
porque el recorte es distinto en cada lugar:

- En la franja de las sucursales se ve una **tira ancha y baja** (se recorta arriba y abajo).
- En el encabezado de la página de Pastas, en celular, se ve una **tira alta y angosta**
  (se recorta a los costados).

Por eso **lo único que se ve siempre es el centro de la foto**. Poné ahí lo importante
(las pastas, el producto) y dejá los bordes con relleno.

Además:

- Encima va texto blanco y un velo oscuro, así que conviene una foto **sin zonas muy claras
  en el centro**.
- Guardala como `.jpg` con el nombre exacto (`pastas.jpg` o `fondo.jpg`) y por debajo de 500 KB.
  Si pesa más, pasala por un compresor de imágenes online antes de subirla.

---

## Cómo se muestra la carta

En cada página hay un botón **Ver la carta completa** que despliega el PDF hacia abajo,
página por página, tal cual está diseñado. Se puede scrollear y hacer zoom con los dedos.

Antes la carta iba metida en un recuadro y en el celular se veía una sola hoja cortada.
Ahora la dibuja el visor que está en la carpeta `pdfjs/`. **Esa carpeta no se toca ni se borra**:
si desaparece, el botón deja de mostrar la carta y solo queda el link para abrir el PDF aparte.

Vos seguís actualizando igual que siempre: reemplazás `carta.pdf` y listo, el visor toma
el archivo nuevo automáticamente, con la cantidad de páginas que tenga.

---

## Cuidado con el peso de los PDF

Las cartas que exporta Canva pesan 17-18 MB. Así como salen, en un celular con datos
tardan muchísimo en abrir y mucha gente cierra la página antes de verlas.

Las que están subidas ahora fueron comprimidas a ~3,5 MB y se ven igual en pantalla.
Los PDF originales sin comprimir están guardados fuera de este repositorio, en la carpeta
`ORIGINALES/cartas` del proyecto.

**Antes de subir una carta nueva, comprimila.** Opciones:

- En Canva, al exportar: elegí *PDF estándar* en vez de *PDF para imprimir*.
- O pasala por un compresor online (buscá "comprimir PDF").
- Objetivo: que quede por debajo de 5 MB.

> GitHub no acepta archivos de más de 25 MB por la web, así que igual conviene comprimir.

---

## Estructura de archivos

```
index.html              → página de inicio: elegir sucursal
fondo.jpg               → fondo del encabezado
logo.png                → logo Rancho Viejo
pastas.jpg              → foto del bloque "Fábrica de Pastas"
fotos/                  → galería de fotos del restaurante (se usa en las dos sedes)
pdfjs/                  → visor de cartas. NO TOCAR ni borrar.

neper/
  index.html                  → página de la sucursal
  carta.pdf                   ← SE ACTUALIZA
  menu-ejecutivo-neper.png    ← SE ACTUALIZA
  portada.jpg                 → foto de la tarjeta en el inicio

nores-martinez/
  index.html
  carta.pdf                            ← SE ACTUALIZA
  menu-ejecutivo-nores.martinez.png    ← SE ACTUALIZA
  portada.jpg

pastas/
  index.html
  carta.pdf             ← SE ACTUALIZA
  portada.jpg
  fotos/                → galería de la fábrica de pastas
```

Los archivos marcados con ← son los únicos que se tocan en el día a día.
El resto (los `index.html`) solo se modifica si hay que cambiar textos, teléfonos o direcciones.

---

## Dónde vive el sitio

Repositorio: `sofiagcastex-spec/rancho-viejo-web`
Sitio publicado: https://rancho-viejo-web.vercel.app

El sitio lo publica **Vercel**, no GitHub Pages. Vercel está conectado al repositorio:
cada vez que se sube un cambio a la rama `principal`, redeploya solo en 1 o 2 minutos.
No hay que tocar nada en Vercel.

Vercel sirve desde la **raíz** del repositorio, así que `index.html` tiene que quedar
arriba de todo, no adentro de una carpeta.

Cada sucursal queda en su propia dirección y se pueden compartir sueltas:

- https://rancho-viejo-web.vercel.app/neper/
- https://rancho-viejo-web.vercel.app/nores-martinez/
- https://rancho-viejo-web.vercel.app/pastas/

## Datos cargados en el sitio

| | Neper | Nores Martínez | Fábrica de Pastas |
|---|---|---|---|
| Dirección | Av. Juan Neper 5788 | Av. Rogelio Nores Martínez 1900 | Av. Carlos F. Gauss 5488, Local 5 |
| Teléfono | 0351 468 3685 / 351 377 1992 | 0351 468 3685 / 351 377 1992 | 351 653 4898 |
| WhatsApp | https://wa.link/8ycklb | https://wa.me/543513771992 | https://wa.link/wzp8e2 |

Para cambiar un teléfono, una dirección o un link de WhatsApp hay que editar el `index.html`
de esa carpeta. Si no te sentís cómoda tocando el HTML, avisá y se cambia.
