# Programación de funcionalidad AGREGAR

## PARTE 1 - Programación del boton NUEVO
**Paso 1:** Abrir el formulario "AdminEmpleadoForm.cs".

![image](https://github.com/user-attachments/assets/214b7ef7-e17a-4143-92e9-27898ad64d7c)

**Paso 2:** dar doble clic sobre el boton **"NUEVO"** para generar el “Evento Click”

![image](https://github.com/user-attachments/assets/0cf8db99-dc62-4e72-b7ba-70b297d06b6f)

**Resultado:**
![image](https://github.com/user-attachments/assets/002be4e1-f887-4b23-ae23-ad7f1dfce22e)

**Paso 3:** Programar la lógica para abrir el formulario **“RegistroEmpleadoForm.cs”**
```csharp
// Abrir formulario para registrar un nuevo cliente 
RegistroEmpleadoForm frmResigistro = new RegistroEmpleadoForm();
frmResigistro.ShowDialog();
```

![image](https://github.com/user-attachments/assets/a9263d86-be4e-4c72-a731-2e2cf196add2)

## PARTE 2 - Programación de funcionalidad GUARDAR 
**Paso 1:** Abrir el formulario **"RegistroEmpleadoForm.cs"**.

![image](https://github.com/user-attachments/assets/db804307-c140-44fc-afd9-2ca0712604f7)

**Paso 2:** Agregar un ErrorProvider al formulario, arrastrándolo y dejándolo caer en el Diseño del formulario “RegistroEmpleadoForm.cs” 

![image](https://github.com/user-attachments/assets/79ce254b-03f7-490e-bf61-dd5e01e723ff)

**Paso 3:** Cambiar el nombre del “errorProvider1” a **“errorProvider”** en la ventana de Propiedades.

![image](https://github.com/user-attachments/assets/acd75045-034d-4af6-b8ee-d87a978f41cb)

**Paso 4:** Seleccionar el formulario “RegistroEmpleadoForm.cs” en el diseño y en la ventana de propiedades, seleccionar la opción **Eventos**.

![image](https://github.com/user-attachments/assets/663c9dbe-9ebd-4a73-8f0f-35c097bbaa32)

**Paso 5:** Generar el evento Load del formulario, dando doble click en la opción Load. 

![image](https://github.com/user-attachments/assets/5b1e5000-6bf6-4023-8f55-8c5f169b459b)

**Resultado**
![image](https://github.com/user-attachments/assets/b36f2d19-abb9-41e9-a386-0c1b8a515d1f)

**Paso 6:** Agregar referencias a bibliotecas en el formulario.
```csharp
//Referencias del proyecto
using SistemaElParaisal.EN;
using SistemaElParaisal.BL;
// Extension de metodos
using ToolsForms;
```
![image](https://github.com/user-attachments/assets/1595b46b-9e7b-4790-8aff-be567cf53dc4)

**Paso 7:** Agregar conexión a la base de datos mediante instancia a la clase **EmpleadoBL**. 
```csharp
// Conexion a la tabla de Empleados en la DB
EmpleadoBL empleadoBL = new EmpleadoBL();
```
![image](https://github.com/user-attachments/assets/4081210e-5c66-4f29-8c64-206696a29d35)

**Paso 8:** Agregar a la lógica la variable “idEmpleado” para almacenar la llave primaria de cualquier registro de "Empleado" que se desee modificar. Debe **asignar el mismo tipo de dato** a como en esta en la **EN**.
```csharp
// Variables
public short idEmpleado = 0; // variable del mismo tipo que la PK
```
![image](https://github.com/user-attachments/assets/165cb33b-8e79-4c64-97e4-a0811c69fd2a)

** Paso 9: Programar la lógica del método interno **"CargarCargos()"** que nos permitirá mostrar en forma de lista de selección las cargos en un formulario.
```csharp
public void CargarCargos()
{
    // Conexion a la tabla de Cargo en la DB
    CargoBL categoriaBL = new CargoBL();

    // Inicializar lista 
    List<Cargo> cargos = new List<Cargo>();
    cargos.Add(new Cargo { IdCargo = 0, Nombre = "SELECCIONAR" });

    // Obtener lista de Cargos de la DB
    cargos.AddRange(categoriaBL.Buscar(new Cargo()));
    cargoComboBox.DataSource = cargos;

    // Configurar texto y valor de la lista de seleccion
    cargoComboBox.DisplayMember = "Nombre";
    cargoComboBox.ValueMember = "IdCargo";
}
```

![image](https://github.com/user-attachments/assets/11edff1d-8ed1-4586-8887-92c935525fc5)

