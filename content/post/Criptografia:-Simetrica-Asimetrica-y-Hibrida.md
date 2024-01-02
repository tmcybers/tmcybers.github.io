+++
title = 'Criptografia:Simetrica, Asimetrica y Hibrida'
date = 2023-12-31T12:24:23+01:00
draft = false
+++

# Criptografía simétrica

La criptografía simétrica solo utiliza una clave para cifrar y descifrar el mensaje, que tiene que conocer el emisor y el receptor previamente y este es el punto débil del sistema, la comunicación de las claves entre ambos sujetos, ya que resulta más fácil interceptar una clave que se ha transmitido sin seguridad (diciéndola en alto, mandándola por correo electrónico u ordinario o haciendo una llamada telefónica).

![Simetrica](/simetrica.png)

Teóricamente debería de ser más fácil conocer la clave interceptándola que probándola una por una por fuerza bruta, teniendo en cuenta que la seguridad de un mensaje cifrado debe recaer sobre la clave y nunca sobre el algoritmo (por lo que sería una tarea eterna reventar la clave, como comenté en un ejemplo de ataque por fuerza bruta).

El inconveniente que tiene este sistema es que si quieres tener un contenido totalmente confidencial con 10 personas tienes que aprenderte o apuntarte (siendo esta forma menos segura) las 10 claves para cada persona.


# Criptografía asimétrica

La criptografía asimétrica se basa en el uso de dos claves: la pública (que se podrá difundir sin ningún problema a todas las personas que necesiten mandarte algo cifrado) y la privada (que no debe de ser revelada nunca).

![Simetrica](/asimetrica.png)

Sabiendo lo anterior, si queremos que tres compañeros de trabajo nos manden un archivo cifrado debemos de mandarle nuestra clave pública (que está vinculada a la privada) y nos podrán mandar de forma confidencial ese archivo que solo nosotros podremos descifrar con la clave privada.

Puede parecer a simple vista un sistema un poco cojo ya que podríamos pensar que sabiendo la clave pública podríamos deducir la privada, pero este tipo de sistemas criptográficos usa algoritmos bastante complejos que generan a partir de la frase de paso (la contraseña) la clave privada y pública que pueden tener perfectamente un tamaño de 2048bits (probablemente imposible de reventar).

Como os habréis dado cuenta solo cifra una persona (con la clave pública) y la otra se limita a mirar el contenido, por lo que la forma correcta de tener una comunicación bidireccional sería realizando este mismo proceso con dos pares de claves, o una por cada comunicador.

Otro propósito de este sistema es también el de poder firmar documentos, certificando que el emisor es quien dice ser, firmando con la clave privada y verificando la identidad con la pública.

Nota: todo esto puede parecer lioso (y lo es) pero hablaré de como poner en práctica esto con GnuPG (una herramienta de cifrado libre muy usada para este propósito) y será más fácil de comprender.

### Diferencias entre criptografía simétrica y asimétrica:

Para empezar, la criptografía simétrica es más insegura ya que el hecho de pasar la clave es una gran vulnerabilidad, pero se puede cifrar y descifrar en menor tiempo del que tarda la criptografía asimétrica, que es el principal inconveniente y es la razón por la que existe la criptografía híbrida.

# Criptografía híbrida

Este sistema es la unión de las ventajas de los dos anteriores, debemos de partir que el problema de ambos sistemas criptográficos es que el simétrico es inseguro y el asimétrico es lento.

![Simetrica](/hibrida.png)

El proceso para usar un sistema criptográfico híbrido es el siguiente (para enviar un archivo):

* Generar una clave pública y otra privada (en el receptor).

* Cifrar un archivo de forma síncrona.

* El receptor nos envía su clave pública.

* Ciframos la clave que hemos usado para encriptar el archivo con la clave pública del receptor.

* Enviamos el archivo cifrado (síncronamente) y la clave del archivo cifrada (asíncronamente y solo puede ver el receptor).

## Resumiendo:

Estos son los métodos criptográficos modernos que usamos comúnmente, aunque las aplicaciones nos abstraigan de todo esto, pero podemos hacerlo de forma manual si se diera el caso de que necesitamos mandar ciertos contenidos y queremos que tengan la confidencialidad adecuada.

tmcyb3r