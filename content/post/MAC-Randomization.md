+++
title = 'MAC Randomization'
author = 'tmcyb3r'
date = 2024-01-28T19:30:14+01:00
description = 'MAC Randomization'
draft = false
tags = [
    'GrapheneOS',
    'privacy',
    'encryption',
    'fossfreedom'
]
+++

# Extreme Proteccion 

Como muchos de vosotros saben, las direcciones MAC son identificadores “grabados” unicos, chips de radio que les dan lo que se supone que es una dirección mundial única. 

El chip utiliza la dirección MAC para las comunicaciones de red, que, de forma inalámbrica, se envían por aire para que todos las vean. 

Debido a esa singularidad, la dirección MAC históricamente representaba el chip en sí, el dispositivo con el chip instalado y el usuario que lo transporta. 

Por lo tanto, las direcciones MAC son una especie de campo de batalla para la privacidad de los datos personales.

> Hoy es tu dia de suerte;;;

Muchos de vosotros teneis un feature tan importante en vuestros moviles, pero seguro que desconoceis? 

Y es normal, porque esta escondido debajo de una capa que se llama = Developer Options, cosa que no te recomiendo nunca tocar si no sabes lo que haces :) 

Por seguridad mantener la apagada siempre que se puede ;)


>>>> What the f.....ck is mac randomization? 


### No te lies, yo te lo explico:

La aleatorización de MAC es un proceso que oculta la identidad exacta de un dispositivo móvil mediante la creación de una dirección MAC artificial en su lugar, que luego se transmite a cualquier punto de acceso WiFi.

En los dispositivos Android, la aleatorización de MAC no persistente está activa a dia de hoy, estas de suerte, lo que genera una nueva dirección MAC aleatoria para cada Wifi, que solo persiste a menos que te desconectes de la red Wifi. 

Si te vuelves a conectar a un Wifi conocida, se genera una nueva dirección MAC ;)

Apple tambien dio el gran paso en sus cacharos manzana.

Apple ha informado a los fabricantes de Wi-Fi que los escaneos de Wi-Fi de iOS y iPadOS utilizan una dirección MAC aleatoria, y ni Apple ni los fabricantes pueden predecir estas direcciones MAC aleatorias. 

Un gran paso, en contra del espionaje de operadores y aplicaciones.

Esto es solo un pequeño avance, no te protegera, pero es una capa muy pequeña hacia la privacidad : ) el derecho fundamental de todo ser humano.

>>> CybeS3C for Humans (Hardened)

