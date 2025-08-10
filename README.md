# RAG_MED
Implementation of a Retrieval-Augmented Generation (RAG) system in Google Colab for semantic analysis of clinical texts.

# RAG for Semantic Analysis of Clinical and Anatomical Texts

**Autores:** [Martín Munive], [Cristian Henao].
**Artículo de Referencia:** [Publicación pendiente.]
**DOI del Repositorio:** [Publicación pendiente.]

## Resumen

Este repositorio contiene el código y la metodología para un sistema de Generación Aumentada por Recuperación (RAG) implementado en Google Colab. El sistema está diseñado para realizar búsquedas semánticas y análisis de contenido en documentos densos, como guías de práctica clínica o libros de texto de anatomía.

## Cómo Funciona

El flujo de trabajo sigue la arquitectura RAG estándar:
1.  **Carga de Documentos:** Se utiliza la librería `PyPDFium2` para una extracción de texto robusta desde archivos PDF.
2.  **División (Chunking):** El texto se divide en fragmentos solapados para mantener la coherencia semántica.
3.  **Embedding y Almacenamiento:** Los fragmentos se convierten en vectores mediante el modelo `models/embedding-001` de Google y se almacenan en una base de datos vectorial local (ChromaDB).
4.  **Recuperación y Re-ranking:** Se utiliza una estrategia de búsqueda de Relevancia Marginal Máxima (MMR) para recuperar un conjunto diverso de documentos, seguido de un re-ranking (opcional, con Flashrank) para la máxima precisión.
5.  **Generación de Respuesta:** Los fragmentos más relevantes se pasan, junto con la pregunta del usuario, al LLM `gemini-1.5-flash-latest` de Google para generar una respuesta sintetizada y basada en la evidencia.

## Instrucciones para la Reproducción

Para replicar este análisis, sigue estos pasos:

1.  **Clona el Repositorio:**
    `git clone https://github.com/tu-usuario/RAG-for-Clinical-Guideline-Analysis.git`

2.  **Configura el Entorno:**
    *   Abre el archivo `.ipynb` en Google Colab.
    *   Las dependencias se pueden instalar ejecutando la primera celda del notebook o usando el archivo `requirements.txt`:
      `pip install -r requirements.txt`

3.  **Configura los Datos:**
    *   Crea una carpeta llamada `RAG_MED-001_DB` en la raíz de tu Google Drive.
    *   **Importante:** Este repositorio no distribuye el material protegido por derechos de autor. Debes obtener una copia del documento a analizar (p. ej., `Gross-Anatomy-The-Big-Picture.pdf`) y colocarla dentro de esta carpeta.

4.  **Configura la API Key:**
    *   En Google Colab, haz clic en el ícono de la llave (🔑) en la barra lateral.
    *   Crea un nuevo secreto llamado `GOOGLE_API_KEY` y pega allí tu clave de la API de Google AI Studio.

5.  **Ejecuta el Notebook:**
    *   Ejecuta todas las celdas en orden.

## Cómo Citar

Si utilizas este código o metodología en tu investigación, por favor, cita nuestro artículo y este repositorio:

[Publicación pendiente].

```bibtex
@software{tu_apellido_2025_rag,
  author = {[Tu Nombre Completo]},
  title = {{RAG for Semantic Analysis of Clinical and Anatomical Texts}},
  month = {aug},
  year = {2025},
  publisher = {Zenodo},
  version = {v1.0.0},
  doi = {[DOI que obtendrás de Zenodo]},
  url = {https://doi.org/[DOI que obtendrás de Zenodo]}
}
