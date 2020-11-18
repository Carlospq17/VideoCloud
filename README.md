# VideoCloud

## Autores:
- Diego Avila Morales
- Manuel Martin Rico
- Miguel Ángel Quiñones Ramírez
- Carlos Alejandro Pool Quintal

## Documento de Arquitectura de Software

## Índice
- [VideoCloud](#videocloud)
  - [Autores:](#autores)
  - [Documento de Arquitectura de Software](#documento-de-arquitectura-de-software)
  - [Índice](#índice)
  - [Introducción](#introducción)
    - [Propósito](#propósito)
    - [Alcance](#alcance)
    - [Documentos de referencia](#documentos-de-referencia)
  - [Arquitectura](#arquitectura)
    - [Descripción de la arquitectura utilizada (Capas)](#descripción-de-la-arquitectura-utilizada-capas)
    - [Definición teórica de Microservicios](#definición-teórica-de-microservicios)
    - [Diagrama de arquitectura con descripción](#diagrama-de-arquitectura-con-descripción)
    - [Diagrama de secuencia para los procesos descritos en la descripción de la App 1 y la App 2](#diagrama-de-secuencia-para-los-procesos-descritos-en-la-descripción-de-la-app-1-y-la-app-2)
    - [Diagrama de la base de datos](#diagrama-de-la-base-de-datos)
    - [Descripción de las entidades](#descripción-de-las-entidades)
    - [Diagrama entidad-relación](#diagrama-entidad-relación)
  - [Documentación de la API](#documentación-de-la-api)
  - [Criterios de calidad](#criterios-de-calidad)

---

## Introducción

Este documento tiene como propósito describir la arquitectura global del proyecto *VideoCloud*, básandose en el modelo arquitectónico orientado a servicios cuyas características orientadas a *funcionalidad*, *Mantenibilidad*, *Eficiencia*, *Usabilidad* y *Confiabilidad* en conjunto con la implementación de tecnologías Web (API) proporcionan una solución viable para los requisitos y necesidades obtenidos para dicho proyecto.

Este documento incluye el propósito, alcance, referencias y un resumen del sistema.

### Propósito

El documento de arquitectura tiene como finalidad proveer una descripción comprensible de la arquitectura del proyecto VideoCloud. Se presentan un conjunto de arquitecturas basadas en capas y componentes que muestran diferentes aspectos del sistema, también se enfoca en recopilar las decisiones arquitecturales que se han definido en este proyecto.

Para representar el software con la mayor simpleza posible, la estructura de este documento se basa en la arquitectura en capas, cuya finalidad es dividir la aplicación en capas, con la intención de que cada capa tenga un rol muy definido.

### Alcance

El documento de arquitectura contendrá todos los componentes arquitectónicos a usarse en el proyecto VideoCloud. Se pretende proveer una fuente de referencia para todos los involucrados en el proyecto. El contenido de este documento es de carácter técnico-informativo, de uso exclusivo de la empresa y/o cliente.

El contenido aquí presentado solamente será accedido y modificado bajo los lineamientos establecidos por el equipo de trabajo.

### Documentos de referencia

- IEEE Recommended Practice for Software Design Descriptions, Software Engineering Standards Committee of the IEEE Computer Society, September, 1998. http://cs.bilkent.edu.tr/~cagatay/cs413/1016-1998_00741934.pdf  
- What are microservices? (s. f.). microservices.io. Recuperado 17 de noviembre de 2020, de https://microservices.io/
- ¿Qué son los microservicios? (s. f.). Redhat. Recuperado 17 de noviembre de 2020, de https://www.redhat.com/es/topics/microservices/what-are-microservices

---

## Arquitectura

### Descripción de la arquitectura utilizada (Capas)

> Meter la cosa de capas

### Definición teórica de Microservicios

Los microservicios se tratan de un estilo arquitectónico mediante el cual una aplicación se estructura en función a una colección de **servicios** que deben ser:
* Altamente mantenibles y probables
* Débilmente acoplados
* Independientes en su despliegue
* Organizados de acuerdo a las capacidades de la empresa
* Liderados por un equipo de desarrollo pequeño

Esto quiere decir que permite un despliegue rápido, frecuente y confiable de aplicaciones grandes y complejas. Es un elemento fundamental de la optimización del desarrollo de aplicaciones hacia un modelo nativo de la **nube**.

![alt text](resources/microservices.png "Arquitectura de Microservicios")

Cada función se denomina servicio y se puede diseñar e implementar de forma independiente. Es más, desarrollar utilizando este estilo arquitectónico provee beneficios como:
* Aplicaciones más rápidas para comercializarse
* Gran capacidad de expansión
* Capacidad de recuperación 
* Facilidad de implementación
* Accesibilidad para los desarrolladores
* Aplicaciones más abiertas

### Diagrama de arquitectura con descripción

> Diagrama de la arquitectura con sus respectivas descripción

### Diagrama de secuencia para los procesos descritos en la descripción de la App 1 y la App 2

> Diagrama de secuencias

### Diagrama de la base de datos

![alt text](resources/StreamServiceAPI.png "Diagrama de la base de datos para SongCloud")

### Descripción de las entidades

Para una descripción más precisa de las entidades involucradas en la base de datos, se anexa a continuación el siguiente documento de [diseño de la base de datos](https://docs.google.com/document/d/1nUIwVgMMC-rgfiYJIb37Z4NiLlI71eAl7fttU49Pfq0/edit?usp=sharing)

### Diagrama entidad-relación

![alt text](resources/Diagrama%20ER.png "Diagrama entidad-relación para SongCloud")

---

## Documentación de la API

> Aquí metemos un buen y rico POSTMAN (Si es posible)

---

## Criterios de calidad

> Para los criterios de calidad de acuerdo a la ISO/IEC

- Funcionalidad
- Mantenibilidad
- Eficiencia
- Usabilidad
- Confiabilidad