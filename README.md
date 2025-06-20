README: Aviatur Hoteles Frontend (Blazor WebAssembly)

Este repositorio contiene la aplicación de interfaz de usuario para el portal de reservas. Es una Single Page Application (SPA) desarrollada con Blazor WebAssembly, que consume los servicios de la API de AviaturHoteles para permitir la búsqueda y reserva de hoteles, así como la visualización de un reporte de reservas.

1. Estructura del Proyecto
   
  La solución del frontend (AviaturHoteles.FrontendSolution.sln) se organiza de la siguiente manera:

  * AviaturHoteles.Client:

    - Proyecto principal de Blazor WebAssembly.
    - Contiene los componentes de UI (archivos .razor en la carpeta Pages).
    - Gestiona la interacción del usuario y realiza llamadas HTTP a la API de backend.
    - Program.cs: Configura los servicios de la aplicación, incluyendo la URL base para el HttpClient que se comunica con la API.
    - Layout: Contiene componentes de diseño compartidos como NavMenu.razor.

  * AviaturHoteles.Shared.Client:

    - Librería de clases que contiene los Data Transfer Objects (DTOs) utilizados por el frontend.
    - Estos DTOs son una copia o una referencia a los definidos en el proyecto AviaturHoteles.Models de la API, asegurando la compatibilidad de los contratos de datos entre frontend y backend.

2. Prerrequisitos
   
  Para ejecutar este proyecto, necesitas tener instalado lo siguiente:

  - SDK de .NET 8.0.
  - Visual Studio 2022.
  - La API de AviaturHoteles (backend) debe estar ejecutándose para que el frontend pueda comunicarse con ella.

3. Configuración y Ejecución
   
  Sigue estos pasos para configurar y ejecutar la aplicación Blazor:

  Clonar el Repositorio:
  
  git clone https://github.com/Cocoska/FrontPortalReservas
  cd AviaturHoteles.FrontendSolution
  
  Verificar y Configurar la URL de la API:

  - Abre la solución AviaturHoteles.FrontendSolution.sln en Visual Studio.
  - Abre el archivo Program.cs en el proyecto AviaturHoteles.Client.
  - Asegúrate de que la URL (https://localhost:7028/) coincida con la URL base de tu API de Aviatur Hoteles. Si tu API se ejecuta en un puerto diferente, actualiza esta URL.

Restaurar Paquetes NuGet:

  - En el Explorador de soluciones, haz clic derecho en la solución (AviaturHoteles.FrontendSolution).
  - Selecciona "Restaurar paquetes NuGet" (o ejecuta dotnet restore desde la terminal en la carpeta de la solución).

Ejecutar la Aplicación Blazor:

  - Presiona F5 o haz clic en el botón "Iniciar" (el triángulo verde).
  - Esto iniciará la aplicación Blazor en tu navegador (ej. https://localhost:5001/). El puerto puede variar.
    
4. Páginas Clave de la Aplicación
   
  * Página de Búsqueda de Hoteles (/):
  
    Descripción: La página de inicio que permite a los usuarios buscar hoteles por ciudad, fechas de check-in/check-out y número de huéspedes.
    Funcionalidad: Envía solicitudes de búsqueda a la API y muestra los resultados en una lista. Permite iniciar el proceso de reserva.

  * Página de Reporte de Reservas (/reporteReservas):

    Descripción: Muestra un listado de todas las reservas registradas en el sistema. Incluye filtros para acotar la búsqueda por fechas de creación, ciudad, estado de la reserva, etc.
    Funcionalidad: Consume el endpoint de reporte de la API para cargar y mostrar los datos de las reservas en una tabla.
