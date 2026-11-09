# Inventario de mi red doméstica con Nmap

## Objetivo
Quería saber cuántos dispositivos estaban conectados a mi red y comprobar que no hubiera nadie conectado desde afuera. Usé Nmap desde Windows.

## Comandos
- `ipconfig`: mostró mi IP (10.0.0.7), mi máscara (255.255.255.0) y mi router (10.0.0.1).
- `nmap -sn 10.0.0.0/24`: escaneo suave de las 256 direcciones de mi red, sin revisar puertos.

## Resultados
Salieron 7 dispositivos activos:
- `10.0.0.1`: router Huawei
- `10.0.0.7`: mi laptop
- `10.0.0.10` y `10.0.0.19`: AzureWave (TV y PlayStation, encendidas porque estaba jugando)
- `10.0.0.3`, `10.0.0.9` y `10.0.0.18`: Unknown (probablemente celulares con MAC aleatoria)

## Comparación
Tengo 7 aparatos en casa: 3 teléfonos, TV, PlayStation y 2 laptops. Confirmé mi celular apagando su Wi-Fi y repitiendo el escaneo: era uno de los Unknown, no un AzureWave. Ningún dispositivo sobraba. Faltó una laptop, seguramente apagada.

## Lo que aprendí
- Un punto de más (`10.0.0.0./24`) hace fallar el comando.
- Unknown no es peligroso: los celulares usan MAC aleatoria por privacidad.
- Nmap muestra quién está conectado, no cuánto consume.

## Limitación
Este escaneo solo muestra los aparatos que responden en ese momento. Uno apagado o dormido no sale.

## Siguiente paso
Medir el consumo por dispositivo con Sniffnet o el panel del router.