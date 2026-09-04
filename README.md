# GISOSA — Landing

Sitio estático para GISOSA (Gestión Integral y Soluciones en Salud).

## Archivos

- `index.html` — landing principal
- `clinova.html` — página de producto Clinova (línea de software/tecnología)

Ambas páginas son componentes React que se transpilan en el navegador con
Babel standalone (React se carga desde unpkg.com), por lo que no requieren
proceso de build: se pueden abrir directamente o servir como archivos estáticos.

## Desarrollo local

Al ser HTML estático, basta con abrir el archivo en el navegador o servirlo
con cualquier servidor estático, por ejemplo:

```
python3 -m http.server 8000
```

y visitar `http://localhost:8000/index.html`.

## Despliegue

- **Netlify**: netlify.com/drop → arrastrar la carpeta del repo (o conectar el repo de Git).
- **Vercel**: vercel.com → New Project → importar el repo.
- **GitHub Pages**: Settings → Pages → Deploy from branch, sirviendo `index.html` desde la raíz.
- **cPanel/FTP**: subir el contenido a `public_html/`.

### Subdominio para Clinova (clinova.gisosa.com)

Crear un registro CNAME en el DNS apuntando al host y publicar `clinova.html`
como `index.html` en ese subdominio.

## Nota técnica

Para producción conviene precompilar el JSX y usar los builds de producción
de React (en vez de los builds de desarrollo cargados desde unpkg) para
acelerar la carga.
