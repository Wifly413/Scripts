# Reporte de Procesos en Formato JSON

Este script de PowerShell permite obtener información específica de procesos en ejecución y exportarlos a un archivo estructurado para su posterior análisis.

## Código PowerShell

Para probarlo, asegúrate de abrir un proceso de Windows y un bloc de notas vacío antes de ejecutar el código, así PowerShell encontrará los procesos y los guardará en el archivo de tu escritorio.

```powershell
Get-Process -Name "notepad", "PON_PROCESO_AQUI" | 
    Select-Object Name, Id, CPU, StartTime | 
    ConvertTo-Json -Depth 2 | 
    Out-File "C:\RUTA\DE\TU\ARCHIVO\Procesos.json"
```



