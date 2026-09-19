# Contuna Alertas

Fichero JSON con alertas de plagas, enfermedades y clima adverso relevantes para
una explotación olivarera en **Corte de Peleas, Badajoz, Extremadura** (España).

`alertas.json` lo actualiza una rutina automática diaria que busca noticias
reales (boletines fitosanitarios, avisos AEMET, prensa agraria) y añade
entradas nuevas cuando encuentra algo relevante y verificable. Nunca debe
contener información inventada: si no hay nada nuevo o fiable, el fichero se
deja sin cambios ese día.

La app [Contuna](../contuna) lee este fichero (`alertas.json` en `main`) y
combina las alertas con su propia base de datos local.

## Esquema de cada entrada

```json
{
  "fecha": "YYYY-MM-DD",
  "tipo": "plaga | clima | otro",
  "titulo": "Resumen corto",
  "resumen": "2-3 frases con el contexto y la recomendación",
  "fuente": "Nombre de la fuente (fecha)",
  "url": "Enlace a la fuente original"
}
```

Se mantiene una lista con las ~30 entradas más recientes.
