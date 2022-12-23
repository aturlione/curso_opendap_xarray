# CHAMBO.Apiprocess

Api en la que se ejecutan geoprocesos.

## MELCA

El módulo MELCA ejecuta el modelo hidrológico en todas las subcuencas que componen chambo
y devuelve los resultados en formato JSON para los siguientes campos: "area", "area_ac",
"ce_ac",	"id",	"petmed",	"petmed_ac",	"precmed",	"precmed_ac",	"q20_ac",	"q50_ac",	"q80_ac",	"qmed",	"qmed_ac" y "smax".

Para la ejecución de este módulo necesitamos tener los siguientes parámetros:

```
{
  "initial date": "00-01-01",
  "final date": "19-31-12",
}
```

El formato de la fecha debe ser "yy-dd-mm".


## MANADGEMENT
EL módulo MANADGEMENT ejecuta tanto el módulo MELCA cómo el módulo de gestión. 
Para la ejecución de este módulo necesitamos tener los siguientes parámetros:

```
{
  "sub-catchment id": 73,
  "initial date": "00-01-01",
  "final date": "19-31-12",
  "series": true
}
```

Los resultados se devuelven en formato JSON, cuando 
series=true los resultados son las series temporales de "qdsim", "qnat", "qnatac" y "qout" para la subcuenca de id dado. Cuando series=false, se obtienen los resultados para "lon", "IAC1", "IAC2", "Gar", "Val_unit_med" y  "Val_agr" para todas las subcuencas.


## Quality

El módulo QUALITY ejecuta el modelo hidrológico, el modelo de gestión y el modelo de calidad.
Para la ejecución de este necesitamos tener los siguientes parámetros:

```
{
  "sub-catchment id": 73,
  "initial date": "00-01-01",
  "final date": "19-31-12",
  "series": true
}
```

Los datos se devuelven en formato JSON, cuando 
series=true los resultados son las series temporales de "qdt" y  "qvt" para la subcuenca de id dado. Cuando series=false, se obtienen los resultados para "Smed",	"conc_p50",	"conc_p90" y	"dSmed" para todas las subcuencas.

## Custom Methods

Para ejecutar los módulos "Custom", es necesario introducir los ficheros que contienen las series temporales para la precipitación, temperatura máxima y mínima, demandas y los parámetros del modelo MELCA por tramos. El formato de las tablas debe ser el mismo que en las tablas de ejemplo dentro de la carpeta "Custom".

