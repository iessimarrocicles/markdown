# Sintaxis básica

En esta página se presentan los elementos básicos de Markdown junto con ejemplos prácticos para cada uno de ellos.

---

## Encabezados

Sintaxis

Usa `#` seguido de un espacio y el texto del encabezado. Añade más `#` para indicar niveles inferiores.

Ejemplos
```markdown
# Encabezado 1
## Encabezado 2
### Encabezado 3
```

Resultado:

# Encabezado 1
## Encabezado 2
### Encabezado 3

---

# Énfasis (Negrita y Cursiva)

### Sintaxis
- Negrita: Rodea el texto con `**` o `__`.
- Cursiva: Rodea el texto con `*` o `_`.
- Combinado: Usa tres asteriscos o guiones bajos.

### Ejemplos
```markdown
**Texto en negrita**
*Texto en cursiva*
***Texto en negrita y cursiva***
```

Resultado:

**Texto en negrita**

*Texto en cursiva*

***Texto en negrita y cursiva***

---

## 3. Listas

### Sintaxis
- **Desordenadas:** Usa `-`, `*` o `+`.
- **Ordenadas:** Usa números seguidos de un punto.

### Ejemplos
```markdown
- Elemento 1
- Elemento 2
    - Sub-elemento 2.1

1. Elemento 1
2. Elemento 2
    1. Sub-elemento 2.1
```

Resultado:

- Elemento 1
- Elemento 2
    - Sub-elemento 2.1

1. Elemento 1
2. Elemento 2
    1. Sub-elemento 2.1

---

## 4. Enlaces

### Sintaxis
- Enlace en línea: `[texto](URL)`
- Enlace como referencia: `[texto][referencia]` y define `[referencia]: URL`.

### Ejemplos
```markdown
[Google](https://www.google.com)
[Markdown Guide][guide]

[guide]: https://www.markdownguide.org
```

Resultado:

[Google](https://www.google.com)  
[Markdown Guide](https://www.markdownguide.org)

---

## 5. Imágenes

### Sintaxis
Usa `!` seguido del texto alternativo entre `[]` y la URL entre `()`.

### Ejemplo
```markdown
![Texto alternativo](https://via.placeholder.com/150 "Título de la imagen")
```

Resultado:

![Texto alternativo](https://via.placeholder.com/150 "Título de la imagen")

---

## 6. Código

### Sintaxis
- **En línea:** Usa `` ` `` para encerrar el texto.
- **Bloques de código:** Usa tres `` ` `` o tres `~` antes y después del bloque.

### Ejemplos
```markdown
En línea: `código corto`

Bloque:
```
print("Hola, mundo!")
```
```

Resultado:

En línea: `código corto`

Bloque:
```
print("Hola, mundo!")
```

---

## 7. Citas

### Sintaxis
Usa `>` antes del texto.

### Ejemplo
```markdown
> Esta es una cita.
>> Esta es una cita anidada.
```

Resultado:

> Esta es una cita.
>> Esta es una cita anidada.

---

## 8. Reglas Horizontales

### Sintaxis
Usa tres o más `-`, `*` o `_`.

### Ejemplo
```markdown
---
```

Resultado:

---
