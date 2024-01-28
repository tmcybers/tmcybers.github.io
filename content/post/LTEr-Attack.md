+++
title = 'LTEr Attack'
author = 'tmcyb3r'
date = 2024-01-28T19:12:11+01:00
description = 'LTEr Attack'
draft = false
tags = [
    'GrapheneOS',
    'privacy',
    'encryption'
]
+++

# Ataques de integridad LTE y 5G (Hardened) Method [Advanced] 🥊

> LTEr attack (Pegasus NSO, GOB Attack Vector) 🪬

+ 4G son las redes celulares de evolución a largo plazo (LTE).
+ 5G se encuentra en una fase avanzada aun a dia de hoy.

> Aspectos y parches de seguridad de las redes 4G se aplicaron a las redes 5G.


### De que va todo esto ? 🥊

Uno de los problemas de seguridad específicos de 4G y 5G, es que manejan cuidadosamente definir el proceso de identificación mutua, que fue diseñado para ser resistente a ataques: la identidad del dispositivo es verificada por la red y la identidad de la red es verificada por el dispositivo.

La garantía de la identidad del dispositivo es crucial para que la red facture al usuario ;) $$$$ por los servicios consumidos y también es importante para asegurar la responsabilidad legal del usuario al utilizar diversos servicios :)

La verificación de la identidad de la red desde la perspectiva del dispositivo es esencial en la protección contra ataques de tipo Man-in-the-Middle (MitM).

El proceso de verificación implementado en 4G y 5G se denomina AKA – Autenticación y Acuerdo de Clave.


>>> Metodologia de superficie de ataque: agencias de espionaje, asi como NSO (Pegasus y variantes), NSA, CIA, GOB 🥊

Se implementa utilizando un eNodeB falso (la torre celular 4G), que actúa como Man-in-The-Middle (MiTM): se persigue al Equipo de Usuario (UE) atacado para que se conecte a la red a través de este equipo, actuando como un relé malicioso. ...;). "un ataque LTEr".

### Un poco dificil de entender ? Te explico 🪄

El atacante, al tener acceso a la comunicación cifrada del UE objetivo, aprovecha el hecho de que no hay protección de integridad en este canal y manipula (o altera...) esa información transmitida para que la comunicación real que llega al destino. 
Dado que la manipulación se realiza en el canal cifrado, el atacante tiene que alterar la comunicación de tal manera que se produzca el contenido deseado después del descifrado.

El objetivo del ataque es realizar lo que se conoce como suplantación de DNS. Los servidores de nombres de dominio (DNS) son los elementos de la red de Internet que se encargan de convertir las direcciones de Internet textuales (URL) en direcciones IP numéricas.

Puede alterar la dirección IP de la consulta DNS emitida por el UE objetivo para que la solicitud DNS se enrute a un servidor DNS malicioso operado por el atacante ;)

Un ataque de este tipo podría ser muy eficaz, superando las capacidades de seguridad básicas de LTE y 5G, aprovechando el hecho de que no se incluyó ninguna protección de integridad.

##  La Medicina ;) 🏆

 LTE Discovery app data (f...ck you NSO) 

>> https://lnkd.in/dRA2TJBt 

La llevo usando en mi Tanque Ruso GOS desde hace mas de 1 año, me sirve en que banda estoy, el app data, lo que recibo, lo que envio, antenas en donde me comunico, y muchismo mas ;)

>>>>> (Hardended Method) necesitas fundamentos para entenderla.

CyberS3C for Humans
