---
title: "De 0 a root: Los cimientos técnicos y el roadmap antes de romper nada"
date: 2026-05-13
draft: false
tags: ["iniciación", "roadmap", "pentesting", "redes", "fundamentos"]
---

El cine ha hecho mucho daño a nuestra profesión. Empezar en ciberseguridad no va de ponerse una capucha, abrir una terminal en verde y teclear a la velocidad de la luz para entrar en un servidor en 30 segundos. A veces nos obsesionamos con ver tutoriales donde la gente revienta máquinas en diez minutos y nos creemos que el *pentesting* es tirar dos herramientas mágicas y a correr. 

La realidad es pura filosofía de ensayo, error y, sobre todo, de tener una base técnica brutal. Joe, qué movida es enfrentarse a esa pantalla negra por primera vez y darte cuenta de que, si no entiendes los cimientos, estás completamente ciego. Si estás pensando en dar el salto a este sector, te aviso ya: vas a dar bandazos. Un follón de conceptos cruzados que flipas. Pero no pasa nada, sigue. Lo que no entiendes ahora, te prometo que hará clic más adelante.

Para no perderte en ese abismo, necesitas cimentar estos tres pilares innegociables antes de intentar atacar:

### 1. Redes: El idioma de las máquinas
No puedes explotar un servicio si no sabes cómo se comunica. Yo me acuerdo perfectamente de cuando arranqué. Escribí mi primer `nmap -sV -sC -p-` contra una IP y me quedé mirando la salida. Ni dea de lo que estaba haciendo realmente. Veía puertos y servicios, pero me faltaba el contexto. 

Antes de atacar, tienes que entender el modelo OSI y el TCP/IP. Necesitas saber la diferencia entre un paquete TCP y uno UDP, cómo funciona el *Three-way handshake*, el enrutamiento y los *firewalls*. Si un escaneo te devuelve que el puerto 445 está abierto, tu cerebro tiene que pensar automáticamente en SMB y vulnerabilidades de Windows. Si no dominas la red, el tráfico te parecerá ruido blanco.

### 2. Sistemas Operativos: Tu terreno de juego
Olvídate del ratón. El 99% de las auditorías y servidores que atacarás corren bajo Linux. La consola tiene que ser tu hábitat natural, y no me vale con saber hacer un `ls` o un `cat`. 

* **En Linux:** Tienes que dominar la jerarquía del sistema de archivos, cómo funcionan los permisos (los famosos SUID y SGID son la puerta a escalar privilegios), cómo se gestionan los procesos y las variables de entorno. 
* **En Windows:** Tienes que perderle el miedo a PowerShell, entender el Registro, los privilegios de los usuarios y, el jefe final: Active Directory. 

Cuando consigues acceso inicial a una máquina, entras como un usuario raso. Si no sabes leer el sistema para encontrar dónde dejaron una contraseña tirada o un binario mal configurado, te vas a quedar ahí estancado.

### 3. Scripting y Programación: Automatiza o muere
No necesitas ser un desarrollador Senior, pero tienes que saber leer código. Muchas veces te vas a encontrar con *exploits* públicos en GitHub que no van a funcionar a la primera. Vas a tener que abrirlos, entender qué hacen, cambiar el *payload* y arreglar problemas de compatibilidad.

Saber armar *scripts* rápidos en Bash te salvará la vida para automatizar tareas, y dominar lo básico de Python te permitirá crear tus propias herramientas. Ver un bloque de código y decir "ni dea de qué es esto" te dejará fuera de juego. Si quieres sobrevivir en la terminal, tienes que aprender a automatizar lo aburrido.

---

## El Roadmap Práctico: Por dónde avanzar

Una vez tienes la teoría, toca mancharse las manos de forma legal y segura. Sigue este orden para no frustrarte:

1. **Nivel 1 - Entornos Guiados (TryHackMe):** Es la mejor plataforma para empezar. Las salas te llevan de la mano explicando la vulnerabilidad antes de pedirte que la explotes. Empieza por la ruta *Jr Penetration Tester*.
2. **Nivel 2 - La jaula de los leones (HackTheBox & VulnHub):** Aquí se quitan las ruedas de entrenamiento. Te dan una IP y búscate la vida. En esta fase aprenderás a lidiar con las famosas "conejeras" (*rabbit holes*): pistas falsas que te harán perder horas. 
3. **Nivel 3 - Laboratorio Propio y CTFs:** Monta tu propio ecosistema con VMware o VirtualBox. Instala máquinas intencionadamente vulnerables (*Metasploitable*, *DVWA*) y apúntate a competiciones CTF de fin de semana para medirte con otros jugadores.

## El muro mental
Aún dominando todo esto, llegará un momento en el que el túnel inverso se caiga, el *exploit* que funcionaba en el manual no compile, o no encuentres la puñetera vía para escalar a *root*. Te vas a frustrar, el sistema te va a escupir un `Connection Refused` en rojo brillante y pensarás en dejarlo. 

Ahí es cuando tienes que respirar frente al teclado, tirar de cabezonería y decirte: "venga, esto no puede contigo". 

Vuelves a enumerar, revisas la estructura de red, te lees un código línea a línea, ajustas el tiro y de repente... la terminal se queda colgada un segundo, y recibes la *shell* interactiva. ¡VAMOS! Ese momento en el que consigues saltar a otro usuario o ves el `#` del *root*, te la gozas. Todo el dolor de cabeza anterior desaparece de golpe.

Romper tu primera máquina no va de ser el que más herramientas de Kali conoce, va de entender la tecnología base y ser el que más aguanta la frustración probando vías nuevas. Documenta todo lo que aprendas (Obsidian es fantástico para esto) y ten paciencia. Todo esfuerzo acaba dando sus frutos.

A seguir picando piedra en la terminal. ¡Mucho ánimo con esos laboratorios y a darle caña!