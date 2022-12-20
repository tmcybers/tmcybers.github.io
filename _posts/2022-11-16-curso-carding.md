---
title: Curso de Carding
layout: post
post-image: /assets/images/bannergit.png
description: Carding
tags:
- Hacking
- Cybersecurity
- Carding
---

## Disclamer: 
`NO asumo ninguna responsabilidad debida al mal empleo de la información aquí contenida, puesto que este texto solamente tiene fines educativos y en ningún caso pretende incitar a nadie a cometer ningún delito ya sea informático o de otra índole`

#### Introducción

`En este curso voy a indicar que es el carding? Algunos términos del mismo como utilizarlo y sacar provecho 🙂`

### Comencemos…!

## Carding
```
Este es un concepto que indica lo más claramente posible que es y de que se trata el carding.
```

`Carding: Es el uso ilegitimo de las tarjetas de crédito, o de sus números, pertenecientes a otras personas. Se relaciona con el hacking, porque para conseguir números de tarjetas de créditos, una de las formas es utilizando Ingenieria Social y sobre todo nuestra inteligencia (esto es lo mas importante)`

---
* Se debe tener mucho cuidado en hacer esto ya que nos podemos meter en muchos líos.
* Con nuestras tarjetas de crédito debemos ser cuidadosos ya que alguien puede leer este documento antes que uno de ustedes y ser capaz de estafarlos.
* Se puede recuperar el dinero talvez pero para eso tendrían que hablar con el administrador del sitio donde se realizo el pago del artículo solicitando la IP de donde se hizo la compra y luego de todo esto tenemos que demostrar que nosotros no hicimos la compra del mismo.
---

---
* Los números de las tarjetas se forman de 16 dígitos divididos en 4 grupos de 4 dígitos pueden tener valores del 0 al 9 los primeros 4 dígitos sirven para determinar el banco.

* El resto de números se pone al azar no mentira vamos a ver el algoritmo.

* Hagamos un ejemplo de la creación de un número de tarjeta.

#### Numero de tarjeta: 5180 2345 3942 8765

##### Las posiciones impares son:
```
5
8
2
4
3
4
8
6
```
##### Luego de esto se multiplica los 2 primeros dígitos entre si luego los siguientes y asi sucesivamente para que sea mas claro quedaría de la siguiente forma:
```
5*8=40
2*4=8
3*4=12
8*6=48
```
##### Si tenemos cifras mayores a 9 se suma los números es decir las cifras reducidas 8+5=13 entonces
```
1+3=4
```
##### En el ejemplo quedaría asi:
```
5*8=40 4+0=4
2*4=8 8
3*4=12 1+2=3
8*6=48 4+8=12 1+2=3
```
##### En resumen los números que nos quedan son:
```
4
8
3
3
```
##### Luego de esto suma los números pares que descartamos al principio y súmalos con estos el resultado debe ser un número múltiplo de 10 para que el número sea correcto:
```
4+8+3+3+1+0+3+5+9+2+7+5=50
```
##### Si no nos diera un numero correcto como va a suceder en la mayoría de los casos lo recomendable es dejar el ultimo casillero libre y jugar con este digito hasta que nos de un numero valido.

##### Esta es una de las formas de conseguir un numero de tarjeta de crédito es decir adivinando a ver si nos sale otra puede ser esperar pacientemente el fin de mes el momento que llega el corte de pago de la tarjeta del vecino nos robamos su correspondencia y listo ahí tenemos un numerito.

#### Si el primer numero es….
```
3 ->American Express (15 dígitos)
4 ->VISA (13 o 16 dígitos)
5 ->Mastercard (16 dígitos)
6 ->Discover (16 dígitos)
```

#### Con estos datos ya se puede comprar algo en línea generalmente los carders realizan una compra de algún software pequeño que sea de descarga o una subscripción para ver pornografía esto lo hacen para probar si la tarjeta funciona o no .

#### Si el momento de la compra nos solicitaran mas datos ya saben que hacer es mas creo que al momento de revisar su correo no tendrán estos datos tendrán muchos mas.

#### Hagan un repaso de lo que aprendieron hasta aquí y piensen en una posible victima hasta mientras me voy hacer un cafe…….y a estudiar.!

##### Aqui te dejo un ejemplo de como un carder hace uso de una tarjeta (datos ficticios y no reales):
```
[Card Information]━━
• Card: 4892720002175670|10|2026|391
• Status: Approved! ✅
• Response: Decline CVV2/CID Fail
• Gateway: Hades
━━━━━━━━━━━━
Bin Information
• Bin: 489272
• Bank: BENCHMARK COMMUNITY BANK
• Country: UNITED STATES – 🇺🇸
• BinType: DEBIT-VISA-CLASSIC
━━━━━━━━━━━━
• Proxy: 154.xxxx11 – United States 🌎
• Status: Live! ✅
• Retries: 1
━━━━━━━━━━━━
```
---
>>>> Un Saludo cordial [Menciono y no me hago responsable del mal uso de esta informacion aqui descrita]
---

{% include share-buttons.html %}
