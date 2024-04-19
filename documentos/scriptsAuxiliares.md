<div align=right>

||[![](https://img.shields.io/badge/-Inicio-FFF?style=flat&logo=Emlakjet&logoColor=black)](/README.md) [![](https://img.shields.io/badge/-Introducción-FFF?style=flat&logo=abbrobotstudio&logoColor=black)](/documentos/intro.md) [![](https://img.shields.io/badge/-Modelos_de_lenguaje-FFF?style=flat&logo=LiveChat&logoColor=black)](/documentos/LLMs.md) [![](https://img.shields.io/badge/-Panorámica-FFF?style=flat&logo=openstreetmap&logoColor=black)](/documentos/panoramica.md)<br>  [![](https://img.shields.io/badge/-Prompts-FFF?style=flat&logo=Proton&logoColor=black)](/documentos/prompts/README.md) [![](https://img.shields.io/badge/-Ing,_de_prompts-FFF?style=flat&logo=googleearthengine&logoColor=black)](/documentos/ingenieriaDePrompts/README.md) [![](https://img.shields.io/badge/-Patrones-FFF?style=flat&logo=textpattern&logoColor=black)](/documentos/ingenieriaDePrompts/patrones/README.md) [![](https://img.shields.io/badge/-Casos_de_uso-FFF?style=flat&logo=gitbook&logoColor=black)](/documentos/casosDeUso/README.md)|
|-:|

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