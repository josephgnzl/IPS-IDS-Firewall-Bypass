## 01. Source Port Manipulation 
Los firewalls mal configurados asumen que el tráfico proveniente de puertos como el 53 (DNS) o el 88 (Kerberos) es legítimo y lo dejan pasar sin inspección profunda.

### Comando Nmap  
```bash
sudo nmap -sS -p- --source-port 53 -Pn -T4 10.129.224.220
```
-Pn evita el ping inicial (que suele ser bloqueado) y escanea los 65,535 puertos.

## 02. Fragmentación Extrema (Evasión de IDS por firma)

Si el firewall inspecciona el payload, dividir el paquete en fragmentos de 8 bytes (el mínimo posible en IP) impide que el IDS reconstruya la firma maliciosa.

### Comando Nmap 
```bash
sudo nmap -sS -f --mtu 8 -p 1-65535 -Pn 10.129.224.220
```
```-f:``` Fragmenta los paquetes.

```--mtu``` 8: Fuerza el tamaño máximo de unidad de transmisión a 8 bytes (muy agresivo, algunos IDS se saturan o ignoran estos fragmentos).

## 03. Nmap Idle Scan (Sigilo Absoluto)
El escaneo IDLE permite escanear un objetivo sin enviar ni un solo paquete desde tu IP. Utiliza una máquina "zombie" intermedia con poco tráfico para inferir los puertos abiertos.

### Comando Nmap  
```bash
sudo nmap -sI <IP_Zombie> -Pn -p- 10.129.224.220
```
```Requisito:``` Necesitas encontrar una máquina "zombie" con un IP ID predecible (global).

```Ventaja:``` Es indetectable desde la perspectiva de la IP origen, porque los paquetes provienen de la IP Zombie.

## Opinión Personal 

Todo depende del contexto al que te enfrentes para utilizar estos comandos, pero casi siempre la taza de éxito con los mismos es muy alta, ya luego hablaré sobre pivoting, otro nivel de enumeración desde dentro de la red.

### h4ck the planet 

josephgnzl-
