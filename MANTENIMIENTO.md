# Mantenimiento — qué es cada cosa y qué se toca al sacar una versión

Nota interna. Quien instala no lee esto: para eso está
[la guía](https://asistente-fda.github.io/instalador/).

## Cuál es cuál

Hay varios repositorios parecidos dando vueltas. Este es el único que ve el
cliente.

| Dónde | Qué es |
|---|---|
| **`asistente-fda/instalador`** (este, público) | La cara pública. Aloja la **guía** en `https://asistente-fda.github.io/instalador/` y los **releases** con los `.exe` que se descargan. No tiene código del programa. |
| `alejojoto/fda_intg` (privado) | El proyecto: el código, y el workflow que compila el instalador. Publica un release **interno** en sí mismo; de ahí sale la URL del `.exe` que se le pasa a este repositorio. |
| `alejojoto/fda_intg_distribucion` | El bytecode que se bajan las máquinas de operación al actualizarse. No es una descarga para personas. |
| `alejojoto/fda-asistente-instalador` (público, viejo) | Quedó en la 1.1.2 y está superado por este. No se publica más ahí. |

## La guía

`index.html` en la raíz, servido por GitHub Pages desde la rama `main`. Es una
sola página sin dependencias: el CSS va dentro y las capturas son archivos de
`imagenes/`.

Los círculos numerados y las flechas están puestos en **porcentajes** sobre cada
captura, no en píxeles. Si alguna imagen se reemplaza o se recorta, hay que
volver a calcular esos porcentajes o el marcador queda apuntando a otro lado.

## Al sacar una versión nueva

**Nada de esto es automático todavía.** El release nuevo no actualiza la guía
solo, y si no se toca, los botones de descarga siguen apuntando a la versión
anterior.

1. Correr el workflow **publicar instalador** con la versión y la URL del `.exe`
   ya compilado. Crea el release y sus notas.
2. Subir a mano al release el `.exe` del soporte remoto, si esa versión lo lleva:
   el workflow no lo adjunta.
3. **Actualizar `index.html`**: la versión aparece en tres sitios, todos en la
   cabecera de la página — el renglón `Asistente FDA · versión X · Windows` y los
   dos enlaces de descarga (la versión va en la carpeta del release y también
   dentro del nombre del archivo).

El paso 3 se puede automatizar metiéndolo en `publicar.yml`, que ya recibe la
versión como parámetro. Mientras no se haga, es el paso que se olvida.
