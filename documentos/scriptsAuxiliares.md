<div align=right>

|[Inicio](/README.md)|[Introducción](/documentos/intro.md)|[Panorámica](/documentos/panorámica.md)|[Prompts](/prompts/README.md)|[Ingeniería de Prompts](/ingenieriaDePrompts/README.md)|[Patrones](/ingenieriaDePrompts/patrones/README.md)|[Casos de Uso](/casosDeUso/README.md)|
|-|-|-|-|-|-|-

</div>

# Scripts auxiliaes

## Envio de emails desde Google Sheet

Hoja de cálculo con datos: Análisis

Columnas relevantes:

![](/imagenes/hojaCalculo.png)


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