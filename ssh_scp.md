###################SSH##################
pasar archivos

scp /home/gnuxdar/GNUXDAR/arthur/DocArturo/CV_Arturo_Cabrera.pdf root@167.99.155.23:/var/www/clients/client2/web1/web/cv
___________________
scp /home/gnuxdar/GNUXDAR/arthur/DocArturo/Freelancer/gnuxdar/Moderna/index.html root@167.99.155.23/var/www/html/gnuxdar.com.ve/public_html

scp /home/gnuxdar/GNUXDAR/desweb/web_css/HTML5-CSS3/HTML5_Plantillas/arturocabrera.com.ve/public_html/index.html root@68.183.107.99:/var/www/html/arturocabrera.com.ve/public_html

scp /home/gnuxdar/GNUXDAR/desweb/web_css/HTML5-CSS3/HTML5_Plantillas/arturocabrera.com.zip  root@68.183.107.99:/var/www/html/gnuxdar.com.ve/public_html

scp -rp /home/gnuxdar/GNUXDAR/desweb/web_css/HTML5-CSS3/HTML5_Plantillas/arturocabrera.com.zip root@68.183.107.99:/var/www/html/

-rp son las banderas que le indican al comando scp que copie todo el contenido de la carpeta local al servidor con la misma estructura, incluyendo subcarpetas.

scp -P 22445 /home/gnuxdar/Documentos/eqsoft/codigo_fuente/cms_hotels.zip root@68.183.107.99:/var/www/html/arturocabrera.com.ve/public/


magento-cloud scp -r -e master /home/felipe/Descargas/pdf_estec/ remote:/app/pub/media/catalog/product/file/



[Descargar]
magento-cloud scp -r -e production remote:/app/uecnipkfuifpi/pub/media/wysiwyg /home/gnuxdar/Descargas/Martech/Khone/descargas/

[Cargar]
magento-cloud scp -r -e staging /home/gnuxdar/Descargas/Martech/Khone/descargas/ remote:/app/uecnipkfuifpi_stg/pub/media/wysiwyg

magento-cloud scp [-r|--recursive] [-p|--project PROJECT] [--host HOST] [-e|--environment ENVIRONMENT] [-A|--app APP] [--worker WORKER] [-i|--identity-file IDENTITY-FILE] [--] [<files>]...
