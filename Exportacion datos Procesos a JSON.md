# Reporte de Procesos en Formato JSON

Este script de PowerShell permite obtener información específica de procesos en ejecución y exportarlos a un archivo estructurado para su posterior análisis.

## Código PowerShell

```powershell
Get-Process -Name "notepad", "PON_PROCESO_AQUI" | 
    Select-Object Name, Id, CPU, StartTime | 
    ConvertTo-Json -Depth 2 | 
    Out-File "C:\RUTA\DE\TU\ARCHIVO\Procesos.json"
```



