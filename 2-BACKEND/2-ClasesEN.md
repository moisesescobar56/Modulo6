# IMPLEMENTACION DE CLASES EN EL PROYECTO 

## PARTE 1 - Analisis de clases segun modelo de datos
Al inicio de todo proyecto es recomendable haber hecho un analisis de la solucion que quiere construir, con el fin de contemplar que datos llegara a manipular el proyecto al completarlo, de no realizarse el analisis los desarrolladores deberan realizar cambios constantes en el modelo de datos, lo cual afectara la duracion estimada de entrega. 

Para mitigar esta problematica, nos auxilaremos de buenas practicas y modelaremos el diagrama de clases de nuestra solucion. 
![image](https://github.com/user-attachments/assets/b50c27ce-6abc-4d71-bbce-e5aa906673ca)

## PARTE 2 - Creacion de clases
Las clases de nuestro modelo de datos debe crearse en la **"Capa de entidades (EN)"** como se muestra en el siguiente esquema: 
![image](https://github.com/user-attachments/assets/83880c6b-fb27-4909-b10f-94987ce025c5)

Es importante respetar el orden de creacion del diagrama de clases. Solo se trabajara con la clase Cargo y Empleado, pero en un escenario real se deben crear todas las clases.

![image](https://github.com/user-attachments/assets/635f2fb3-4f8a-47a3-8fa0-cd0c6aed17e3)

**IMPORTANTE:** se recomienda primero crear los archivos de clases y luego codificarlas.

**Paso 1:** Ubicarse en la capa **"SistemaElParaisal.DAL"** y dar clic derecho y seleccionar **"Agregar > Clase"**.

**Paso 2:** Nombrar la clase **"Cargo.cs"** y dar clic en **Agregar**.
