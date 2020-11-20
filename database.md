# Descripción de las entidades

## Autor 
- Diego Avila Morales

## Índice
- [Descripción de las entidades](#descripción-de-las-entidades)
  - [Autor](#autor)
  - [Índice](#índice)
  - [Diccionario de la base de datos](#diccionario-de-la-base-de-datos)
  - [Tablas](#tablas)
    - [users](#users)
    - [roles](#roles)
    - [videos](#videos)
    - [videos_clasifications](#videos_clasifications)
    - [tags](#tags)
    - [user_ratings](#user_ratings)
    - [user_recommendations](#user_recommendations)
  - [APÉNDICE A](#apéndice-a)
    - [TIPOS DE DATOS](#tipos-de-datos)


## Diccionario de la base de datos

Ciertas convenciones fueron seguidas en este documento.
- Todos los nombres de las tablas se encuentran remarcados con negrita.
- Todos los nombres de columna se encuentran remarcados en cursiva
- Los siguientes valores se encuentran en la columna de índicee de las tablas de este informe:
  - Índex: Todos los nombres de la columna en una tabla con este valor se indexan juntos para crear el índice primario en la tabla.
  - Unisque index: Todos los nombres de columna en una tabla con este valor se indexan juntos para crear un índice primario único en la tabla.
  - *La combinación de valores en este índice no se puede duplicar en ninguna parte de la tabla*


---

## Tablas

---

### users

- Nombre de la tabla- **users**
- Descripción: Almacena datos relevantes de los usuarios del sistema.


| Nombre de la columna | Tipo | Nombre descriptivo | Rangos válidos de valores | Permite valores nulos | Índices de la columna | Descripción |
--- | --- | --- | --- |--- | --- |  ---
| ***id*** | integer(10) | Clave del usuario | | No | Unique Index | Este campo es la clave única de cada usuario |
| *name* | varchar(50) | Nombre del usuario | | No | | Este campo es el nombre de cada usuario |
| *email* | varchar(100) | Correo electrónico | *.@*.* | No | | Este campo representa el correo de cada usuario |
| *password* | varchar(20) | Contraseña del usuario | | No | | Este campo representa la contraseña de cada usuario |
| **role** | integer(10) | Clave del rol | | No | | Este campo es la clave única del rol del usuario. Hace referencia a la tabla **roles**. |
| *created_at* | timestamp | Fecha de creación | | No | | Este campo se llena automáticamente por parte de la base de datos. Es usado para identificar el día en que se creó el registro |
| *updated_at* | timestamp | Fecha de actualización | | No | | Este campo se llena automáticamente por parte de la base de datos. Es usado para identificar la fecha en que se actualizó el registro |

---

### roles

- Nombre de la tabla- **roles**
- Descripción: Tabla que almacena los datos referentes a los roles que pueden tener los usuarios en el sistema.

---

| Nombre de la columna | Tipo | Nombre descriptivo | Rangos válidos de valores | Permite valores nulos | Índices de la columna | Descripción |
--- | --- | --- | --- |--- | --- |  ---
| ***id_role*** | integer(10) | Clave del role | | No | Unique Index | Este campo es la clave única de los roles en el sistema |
| *name* | varchar(50) | Nombre del rol | Admin, User | No | | Este campo representa el nombre del rol |

---

### videos

- Nombre de la tabla- **videos**
- Descripción: Tabla que almacena los datos relacionados a los videos almacenados dentro del sistema.

---

| Nombre de la columna | Tipo | Nombre descriptivo | Rangos válidos de valores | Permite valores nulos | Índices de la columna | Descripción |
--- | --- | --- | --- |--- | --- |  ---
| ***id_video*** | integer(10) | Clave del video | | No | Unique Index | Este campo es la clave única del video |
| *titulo* | varchar(100) | titulo del video | | No | | Este campo es el título asociado al video |
| ***autor*** | integer(10) | Autor del video | | No | | Este campo representa el usuario autor del video. Hace referencia a la tabla **users** |
| *average_score* | float | Puntaje promedio | | Si | | Este campo es el puntaje promedio del video |
| *created_at* | timestamp | Fecha de creación | | No | | Este campo se llena automáticamente por parte de la base de datos. Es usado para identificar el día en que se creó el registro |
| *video_location* | text | Ubicación del video | | No | | Este campo guarda la URL que hace referencia al video almacenado |

---

### videos_clasifications

- Nombre de la tabla- **videos_clasifications**
- Descripción: Tabla que almacena la relación de los videos y su clasificación.

---

| Nombre de la columna | Tipo | Nombre descriptivo | Rangos válidos de valores | Permite valores nulos | Índices de la columna | Descripción |
--- | --- | --- | --- |--- | --- |  ---
| ***id_tag*** | integer(10) | Clave de la etiqueta | | No | Index | Este campo es la clave única de la etiqueta del video. Hace referencia a la tabla de **tags**|
| ***id_video*** | integer(10) | Clave del video | | No | Index | Este campo es la clave única del video. Hace referencia a la tabla de **videos** |

---

### tags

- Nombre de la tabla- **tags**
- Descripción: Tabla que almacena los datos de las etiquetas de los videos.

---

| Nombre de la columna | Tipo | Nombre descriptivo | Rangos válidos de valores | Permite valores nulos | Índices de la columna | Descripción |
--- | --- | --- | --- |--- | --- |  ---
| ***id_tag*** | integer(10) | Clave de la etiqueta | | No | Unique Index | Este campo es la clave única de la etiqueta del video. |
| *name* | varchar(50) | Nombre de la etiqueta | | No | | Este campo es el nombre asociado a la etiqueta |

---

### user_ratings

- Nombre de la tabla- **user_ratings**
- Descripción: Tabla que almacena los videos en los cuales los usuarios les asignó una calificación y el valor de la calificación otorgada.

---

| Nombre de la columna | Tipo | Nombre descriptivo | Rangos válidos de valores | Permite valores nulos | Índices de la columna | Descripción |
--- | --- | --- | --- |--- | --- |  ---
| ***id_user*** | integer(10) | Clave de la orden de servicio | | No | Index | Este campo es la clave única del usuario. Hace referencia a la tabla **users** |
| ***id_video*** | integer(10) | Clave de la orden de servicio | | No | Index | Este campo es la clave única del video calificado por el usuario. Hace referencia a la tabla de **videos**|
| *rating* | integer(10) | Nombre de la etiqueta | | No | | Este campo es el nombre asociado a la etiqueta |
| *created_at* | timestamp | Fecha de creación | | No | | Este campo se llena automáticamente por parte de la base de datos. Es usado para identificar la fecha en que se creó el registro |
| *updated_at* | timestamp | Fecha de actualización | | No | | Este campo se llena automáticamente por parte de la base de datos. Es usado para identificar la fecha en que se actualizó el registro |

---

### user_recommendations

- Nombre de la tabla- **user_recommendations**
- Descripción: Tabla que almacena los videos recomendados para cada usuarios. Esta tabla está sujeta a cambios constantes.

---

| Nombre de la columna | Tipo | Nombre descriptivo | Rangos válidos de valores | Permite valores nulos | Índices de la columna | Descripción |
--- | --- | --- | --- |--- | --- |  ---
| ***id_user*** | integer(10) | Clave de la etiqueta | | No | Index | Este campo es la clave única del usuario. Hace referencia a la tabla **users** |
| ***id_video*** | integer(10) | Clave del video | | No | Index | Este campo es la clave única del video calificado por el usuario. Hace referencia a la tabla **videos** |

---

## APÉNDICE A 
### TIPOS DE DATOS

| Nombre del tipo | Descripción |
--- | ---
| bigint | entero de ocho bytes con signo (-9223372036854775808 hasta 9223372036854775807) |
| bigserial | entero de ocho bytes autoincremento |
| bit | cadena de bits de longitud fija | 
| bit varying(n) | cadena de bits de longitud variable |
| boolean | lógico booleano (verdadero/falso) | 
| bytea | datos binarios character(n) |
| char(n) | cadena de caracteres de longitud fija | 
| date | fecha calendario (año, mes día) |
| double precision| un valor en punto flotante de doble precisión (15 digítos decimales) | 
| integer | entero de cuatro bytes con signo (-2147483648 hasta +2147483647) | 
| interval(p) | intervalo de tiempo de uso general |
| decimal [(p,s)] | valor numérico exacto con precisión seleccionable (p) y lugares decimales (s) | 
| real | un valor en punto flotante de precisión simple (6 dígitos decimales) |
| smallint | entero de dos bytes con signo (-32768 hasta +32767) | 
| serial | entero de cuatro bytes con autoincremento |
| text | cadena de caracteres de longitud variable |
| time | hora del día | 
| timez| hora del día, incluida zona horaria |
| timestamp| fecha y hora |
| timestamptz| fecha y hora, incluida zona horaria |
| varchar(n)| cadena de caracteres de longitud variable |