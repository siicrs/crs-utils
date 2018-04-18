# crs-utils
## Utilidades para CRS SII
Para poder firmar un archivo CRS se requiere:
- El RUT del dueño de certificado sin puntos ni dígito verificador, por ejemplo, el RUT 11.111.111-1 sería 11111111
- El certificado digital en formato p12, por ejemplo, [ks.p12](./ks.p12)
- La clave del almacén p12, por ejemplo, 11111111
- La clave de la llave privada, por ejemplo, 11111111
- El archivo XML CRS, por ejemplo, [crs.xml](./crs.xml)
- Descargar la utilidad [crs-utils.jar](./crs-utils.jar)
- Tener instalado [Java](http://www.oracle.com/technetwork/java/index.html) versión 8 o mayor

En el archivo [sign.bat](./sign.bat) se puede ver como llamar a la utilidad para firmar un archivo:
```
java -jar crs-utils.jar^
 -rut 11111111^
 -ks ks.p12^
 -kspass 11111111^
 -kpass 11111111^
 -file crs.xml
 ```
Al ejecutarlo se debería ver:
```
OK:
        Archivo [crs-utils\crs.xml]
        Firmado en archivo [crs-utils\crs-signed.xml]
        Para RUT [11111111]
```
Y se debería generar como resultado un archivo crs firmado [crs-signed.xml](./crs-signed.xml)

### Código
El código incluido en el archivo [crs-utils.jar](./crs-utils.jar) está basado en lo publicado por [IRS](http://irsgov.github.io) para FATCA
http://irsgov.github.io/IDES-Data-Preparation-Java/
