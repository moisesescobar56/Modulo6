# AUTOMATIZACIÓN DE PRUEBAS UNITARIAS

## ¿Que es una prueba unitaria?
Las pruebas unitarias son el proceso en el que se prueba la unidad funcional de código más pequeña. 

## ¿Por qué son importantes?
Las pruebas de software ayudan a garantizar la calidad del código y son una parte integral del desarrollo de software. Una práctica recomendada en el desarrollo de software es escribir el software como unidades pequeñas y funcionales, y luego escribir una prueba unitaria para cada unidad de código. 

## ¿Comó automatizar las pruebas unitarias ?
Puede escribir primero pruebas unitarias como código. Luego, ejecute ese código de prueba de forma automática cada vez que realice cambios en el código del software. De esta forma, si una prueba falla, puede aislar con rapidez el área del código que tiene el error. 

![image](https://github.com/user-attachments/assets/bdc1aa54-b9f4-4fba-bdf6-bd9d19d1dffc)

## PARTE 1 - Configuración de archivo “CargoUnitTest.cs”

**Paso 1:** Seleccionar el proyecto **“SistemaElParaisal.PruebasUnitarias”**, dar clic derecho y seleccionar 
**Agregar > Prueba Unitaria**.

![image](https://github.com/user-attachments/assets/cebf6194-4392-4147-8099-50b20d0a087f)

**Paso 2:** Dar clic derecho sobre el archivo **UnitTest1.cs** y seleccionar **Cambiar nombre**.

![image](https://github.com/user-attachments/assets/68901003-53b5-4258-a0fb-09ca8e981ee4)

**Paso 3:** Ingresar el nombre **“CargoUnitTest.cs”** y pulsar la tecla Enter. 

![image](https://github.com/user-attachments/assets/8d9d3a94-ed76-4de9-9a8d-75f4189880b4)

**Paso 4:** En el siguiente cuadro de dialogo seleccionar **"Si"**. Para que cambie en todas las referencias el 
nombre del archivo. 

![image](https://github.com/user-attachments/assets/2e1dd1cd-92c6-4275-a3d3-17f1b81efdf6)

**Resultado:**

![image](https://github.com/user-attachments/assets/38793d30-0ce3-4adf-92f5-74504b4bd563)

**Paso 5:** Agregar las **referencias a bibliotecas** para acceder a la tabla Cargo en la base de datos 
desde el archivo **“CargoUnitTest.cs”**.

```csharp
// Referencias
using System.Collections.Generic;
// Referencias del proyecto
using SistemaElParaisal.EN;
using SistemaElParaisal.BL;
```

![image](https://github.com/user-attachments/assets/49328cc5-898b-4ca5-b71d-7443868ec14b)

**Paso 6:** Borrar el método **TestMethod1** del archivo **“CargoUnitTest.cs”**.

![image](https://github.com/user-attachments/assets/e58392e5-6bfc-4de5-8ba6-23a2e725a734)

**Resultado:**
![image](https://github.com/user-attachments/assets/7e28b57f-79d8-4042-be64-7df685f069bb)

## PARTE 2 - Programación de métodos de prueba en “CargoUnitTest.cs” 

![image](https://github.com/user-attachments/assets/9d90a250-ee2c-48cf-9d07-900131de0dab)

**Paso 1:** Agregar la instancia a la clase **CargoBL** para acceder a la tabla Cargos de la base de  datos.
```csharp
// Conexion a la tabla de Cargos en la DB mediante una instancia de CargoBL
CargoBL cargoBL = new CargoBL();
```
![image](https://github.com/user-attachments/assets/a2374c10-07b6-43e4-84d7-51c2000382f9)

**Paso 2:** Programar el **[TestMethod]** para comprobar el funcionamiento del método **ObtenerPorId**
de **CargoBL**. 

```csharp
[TestMethod]
public void T1_ObtenerPorId()
{
    // Buscar el cargo con id = 1
    Cargo cargo = cargoBL.ObtenerPorId(1);

    // Comprobacion de la prueba
    // si el Id de Cargo es diferente de 0, el Cargo se obtuvo por Id correctamente
    Assert.AreNotEqual(0, cargo.IdCargo);
}
```
![image](https://github.com/user-attachments/assets/3319ccab-d58c-403a-8907-81183120b833)

**NOTA:** La configuracion del nombre de las pruebas unitarias es conformado por la siguiente estructura: 

**"T"** + ***"Numero de prueba"*** + **"_"** + ***"Metodo a probar"*** 

**Paso 3:** Programar el **[TestMethod]** para comprobar el funcionamiento del método **Buscar** de 
**CargoBL**.
```csharp
[TestMethod]
public void T2_Buscar()
{
    List<Cargo> lista = cargoBL.Buscar(new Cargo { Nombre = "ADMIN" });

    // Comprobacion de la prueba
    // si el total de la lista es diferente de 0, los Cargos se buscaron correctamente
    Assert.AreNotEqual(0, lista.Count);
}
```

![image](https://github.com/user-attachments/assets/61f52df4-3742-4331-a739-de1bd5136c8e)


## PARTE 3 - Configuración de archivo “EmpleadoUnitTest.cs”

**Paso 1:** Seleccionar el proyecto **“SistemaElParaisal.PruebasUnitarias”**, dar clic derecho y seleccionar 
**Agregar > Prueba Unitaria**.

![image](https://github.com/user-attachments/assets/cebf6194-4392-4147-8099-50b20d0a087f)

**Paso 2:** Dar clic derecho sobre el archivo **UnitTest1.cs** y seleccionar **Cambiar nombre**.

![image](https://github.com/user-attachments/assets/1a579eef-9773-44c0-a23a-0796f2239206)


**Paso 3:** Ingresar el nombre **“EmpleadoUnitTest.cs”** y pulsar la tecla Enter. 

![image](https://github.com/user-attachments/assets/23eaa2da-5ddc-4427-893d-b3370f8b4719)

**Paso 4:** En el siguiente cuadro de dialogo seleccionar **"Si"**. Para que cambie en todas las referencias el 
nombre del archivo. 

![image](https://github.com/user-attachments/assets/be69a2ac-e0cb-4694-93df-4cb4a4923262)

**Resultado:**

![image](https://github.com/user-attachments/assets/c167e46a-04c5-4660-9fa1-8afaac4a3da0)


**Paso 5:** Agregar las **referencias a bibliotecas** para acceder a la tabla Empleado en la base de datos 
desde el archivo “EmpleadoUnitTest.cs”.

```csharp
// Referencias
using System.Collections.Generic;
// Referencias del proyecto
using SistemaElParaisal.EN;
using SistemaElParaisal.BL;
```

![image](https://github.com/user-attachments/assets/d0aeb952-13ee-4ef3-88ae-797665698028)

**Paso 6:** Borrar el método TestMethod1 del archivo **“CargoUnitTest.cs”**.

![image](https://github.com/user-attachments/assets/87a0f018-8f64-4aee-a08e-04c288c986f1)

**Resultado:**
![image](https://github.com/user-attachments/assets/097406ec-4783-4a83-9d73-4d6371a41455)

## PARTE 4 - Programación de métodos de prueba en “EmpleadoUnitTest.cs” 

![image](https://github.com/user-attachments/assets/9d90a250-ee2c-48cf-9d07-900131de0dab)

**Paso 1:** Agregar la instancia a la clase **EmpleadoBL** para acceder a la tabla Empleados de la base de  datos.
```csharp
// Conexion a la tabla de Empleados en la DB mediante una instancia de EmpleadoBL
EmpleadoBL empleadoBL = new EmpleadoBL();
```
![image](https://github.com/user-attachments/assets/6a6e4945-0135-4470-9125-4e0b416789de)

**Paso 2:** Programar el **[TestMethod]** para comprobar el funcionamiento del método **Guardar**
de EmpleadoBL. 
```csharp
[TestMethod]
public void T1_Guardar()
{
    // instancia de Empleado con los datos a guardar
    Empleado empleado = new Empleado();
    empleado.IdCargo = 1;
    empleado.Nombre = "Ramon";
    empleado.Apellido = "Perez";
    empleado.Telefono = "12341234";
    empleado.Clave = "123";
    // Ejecutar metodo 
    int resultado = empleadoBL.Guardar(empleado);

    // Comprobacion de la prueba
    // si resultado es igual a 1, la Empleado se guardo correctamente
    Assert.AreEqual(1, resultado);
}
```

![image](https://github.com/user-attachments/assets/841adca7-1842-43e8-96f0-5a15be922aa4)

**Paso 3:** Programar el **[TestMethod]** para comprobar el funcionamiento del método **Modificar**
de EmpleadoBL. 
```csharp
[TestMethod]
public void T2_Modificar()
{
    // instancia de Empleado con los datos a modificar
    Empleado empleado = empleadoBL.ObtenerPorId(1);
    empleado.IdCargo = 1;
    empleado.Nombre = "Juan";
    empleado.Apellido = "Perez";
    empleado.Telefono = "98001234";
    empleado.Clave = "123";
    // Ejecutar metodo
    int resultado = empleadoBL.Modificar(empleado);

    // Comprobacion de la prueba
    // si resultado es igual a 1, la Empleado se modifico correctamente
    Assert.AreEqual(1, resultado);
}
```

![image](https://github.com/user-attachments/assets/ec598dfd-cfb1-42b6-b92f-42e189dd9225)


**Paso 4:** Programar el **[TestMethod]** para comprobar el funcionamiento del método **Eliminar**
de EmpleadoBL. 
```csharp
[TestMethod]
public void T3_Eliminar()
{
    // Buscar el empleado con id = 3
    Empleado empleado = empleadoBL.ObtenerPorId(3);
    // Ejecutar metodo		
    int resultado = empleadoBL.Eliminar(empleado);

    // Comprobacion de la prueba
    // si resultado es igual a 1, la Empleado se elimino correctamente
    Assert.AreEqual(1, 1);
}
```

![image](https://github.com/user-attachments/assets/315581a2-d048-4285-87d8-64e7bf34229c)

**Paso 5:** Programar el **[TestMethod]** para comprobar el funcionamiento del método **ObtenerPorId**
de EmpleadoBL. 
```csharp
[TestMethod]
public void T4_ObtenerPorId()
{
    // Buscar el empleado con id = 1
    Empleado empleado = empleadoBL.ObtenerPorId(1);

    // Comprobacion de la prueba
    // si el Id de Empleado es diferente de 0, la Empleado se obtuvo por Id correctamente
    Assert.AreNotEqual(0, empleado.IdEmpleado);
}
```

![image](https://github.com/user-attachments/assets/5f073794-914a-47ba-b855-3c7484790353)


**Paso 6:** Programar el **[TestMethod]** para comprobar el funcionamiento del método **Buscar**
de EmpleadoBL. 
```csharp
[TestMethod]
public void T5_Buscar()
{
    List<Empleado> lista = empleadoBL.Buscar(new Empleado { Nombre = "Juan" });

    // Comprobacion de la prueba
    // si el total de la lista es diferente de 0, las Empleado se buscaron correctamente
    Assert.AreNotEqual(0, lista.Count);
}
```

![image](https://github.com/user-attachments/assets/6ca6e2fc-997f-4034-9c88-ca7bf942f90b)


## PARTE 5 - Ejecutar Pruebas Unitarias desde Visual Studio 
**Paso 1:** Seleccionar el proyecto “SistemaElParaisal.PruebasUnitarias” y dar clic derecho sobre el 
proyecto y seleccionar **Ejecutar pruebas**.

![image](https://github.com/user-attachments/assets/5ed370b9-4071-4043-aaa7-f5f015bb6bda)

**Resultado:**
![image](https://github.com/user-attachments/assets/e939c43c-c8ec-4939-ae2d-9b8369ed8867)
