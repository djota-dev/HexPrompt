# HexPrompt - MVP Roadmap

## 1. Preparación del entorno
- [ ] Crear un repositorio nuevo `HexPrompt` en GitHub o local
- [ ] Crear entorno virtual Python (`venv`) y activarlo
- [ ] Instalar dependencias necesarias (`openai`, `argparse`, `requests`)

## 2. Diseño básico del script principal
- [ ] Crear archivo `hexprompt.py`
- [ ] Implementar parser de argumentos (API key, modelo, prompt o archivo con múltiples prompts)
- [ ] Crear función para enviar un prompt a la API de OpenAI y recibir respuesta
- [ ] Manejar errores de conexión o límite de tokens

## 3. Implementación del fuzzer básico
- [ ] Permitir pasar un solo prompt o cargar múltiples prompts desde un archivo `.txt`
- [ ] Enviar cada prompt a la API y guardar la respuesta en memoria
- [ ] Mostrar resultados por consola de forma clara y ordenada

## 4. Detección simple de patrones sospechosos en respuestas
- [ ] Definir lista de palabras o frases indicativas de evasiones o saltos de rol (ej: “Lo siento, no puedo…”, “No puedo revelar…”)
- [ ] Marcar o resaltar en el output respuestas que contengan esos patrones

## 5. Guardar resultados en archivos
- [ ] Crear carpeta `outputs` para almacenar logs y resultados
- [ ] Guardar cada sesión de fuzzing en un archivo con timestamp (ej: `output_YYYY-MM-DD_HHMM.txt`)
- [ ] Incluir prompt, respuesta y marcas de patrones sospechosos

## 6. Documentación inicial
- [ ] Crear `README.md` con descripción del proyecto y cómo usar el script
- [ ] Explicar requisitos, instalación, uso básico y ejemplos de comandos
- [ ] Añadir notas sobre seguridad y límites de uso de la API

## 7. Pruebas y mejora iterativa
- [ ] Testear con prompts simples y maliciosos
- [ ] Refinar detección de patrones según resultados
- [ ] Añadir control de velocidad o espera para evitar límites de la API
- [ ] Mejorar legibilidad de la salida en consola (colores o formato)

## 8. Extras opcionales (post-MVP)
- [ ] Añadir soporte para múltiples APIs o modelos (HuggingFace, otros LLMs)
- [ ] Interfaz interactiva por terminal para enviar prompts en vivo
- [ ] Reportes HTML o JSON con análisis de respuestas
- [ ] Integrar base de datos local para historial de fuzzing y análisis



HexPrompt/
├── hexprompt/           ← Código fuente
│   ├── __init__.py
│   ├── cli.py           ← Entry-point (Click/argparse)
│   ├── fuzz.py          ← Lógica de envío de prompts
│   ├── patterns.py      ← Patrones de evasión
│   └── utils.py         ← Helpers (logging, lectura .env)
├── tests/               ← Pruebas unitarias
│   ├── test_fuzz.py
│   └── test_patterns.py
├── .env.example         ← Variables de entorno de muestra
├── pyproject.toml       ← Metadatos y dependencias
├── requirements.txt     ← (opcional, si no usas Poetry)
└── README.md            ← Documentación inicial
