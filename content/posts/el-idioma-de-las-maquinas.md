---
title: "El idioma de las máquinas: Qué necesitas saber de redes antes de lanzar un nmap"
date: 2026-05-15
tags: ["redes", "pentesting", "fundamentos", "iniciación"]
---

En el artículo de cero a root(/posts/de-cero-a-root/) comentamos que tirar comandos a ciegas es el peor error que puedes cometer. Hoy vamos a hacer un *zoom* al primer pilar innegociable: las redes. 

A veces nos creemos que esto de la ciberseguridad es solo buscar vulnerabilidades en código, pero la realidad es que si no entiendes cómo viaja la información de un punto A a un punto B, estás muerto antes de empezar. Joe, qué movida es abrir Wireshark por primera vez y ver miles de líneas de colores moviéndose a toda leche. Al principio piensas: "ni dea de lo que estoy mirando, qué follón". Pero dominar esto es lo que separa a un *script kiddie* de un analista de verdad.

Aquí tienes la sabiduría de redes que necesitas tatuarte a fuego en la cabeza:

### 1. El TCP/IP y el famoso Handshake
No te hablo de chaparte la teoría aburrida del modelo OSI para aprobar un examen, te hablo de supervivencia en la terminal. Tienes que saber diferenciar cómo habla TCP y cómo lo hace UDP. 
* **TCP es el educado:** Hace el *Three-way handshake* (SYN, SYN-ACK, ACK). Si lanzas un escaneo de puertos TCP, Nmap espera respuesta.
* **UDP es el salvaje:** Tira el paquete y se olvida. Muchas veces lanzamos un escaneo UDP masivo, vemos que tarda horas y pensamos que el escáner se ha roto. No, es que UDP funciona así de mal para escanear. Saber esto te ahorra horas de dar bandazos.

### 2. Los puertos son puertas, los servicios son los porteros
Ver que el puerto 80 (HTTP) o el 443 (HTTPS) están abiertos no tiene mucho misterio. Pero cuando lanzas Nmap y ves el 445 o el 139, tu cerebro tiene que hacer clic al instante: SMB (Server Message Block). El coladero por excelencia de las redes Windows. 
Yo me acuerdo de ver un puerto 53 abierto y no saber qué hacer con él. Cuando entiendes que es un DNS, sabes que puedes intentar una transferencia de zona. Si no sabes qué servicio corre por defecto en cada puerto, te vas a saltar la puerta de entrada a la máquina.

### 3. Subnetting y la magia de Pivotar
Imagina que logras explotar un servidor web. Entras, tienes tu *shell*, te la gozas. Haces un `ip a` o un `ifconfig` y ves que esa máquina tiene dos tarjetas de red: una que da a Internet y otra apuntando a una red interna `10.10.x.x /24`. Un follón que flipas.
Si no entiendes de máscaras de subred y enrutamiento, tu auditoría termina ahí. Si dominas las redes, sabes que puedes usar esa máquina comprometida como puente (pivotar) para atacar a los equipos internos que ni siquiera tienen conexión a Internet. 

### 4. El dolor de los Firewalls y el NAT
Llega el momento de la verdad. Has encontrado la vulnerabilidad, configuras tu *exploit* para que te devuelva una *Reverse Shell* al puerto 4444 de tu Kali, lo lanzas y... nada. Silencio. Te pasas horas revisando el código, frustrado perdido. 

Te paras, respiras y dices: "venga, esto no puede contigo". 

Te pones el gorro de analista de redes y te das cuenta: ¡claro, el *firewall* de la empresa bloquea todo el tráfico saliente hacia puertos raros! ¿Qué haces? Levantas tu *listener* en el puerto 443 (HTTPS) o 53 (DNS) porque esos puertos casi siempre están permitidos para salir a Internet. Vuelves a lanzar el *exploit* por el 443, la terminal parpadea y... ¡VAMOS! Consigues la conexión. 

Ese subidón de dopamina cuando un concepto de redes puro y duro te salva la vida, es brutal. Y lo mejor es que lo que hoy te parece chino, con esfuerzo y dándote cabezazos contra el teclado, mañana será tu segunda naturaleza.

Si quieres romper cosas, primero aprende cómo están conectadas. A seguir picando piedra, ¡mucho ánimo y a darle caña a la consola!