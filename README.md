# Actividad 2: Interfaz Gráfica con Conexión a MySQL #

Este proyecto detalla la creación de una interfaz gráfica en **C#** diseñada para interactuar con una base de datos **MySQL**. El sistema permite validar credenciales, gestionar errores de red y visualizar datos en tiempo real.

---

## 🛠️ Configuración Técnica

Para garantizar la estabilidad y evitar errores de compatibilidad, se utiliza la siguiente configuración:

* **Librería:** `MySql.Data` versión **8.1**.
* **Entorno:** .NET con Windows Forms.
* **Dependencias:** Es fundamental instalar la versión específica 8.1 desde el administrador de paquetes NuGet para asegurar la comunicación con el servidor.

---

## 📖 Guía de Uso

Siga estos pasos para probar la conectividad de la interfaz:

### 1. Inicio del Proyecto
Al ejecutar la aplicación, se presentará una **Interfaz de conexión** limpia con los campos de configuración vacíos.
<img width="912" height="438" alt="Fig4" src="https://github.com/user-attachments/assets/c8afce8d-2c17-446b-b658-d8899b4bd48e" />


### 2. Pruebas de Error (Manejo de Excepciones)
[cite_start]El sistema está capacitado para identificar y notificar fallos comunes antes de establecer una conexión exitosa]:

* **Error de Puerto:** Si se ingresa un puerto incorrecto (diferente al 3306 por defecto), el sistema arrojará un mensaje indicando que no se pudo conectar al host de MySQL.
  <img width="915" height="540" alt="Fig5" src="https://github.com/user-attachments/assets/d26c44f0-fea8-47aa-a47b-a8499be47ada" />

* **Base de Datos Inexistente:** Si las credenciales son válidas pero el nombre de la base de datos no existe en el servidor, la interfaz mostrará un error de "Unknown database".
  <img width="916" height="441" alt="Fig6" src="https://github.com/user-attachments/assets/a7f5d1ca-de74-4c1d-ad80-debb9065c291" />


### 3. Conexión Exitosa y Visualización
Para visualizar los datos, ingrese los parámetros correctos de su servidor (Usuario, Contraseña, Host, Base de Datos y Puerto):

1. Presione el botón **Conectar**.
2. El sistema ejecutará una consulta `SELECT * FROM CatPersonal`.
3. Los datos (ID, Nombre y Cargo) se desplegarán automáticamente en el control de datos (DataGridView) de la interfaz.
<img width="913" height="435" alt="Fig7" src="https://github.com/user-attachments/assets/bd3c9bde-67d4-47d6-814c-82142d672ec9" />

---

## 💻 Código Fuente Principal

El núcleo de la conexión se basa en la construcción dinámica de la cadena de conexión:
<img width="766" height="756" alt="Fig8" src="https://github.com/user-attachments/assets/19af1265-f255-4fc5-a684-6370ffea771a" />
<img width="891" height="300" alt="Fig9" src="https://github.com/user-attachments/assets/3c0933a4-6cb3-46fe-82bc-c82389b68c0b" />

