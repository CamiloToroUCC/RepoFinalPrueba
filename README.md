# Cognitive Training App

La **Cognitive Training App** es una aplicación diseñada para entrenar habilidades cognitivas mediante juegos y cuestionarios interactivos. El proyecto se divide en dos partes principales:

- **Backend:** Desarrollado con Spring Boot (Java) para gestionar la lógica de negocio, persistencia y APIs REST.
- **Frontend:** Desarrollado con Next.js, TypeScript y Tailwind CSS para la interfaz de usuario, comunicándose con el backend.

---

## Tabla de Contenidos

- [Características](#características)
- [Arquitectura y Patrones de Software](#arquitectura-y-patrones-de-software)
- [Estructura del Proyecto](#estructura-del-proyecto)
- [Requisitos Previos](#requisitos-previos)
- [Instalación y Ejecución](#instalación-y-ejecución)
  - [Clonación del Repositorio](#clonación-del-repositorio)
  - [Configuración y Ejecución del Backend](#configuración-y-ejecución-del-backend)
  - [Configuración y Ejecución del Frontend](#configuración-y-ejecución-del-frontend)
- [Despliegue](#despliegue)
- [Contribución](#contribución)
- [Licencia](#licencia)

---

## Características

- **Entrenamiento Cognitivo:** Juegos y cuestionarios para mejorar memoria, atención y otras habilidades.
- **Backend en Spring Boot:** Manejo de lógica de negocio y persistencia con H2 Database para desarrollo.
- **Frontend en Next.js:** Interfaz moderna y reactiva, utilizando Context API para el manejo global del estado.
- **Implementación de Patrones:** Se han empleado los patrones **Singleton**, **Factory Method**, **Observer** y **Composite** (según lo requerido).

---

## Arquitectura y Patrones de Software

El proyecto está organizado siguiendo los siguientes patrones, los cuales se usan de forma real en el código:

- **Singleton:**  
  El contenedor de Spring Boot crea todos los beans (por ejemplo, en `UserService` y `GameService`) en modo singleton, garantizando que exista una única instancia por aplicación.

- **Factory Method:**  
  Spring Boot utiliza internamente métodos fábrica para instanciar e inyectar componentes. Se invoca `SpringApplication.run(...)` en `ApplicationTraining.java`, que desencadena este proceso de forma automática.

- **Observer:**  
  La gestión del estado global se realiza en el frontend mediante la React Context API (definida en `src/context/AppContext.tsx`). Los componentes que consumen este contexto se actualizan automáticamente cuando cambia el estado.

- **Composite:**  
  La estructura en `BinarySearchTreeUsers.java` organiza los usuarios en un árbol basado en su puntaje. Mediante un recorrido in-order se obtiene un ranking ordenado, permitiendo tratar nodos individuales y compuestos de forma uniforme.

*Nota: Solo se han usado los patrones obligatorios del documento. Cualquier otro patrón (por ejemplo, MVC) queda implícito en la separación de capas del backend y frontend.*

---

## Requisitos Previos

Antes de clonar y ejecutar el proyecto, asegúrate de tener instalados los siguientes programas:

- **Java JDK 21**
- **Maven**
- **Node.js (versión 14 o superior) y npm**
- **Git** (opcional, para clonar el repositorio)
- Editor de código (por ejemplo, VS Code)

---

## Instalación y Ejecución

### Clonación del Repositorio

Utiliza Git para clonar el proyecto:

```bash
git clone https://github.com
```

###Navega a la carpeta del backend

```bash
cd cognitive-training-app
```

### Compila y empaqueta el proyecto con Maven:
```bash
mvn clean compile
```

### Para empaquetar la aplicación:
```bash
mvn package
```

###Ejecuta la aplicación:
```bash
mvn spring-boot:run
```


### En otra TerminalNavega a la carpeta del Frontend
```bash
cd ../../frontend/cognitive-training-frontend
```

### Instala las dependencias:
```bash
npm install
```

### Inicia el servidor de desarrollo:
```bash
npm run dev
```



