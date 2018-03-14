## Manipular los informes del sigad

Podemos manipular las orlillas del sigad con esta macro de Excel:

```
Sub Macro1()


Dim i, j, k, l, fila_inicial, columna_inicial, nalumnos, nasignaturas As Integer
Dim asignatura As String


    fila_inicial = 2
    columna_inicial = 2
    Sheets("Hoja1").Select
    Range("A" & fila_inicial).Select
    i = ActiveCell.Row
    
    Selection.End(xlDown).Select
    j = ActiveCell.Row
    
    nalumnos = j - i + 1
    
    Cells(1, columna_inicial).Select
    
    i = ActiveCell.Column
    
    Selection.End(xlToRight).Select
    j = ActiveCell.Column
    
    nasignaturas = j - i + 1
    
    ' MsgBox alumnos
    
    Sheets("Resultados").Select
    Cells(1, 1).Value = "Nombre"
    Cells(1, 2).Value = "Asignatura"
    Cells(1, 3).Value = "Matricula"
    
    i = fila_inicial
    
    
    For k = 1 To nasignaturas
    
    Sheets("Hoja1").Select
    asignatura = Cells(1, columna_inicial - 1 + k).Value
    
    
    Range(Cells(fila_inicial, 1), Cells(fila_inicial + nalumnos - 1, 1)).Select
    Application.CutCopyMode = False
    Selection.Copy
    Sheets("Resultados").Select
    Cells(i, 1).Select
    ActiveSheet.Paste
          
    Range(Cells(i, 2), Cells(i + nalumnos - 1, 2)).Value = asignatura
    
    Sheets("Hoja1").Select
    Range(Cells(fila_inicial, columna_inicial - 1 + k), Cells(fila_inicial + nalumnos - 1, columna_inicial - 1 + k)).Select
    Application.CutCopyMode = False
    Selection.Copy
    Sheets("Resultados").Select
    Cells(i, 3).Select
    ActiveSheet.Paste
    
          
    i = i + nalumnos
       
    Next
        
    
End Sub
```
Esperemos que los desarrolladores de la aplicación vayan mejorando el generador de informes. Hasta entonces me tocará usar esta macro de visual basic.

Normalmente sigo estos pasos antes de ejecutar la macro:

    * Quito las columnas que no tienen datos y que se doblan por la exportación de los encabezados y dejo la tabla colocada en la celda A1 (la fila de resultados totales final también la quito). La primera columna y la última también
    * Creo una nueva hoja llamada Resultados y a la hoja donde están los datos la renombro a Hoja1
    * Ejecuto la macro

