INSTRUCCIONES - FRUTERIA CHOFITA PWA

Archivos:
1. index_chofita_github_pages.html
   - Renómbralo a index.html antes de subirlo a GitHub Pages.
   - Busca CHOFITA_API y pega tu URL de Apps Script Web App en URL.
   - Si configuraste API_PIN en Apps Script, pon el mismo valor en PIN.

2. manifest.webmanifest
   - Déjalo junto al index.html.
   - Crea la carpeta icons/ con icon-192.png e icon-512.png.

3. sw.js
   - Déjalo junto al index.html.
   - Sirve para que la app se pueda instalar como PWA.

IMPORTANTE:
El HTML todavía tiene el botón "Postear a Bind ERP".
Para que funcione desde GitHub Pages, agrega esta acción al switch del handleApiRequest_ en Code.gs:

case "postearComprasABind":
  if (typeof postearComprasABind !== "function") {
    result = { ok: false, error: "No existe la funcion postearComprasABind en Apps Script." };
  } else {
    result = postearComprasABind(payload);
  }
  break;

Si no usas Bind todavía, puedes dejarlo así; solo fallará ese botón.
