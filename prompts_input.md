# Guía de Prompts para Generación de Imágenes

Cuatro enfoques para construir prompts, de lo más simple a lo más técnico: descripción directa, uso de referencias visuales, definición exacta vía JSON, y transferencia de estilo.

---

## 01. Prompt Descriptivo (Texto plano)

**Objetivo:** Generar una imagen desde cero describiendo el sujeto, el entorno, la iluminación y el estilo visual con precisión.

### Plantilla

```
[Sujeto/Producto detallado] ubicado en [Descripción del entorno/fondo].
Iluminación [Tipo de luz: ej. luz natural de tarde, luz de estudio].
Estilo visual [Estilo: ej. fotografía publicitaria, minimalista, fotorrealista],
tomado con una cámara [Tipo de cámara/lente: ej. 50mm, macro],
profundidad de campo [foco].
```

### Ejemplo para el Workshop

```
Una botella de agua de acero inoxidable de color verde oliva mate, con gotas
de condensación realistas en su superficie. Colocada sobre una roca lisa de
río, con un fondo difuminado de un bosque de pinos por la mañana. Luz solar
suave que se filtra a través de los árboles. Fotografía de estilo publicitario
exterior, plano medio, enfoque nítido en el producto.
```

---

## 02. Con Referencias (Estilo o Composición)

**Objetivo:** Guiar a la IA usando una imagen base (Image-to-Image o ControlNet en herramientas que lo permitan). El prompt debe describir la fusión entre la referencia y el nuevo producto.

### Plantilla

```
[Sujeto/Producto] integrado en una escena inspirada en la imagen de referencia.
Mantener la misma composición de [describir composición de la referencia,
ej. diagonal, elementos flotantes] y la paleta de colores [colores].
Estilo visual moderno y limpio.
```

### Ejemplo para el Workshop

*(Asumiendo que suben una imagen de referencia donde hay cosméticos flotando sobre agua)*

```
Una botella de agua de acero inoxidable verde oliva flotando horizontalmente
en el centro, salpicando agua cristalina a su alrededor. Mantener la
composición de la imagen de referencia, con el producto como eje central y
las ondas de agua dinámicas en un fondo azul turquesa claro.
```

---

## 03. Recrear con JSON (Definición exacta)

**Objetivo:** Para perfiles más técnicos o integraciones con APIs (como Adobe Firefly o Midjourney v6 en workflows automatizados). El JSON le dice a la máquina exactamente los parámetros de control.

### Plantilla/Ejemplo para el Workshop

```json
{
  "prompt": "Stainless steel green water bottle, studio lighting, minimal background",
  "aspect_ratio": "16:9",
  "style": {
    "preset": "photographic",
    "strength": 85,
    "visual_intensity": "high"
  },
  "composition": {
    "placement": "centered",
    "angle": "eye-level",
    "depth_of_field": "shallow"
  },
  "negative_prompt": "blurry, low quality, distorted, reflection on metal, hands"
}
```

---

## 04. Copiar Estilo (Acabado visual/Dirección de arte)

**Objetivo:** Enseñar a la IA a replicar la "vibra" o el look & feel de una marca/campaña sin copiar el producto de la referencia.

### Plantilla

```
Generar una imagen de [Sujeto/Producto] replicando el estilo visual de la
imagen de referencia: misma paleta de colores de tonos [cálidos/fríos/pasteles],
grano de película analógica, contraste [suave/alto] y estética
[ej. editorial de moda de los años 70, minimalismo escandinavo].
```

### Ejemplo para el Workshop

```
Una botella de agua de acero inoxidable verde oliva en una mesa de madera.
Replicar el estilo de la imagen de referencia: estética cálida "cozy style",
iluminación dorada de atardecer entrando por una ventana, tonos tierra
suaves, textura analógica con un ligero grano de película y atmósfera
nostálgica de revista de diseño de interiores.
```
