---
title: "De 0 a root: Cómo iniciarte en el mundo del hacking sin perder la cabeza"
date: 2026-05-12
draft: false
tags: ["Iniciación", "Roadmap", "Fundamentos"]
---

El cine ha hecho mucho daño a nuestra profesión. Empezar en ciberseguridad no va de ponerse una capucha, abrir una terminal en verde y teclear a la velocidad de la luz para entrar en un servidor en 30 segundos. 

El *pentesting* real es metodología, frustración, lectura de documentación y, sobre todo, entender profundamente cómo funcionan las cosas antes de intentar romperlas. Si estás pensando en dar el salto a este sector, aquí tienes la hoja de ruta que me hubiera gustado leer a mí.

## Los cimientos: Qué debes dominar antes de atacar

No puedes explotar un servicio si no sabes cómo se comunica. Antes de tocar herramientas ofensivas como Metasploit o Burp Suite, necesitas una base sólida de infraestructura:

1. **Redes (El idioma de los equipos):** Debes conocer al dedillo el modelo OSI, el protocolo TCP/IP, cómo funciona el enrutamiento y qué son los puertos. Si no sabes la diferencia entre UDP y TCP, aún no es el momento de hackear.
2. **Administración Linux:** Olvídate del ratón. El 99% de las auditorías y servidores que atacarás corren bajo Linux. Tienes que moverte por la terminal de Kali, Parrot o Ubuntu con total fluidez.
3. **Scripting básico:** No necesitas ser desarrollador de software, pero debes saber leer y automatizar tareas. Python y Bash son tus mejores amigos.

```bash
# Un buen hacker automatiza lo aburrido. 
# Ejemplo de un script rápido en Bash para descubrir equipos vivos en tu red local:
for ip in $(seq 1 254); do ping -c 1 192.168.1.$ip | grep "bytes from" | cut -d " " -f 4 | tr -d ":" & done
```

## El Roadmap Práctico: Por dónde avanzar

Una vez tienes la teoría, toca mancharse las manos de forma legal y segura. Sigue este orden para no frustrarte:

### Nivel 1: Entornos Guiados (TryHackMe)
Es la mejor plataforma para empezar. Las salas (Rooms) te llevan de la mano explicando la vulnerabilidad antes de pedirte que la explotes. Empieza por rutas como el *Jr Penetration Tester*. Te dará la confianza inicial que necesitas.

### Nivel 2: La jaula de los leones (HackTheBox & VulnHub)
Aquí se quitan las ruedas de entrenamiento. Te dan una IP y te dicen: "Consigue acceso de administrador". En esta fase aprenderás a lidiar con las famosas "conejeras" (*rabbit holes*): pistas falsas que te harán perder horas. 

### Nivel 3: Laboratorio Propio y CTFs (Capture The Flag)
Monta tu propio ecosistema con VMware o VirtualBox. Instala máquinas intencionadamente vulnerables como *Metasploitable* o *DVWA* (Damn Vulnerable Web App). Paralelamente, apúntate a competiciones CTF de fin de semana para medirte con otros jugadores.

## La Cara Oculta: La gestión de la frustración

La habilidad más importante de un auditor de ciberseguridad no es técnica, es psicológica. Pasarás horas frente a un error `Connection Refused` o un *exploit* que funciona en el manual pero no en tu máquina. 

En esta profesión nunca se deja de estudiar. La tecnología cambia cada día, y lo que hoy es seguro, mañana será el vector de entrada de un ransomware. Documenta todo lo que aprendas ( Obsidian es una herramienta fantástica para esto), construye tu propio repositorio de comandos y, sobre todo, ten paciencia. El acceso como `root` siempre acaba llegando.