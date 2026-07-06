# HolaMundoApp - Spring Boot con GitHub Actions

Proyecto de demostración de Spring Boot 3.5.5 con un pipeline CI/CD configurado con GitHub Actions.

## 📋 Requisitos

- **Java 17** o superior
- **Maven 3.6+**
- **Git**

## 🚀 Configuración Local

### 1. Clonar el repositorio
```bash
git clone https://github.com/NoeliaPodmoguilny/prueba_github_actions.git
cd prueba_github_actions
```

### 2. Compilar el proyecto
```bash
mvn clean install
```

### 3. Ejecutar la aplicación
```bash
mvn spring-boot:run
```

La aplicación se ejecutará en `http://localhost:8080`

## 🔄 Pipeline CI con GitHub Actions

Este proyecto incluye un pipeline automatizado que se ejecuta en cada:
- **Push** a la rama `main`
- **Pull Request** hacia la rama `main`

### ¿Qué hace el pipeline?

El archivo `.github/workflows/ci.yml` realiza:

1. ✅ **Checkout** del código
2. ✅ **Configuración de Java 17** (Temurin)
3. ✅ **Compilación y ejecución de tests** con Maven

### Comandos ejecutados

```bash
mvn -B -DskipTests=false clean verify
```

Este comando:
- `clean`: Limpia archivos compilados previos
- `verify`: Compila y ejecuta los tests
- `-B`: Modo batch (sin interacción)
- `-DskipTests=false`: Asegura que se ejecuten los tests

## 📁 Estructura del Proyecto

```
prueba_github_actions/
├── .github/
│   └── workflows/
│       └── ci.yml              # Pipeline GitHub Actions
├── src/
│   ├── main/java/...           # Código fuente
│   └── test/java/...           # Tests
├── pom.xml                      # Configuración Maven
└── README.md                    # Este archivo
```

## 🛠️ Stack Tecnológico

- **Spring Boot** 3.5.5
- **Java** 17
- **Maven** (gestor de dependencias)
- **GitHub Actions** (CI/CD)

## 📦 Dependencias Principales

- `spring-boot-starter-web`: Framework web
- `spring-boot-starter-test`: Testing con JUnit y Mockito

## 🎯 Próximos Pasos

1. Realiza cambios en el código
2. Haz commit y push a la rama `main`
3. Observa el pipeline ejecutarse automáticamente en la pestaña **Actions** de tu repositorio
4. Si todo es correcto, verás un ✅ verde junto a tu commit

## 📞 Recursos

- [Spring Boot Documentation](https://spring.io/projects/spring-boot)
- [GitHub Actions Documentation](https://docs.github.com/en/actions)
- [Maven Documentation](https://maven.apache.org/guides/index.html)
