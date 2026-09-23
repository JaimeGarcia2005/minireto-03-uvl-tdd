# Diario TDD

## Ciclo 1

### Red
- Prueba añadida: No se ha añadido ninguna prueba nueva, ya estaba añadida, test_one_feature_is_tiny().
- Técnica de diseño de pruebas empleada: Valor límite
- Motivo de elegir este caso: Probar que un solo elemento sea tiny, que es un caso límite para tiny.
- Fallo observado: Devuelve error

### Green
- Código mínimo escrito: def classify_model_size(feature_count: int) -> str:
    return "tiny"

- Resultado de las pruebas: Una vez añadido el código, pasa correctamente

### Refactor
- Mejora realizada, o motivo por el que no era necesaria: No hay nada que mejorar, por tanto, no se ha hecho.

---

## Ciclo 2

### Red
- Prueba añadida: Se ha añadido la prueba test_zero_fetures_is_invalid().
- Técnica de diseño de pruebas empleada: Valor límite
- Motivo de elegir este caso: Rechazar los que tengan el valor 0, es decir, no válidos.
- Fallo observado: No estaba implementado el ValueError de la prueba.

### Green
- Código mínimo escrito: def classify_model_size(feature_count: int) -> str:
    if feature_count < 1:
        raise ValueError("feature_count debe ser positivo")

- Resultado de las pruebas: Una vez añadido el código, pasa correctamente

### Refactor
- Mejora realizada, o motivo por el que no era necesaria: No hay nada que mejorar, por tanto, no se ha hecho.


---

## Ciclo 3

### Red
- Prueba añadida: Se ha añadido la prueba test_five_features_is_tiny() y test_six_features_is_small().
- Técnica de diseño de pruebas empleada: Valor límite de las particiones equivalentes
- Motivo de elegir este caso: Con esto observamos el final de la partición tiny, y el principio de la partición small.
- Fallo observado: Ambas dan fallos al no tener contemplado el código estos casos.

### Green
- Código mínimo escrito: def classify_model_size(feature_count: int) -> str:
    if feature_count <= 5:
        return "tiny"
    return "small"

    (Mantenemos el if del caso < 1)

- Resultado de las pruebas: Una vez añadido el código, pasa correctamente

### Refactor
- Mejora realizada, o motivo por el que no era necesaria: No hay nada que mejorar, por tanto, no se ha hecho.
