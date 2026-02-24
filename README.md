# ProyectoIA
# Customer Service Chatbot / Chatbot de Asistencia al Cliente

This project demonstrates a proof-of-concept for creating a Spanish customer support chatbot. We fine-tune a pre-trained language model using Quantized LoRA (QLoRA) and PEFT adapters to efficiently adapt the model for answering common customer queries.

Este proyecto demuestra una prueba de concepto para crear un chatbot de asistencia al cliente en español. Se realiza fine-tuning de un modelo preentrenado utilizando Quantized LoRA (QLoRA) y adaptadores PEFT para adaptar de forma eficiente el modelo y responder consultas comunes de clientes.

---
## Introduction / Introducción

**English:**  
The goal of this project is to build a Spanish customer service chatbot capable of answering frequently asked questions (e.g., business hours, order cancellation, payment methods, etc.). We leverage a pre-trained Spanish language model (based on GPT-2), quantize it to 4-bit precision using BitsAndBytes, and fine-tune it with LoRA adapters to keep training efficient.

**Español:**  
El objetivo de este proyecto es construir un chatbot de asistencia al cliente en español, capaz de responder preguntas frecuentes (por ejemplo, horarios de atención, cancelación de pedidos, métodos de pago, etc.). Utilizamos un modelo de lenguaje preentrenado en español (basado en GPT-2), lo cuantizamos a precisión de 4 bits con BitsAndBytes y lo afinamos utilizando adaptadores LoRA para mantener la eficiencia en el entrenamiento.

---
## Data Preparation / Preparación de Datos

**English:** 
The dataset is defined as a list of customer queries and responses in Spanish. Each example is formatted into a single "text" field that contains both the instruction and the answer.

**Español:** 
El conjunto de datos se define como una lista de consultas de clientes y respuestas en español. Cada ejemplo se formatea en un único campo "text" que contiene tanto la instrucción como la respuesta.

## Model Setup and Fine-Tuning / Configuración del Modelo y Fine-Tuning

**English:** 
We load a pre-trained Spanish model (datificate/gpt2-small-spanish).
The model is quantized to 4-bit precision using BitsAndBytes.
PEFT and LoRA adapters are attached to enable fine-tuning of the quantized model.
We use TRL's SFTTrainer for supervised fine-tuning on the dataset.

**Español:** 
Se carga un modelo preentrenado en español (datificate/gpt2-small-spanish).
El modelo se cuantiza a 4 bits usando BitsAndBytes.
Se adjuntan adaptadores LoRA mediante PEFT para permitir el fine-tuning del modelo cuantizado.
Se utiliza el SFTTrainer de TRL para el fine-tuning supervisado con el conjunto de datos.

## Training Issues and Challenges / Problemas y Desafíos del Entrenamiento

**English:** 
Small and Non-Diverse Dataset: Only 5 examples are used, which is insufficient for the model to learn generalizable patterns.
Incoherent Responses: Due to limited data, the model may generate long, unrestrained, or incoherent responses.
Evaluation and Generation Issues: Lack of systematic evaluation and parameter tuning can result in text without constraints.

**Español:** 
Dataset Pequeño y Poco Diverso: Se utilizan solo 5 ejemplos, lo que es insuficiente para que el modelo aprenda patrones generalizables.
Respuestas Incoherentes: Debido a la limitación de datos, el modelo puede generar respuestas largas, sin restricciones o incoherentes.
Problemas de Evaluación y Generación: La falta de evaluación sistemática y ajustes en los parámetros puede derivar en la generación de texto sin restricciones.

## Inference / Inferencia

**English:** 

The inference function generates responses by:
Formatting the prompt to match the training data format.
Passing the input's attention mask and pad token ID to ensure reliable output.
Extracting the response part from the generated text.

**Español:** 
La función de inferencia genera respuestas de la siguiente manera:
Formatea el prompt para que coincida con el formato utilizado en el entrenamiento.
Pasa la máscara de atención y el pad_token_id del input para garantizar un output confiable.
Extrae la parte correspondiente a la respuesta del texto generado.

## Usage / Uso

**English:** 
Once fine-tuning is completed, you can use the model to answer customer queries. For example:
"How can I change my shipping address?"
"What payment methods are available?"

**Español:** 
Una vez finalizado el fine-tuning, puedes utilizar el modelo para responder consultas de clientes. Por ejemplo:
"¿Cómo puedo cambiar mi dirección de envío?"
"¿Qué métodos de pago aceptan?"

## Saving and Deployment / Guardado y Despliegue

**English:** 
The fine-tuned model and tokenizer are saved locally for future deployment or further evaluations.

**Español:** 
El modelo ajustado (fine-tuned) y el tokenizador se guardan localmente para su despliegue futuro o evaluaciones adicionales.

## Conclusion / Conclusión

**English:** 
This project serves as a proof-of-concept for a Spanish customer service chatbot using fine-tuning on a quantized model with LoRA adapters. Future improvements include expanding the dataset, refining generation parameters, and implementing systematic evaluation.

**Español:** 
Este proyecto sirve como prueba de concepto para un chatbot de asistencia al cliente en español, utilizando fine-tuning sobre un modelo cuantizado con adaptadores LoRA. Las mejoras futuras incluyen ampliar el conjunto de datos, refinar los parámetros de generación e implementar una evaluación sistemática.

## Contact / Contacto
**English:** 
For further information, please contact @paucimi.

**Español:** 
Para más información, por favor contacta a @paucimi.
