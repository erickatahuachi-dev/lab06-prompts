# lab06-prompts
Bitacora de ingenieria de prompts
# Bitacora de prompts 
Laboratorio 06: Fundamentos de Ingenieria de Prompts. 
Herramienta de IA usada: (escribe aqui cual usaste) 
## Ejercicio 2: Tokens y ventana de contexto

### 1. Conteo de tokens
| Texto | Caracteres | Tokens |
|---|---|---|
| Los estudiantes programan en Java. | 35 | 7 |
| The students program in Java. | 30 | 6 |
| desafortunadamente | 18 | 4 |

### 2. Explicación de la ventana de contexto
En los pasos 4 y 5 se observó que en el mismo chat la IA recordó el nombre "TiendaTec" y "Java Swing" porque esa información se encontraba dentro de su ventana de contexto activa. Al abrir un chat nuevo, la IA no pudo responder correctamente debido a que la ventana de contexto inicia completamente limpia y no conserva memoria de conversaciones o chats anteriores.
## Ejercicio 3: Temperatura

### 1. Resultados del simulador
| Temperatura | % de BiblioTec | Nombres en los 5 intentos |
|---|---|---|
| 0 | 100% | BiblioTec, BiblioTec, BiblioTec, BiblioTec, BiblioTec |
| 0.5 | 81.3% | BiblioTec, BiblioTec, LibroYa, BiblioTec, PrestaLibro |
| 1.0 | 48.7% | BiblioTec, PrestaLibro, LibroYa, LectoGo, BiblioTec |
| 1.8 | 32.1% | LectoGo, NubeDeTinta, BiblioTec, PaginaLibre, LibroYa |

### 2. Explicación
Al aumentar la temperatura, las probabilidades de las distintas opciones se distribuyen de forma más uniforme, lo que hace que el modelo elija palabras menos frecuentes y genere resultados más variados. El simulador nunca inventa un nombre nuevo porque la temperatura solo altera la probabilidad de selección entre los elementos del conjunto predefinido de datos, sin añadir información externa al modelo.
## Ejercicio 4: Prompt vago vs estructurado

| Criterio | Prompt vago | Prompt estructurado |
|---|---|---|
| Menciona el objetivo del sistema | No | Si |
| Menciona a los usuarios principales | No | Si |
| Tiene exactamente 3 funcionalidades | No | Si |
| Esta en 3 parrafos | No | Si |
| Lo usaria en un informe real | No | Si |
## Ejercicio 5: Anatomia de un prompt

### 1. Tabla de componentes
| Componente | Texto de mi prompt |
|---|---|
| Rol | Actua como desarrollador Java. |
| Instruccion | Crea un programa en Java usando una clase Producto con los atributos codigo, nombre, precio y stock. |
| Contexto | Para gestionar los productos de una tienda. |
| Ejemplo | Usa este estilo para los metodos: getPrecio(), setPrecio(double precio). |
| Formato | Explica primero la estructura de la clase y luego presenta el codigo Java. |

### 2. Evolución por niveles
- Nivel 1: La IA genero un programa generico basico (tipo Hola Mundo o calculadora) al carecer de especificaciones.
- Nivel 2 (+Rol): Adoptó un enfoque y lenguaje técnico orientado a mejores prácticas de desarrollo en Java.
- Nivel 3 (+Contexto): Orientó el diseño y la lógica del programa hacia la gestión de inventario comercial.
- Nivel 4 (+Instrucción): Definió la estructura específica de la clase Producto con los cuatro atributos requeridos.
- Nivel 5 (+Formato y Ejemplo): Separó claramente la explicación conceptual del código y adaptó el estilo de los métodos getter y setter al ejemplo provisto.
## Ejercicio 6: Del prompt basico al profesional

### 1. Evaluación del prompt profesional
| Qué revisar | Cumple (Si/No) |
|---|---|
| ¿Está escrito en Java y usa Swing? | Si |
| ¿Pide correo y contraseña? | Si |
| ¿Explica el funcionamiento antes o después del código? | Si |
| ¿El código está organizado en clases? | Si |
| ¿Valida los datos que ingresa el usuario? | No |

### 2. Prompts utilizados

```text
Prompt profesional:
Actua como desarrollador Java. Crea un ejemplo de login para una aplicacion de escritorio utilizando Swing. El usuario debe ingresar correo y contrasena. Explica brevemente el funcionamiento y presenta el codigo organizado por clases.

Prompt de mejora (iteración):
Mejora el codigo anterior con estas restricciones: no uses librerias externas, valida que el correo contenga @ y que la contrasena tenga al menos 8 caracteres, y muestra los mensajes con JOptionPane.
