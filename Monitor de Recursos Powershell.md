# Scripts
Monitor de Recursos 💻

Un script muy ligero y sencillo , esta mas o menoos bonito.

```powershell

Write-Host " MONITOR DE RECURSOS " 

$cpu = Get-Counter -Counter "\Procesador(_Total)\% de tiempo de procesador"
$usoCPU = [math]::Round($cpu.CounterSamples.CookedValue, 2)
Write-Host "  CPU en uso:        $usoCPU %"

$ram = Get-Counter -Counter "\Memoria\Mbytes disponibles"
$ramLibre = $ram.CounterSamples.CookedValue
Write-Host "  RAM Disponible:    $ramLibre MB"

$disco = Get-Counter -Counter "\Disco lógico(C:)\Longitud promedio de la cola de disco"
$colaDisco = [math]::Round($disco.CounterSamples.CookedValue, 2)
Write-Host "  Cola de Disco (C:): $colaDisco"

$temp = Get-CimInstance -Namespace "root/wmi" -ClassName MSAcpi_ThermalZoneTemperature
$textoTemp = "$([math]::Round(($temp.CurrentTemperature / 10) - 273.15, 1)) °C"
Write-Host "  Temperatura CPU: $textoTemp"´´´

