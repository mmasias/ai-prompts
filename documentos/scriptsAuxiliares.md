<div align=right>

|[![](https://img.shields.io/badge/-Inicio-FFF?style=flat&logo=Emlakjet&logoColor=black)](/README.md) [![](https://img.shields.io/badge/-Introducción-FFF?style=flat)](/documentos/intro.md) [![](https://img.shields.io/badge/-Panorámica-FFF?style=flat)](/documentos/panorámica.md) [![](https://img.shields.io/badge/-Prompts-FFF?style=flat)](/documentos/prompts/README.md) [![](https://img.shields.io/badge/-Ingeniería_de_prompts-FFF?style=flat)](/documentos/ingenieriaDePrompts/README.md) [![](https://img.shields.io/badge/-Patrones-FFF?style=flat)](/documentos/ingenieriaDePrompts/patrones/README.md) [![](https://img.shields.io/badge/-casos_de_uso-FFF?style=flat)](/documentos/casosDeUso/README.md)|
|-|

</div>

# Scripts auxiliaes

## Envio de emails desde Google Sheet

Hoja de cálculo con datos: Análisis

Columnas relevantes:

![](/documentos/imagenes/hojaCalculo.png)


```
function validaEnvioCorreos() {

  var documento = SpreadsheetApp.getActiveSpreadsheet()
  var hoja = documento.getSheetByName('Análisis');
  var subject = "RespuestaDeGPT"
  var direccionDeCorreo = "manuel@masiasweb.com"

  for (var fila = 2; fila < 150; fila = fila + 1){

    var recibido = hoja.getRange(fila,11).getValue();
    var gestionado = hoja.getRange(fila, 13).getValue();

    if (recibido && !gestionado) {

      var hayQueEnviar = hoja.getRange(fila, 12).getValue();

      if (hayQueEnviar) {
        var elMensaje = hoja.getRange(fila, 10).getValue();
        MailApp.sendEmail(direccionDeCorreo, subject + ">" + fila, elMensaje);
      }

      hoja.getRange(fila,13).setValue(true)
    }
  }
}
```