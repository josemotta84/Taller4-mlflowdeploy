# Pipeline de Despliegue con MLflow

Este repositorio contiene un flujo de trabajo estructurado para el entrenamiento, validación y despliegue de modelos de aprendizaje automático, utilizando **MLflow** para el seguimiento de experimentos y **GitHub Actions** para la integración continua (CI).

## Estructura del Proyecto

El repositorio está organizado para separar la lógica del modelo de la configuración y automatización:

* **`src/train.py`**: Punto de entrada principal para entrenar modelos y registrar parámetros, métricas y artefactos en MLflow.
* **`src/validate.py`**: Gestiona la evaluación del modelo y las pruebas de rendimiento frente a conjuntos de datos de validación.
* **`Makefile`**: Contiene comandos abreviados para la configuración del entorno, entrenamiento y pruebas.
* **`.github/workflows/mlflow-ci.yml`**: Automatiza el pipeline de pruebas y seguimiento en cada commit al repositorio.
* **`requirements.txt`**: Define las dependencias de Python necesarias para ejecutar el proyecto.
* **`.gitignore`**: Asegura que los metadatos locales, entornos virtuales y archivos de datos pesados no se incluyan en el control de versiones.

---

## 🚀 Inicio Rápido

### Requisitos Previos
* **Python 3.14.3+**
* **MLflow** (instalado a través de los requisitos)
* **Make** (opcional, para usar el Makefile)

### Instalación
1.  **Clonar el repositorio:**
    ```bash
    git clone <url-de-tu-repositorio>
    cd mlflow-deploy
    ```
2.  **Instalar dependencias:**
    ```bash
    pip install -r requirements.txt
    ```

---

## Uso

### Entrenamiento del Modelo
Puedes ejecutar el script de entrenamiento directamente o usar la automatización:
```bash
python src/train.py
```

## Integración CI/CD

Este proyecto utiliza GitHub Actions para mantener la calidad del código y la integridad del modelo[cite: 1]. El flujo de trabajo mlflow-ci.yml se ejecuta automáticamente con cada "push" para realizar[cite: 1]:

Configuración del entorno.

Instalación de dependencias.

Ejecución del script de validación.

---
## Configuración
Tracking URI: Asegúrate de que tu servidor de seguimiento de MLflow sea accesible o esté configurado como un directorio local para que los experimentos se registren correctamente[cite: 1].

Variables de Entorno: Utiliza un archivo .env (asegúrate de que esté en el .gitignore) para gestionar credenciales sensibles o URLs específicas del servidor de seguimiento sin exponerlas en el código[cite: 1].
