Entidad: GtfsShape  
==================  
[Licencia abierta](https://github.com/smart-data-models//dataModel.UrbanMobility/blob/master/GtfsShape/LICENSE.md)  
[documento generado automáticamente](https://docs.google.com/presentation/d/e/2PACX-1vTs-Ng5dIAwkg91oTTUdt8ua7woBXhPnwavZ0FxgR8BsAI_Ek3C5q97Nd94HS8KhP-r_quD4H0fgyt3/pub?start=false&loop=false&delayms=3000#slide=id.gb715ace035_0_60)  
Descripción global: **Formación GTFS**  

## Lista de propiedades  

- `alternateName`: Un nombre alternativo para este artículo  - `dataProvider`: Una secuencia de caracteres que identifica al proveedor de la entidad de datos armonizada.  - `dateCreated`: Marca de tiempo de creación de la entidad. Suele ser asignada por la plataforma de almacenamiento.  - `dateModified`: Marca de tiempo de la última modificación de la entidad. Normalmente será asignada por la plataforma de almacenamiento.  - `description`: Una descripción de este artículo  - `distanceTravelled`: Un array de la distancia recorrida al llegar a cada uno de los puntos que forman la `LineString` o `MultiLineString` que representa esta forma. Deberá coincidir con el mismo número de elementos que la correspondiente `LineString` o `MultiLineString`.  - `id`: Identificador único de la entidad  - `location`: La forma geográfica asociada a esta entidad codificada como GeoJSON `LineString` o `MultiLineString`. Las coordenadas se obtendrán del archivo de alimentación `shapes.txt` según el valor de `shape_id`, `shape_pt_lat`, `shape_pt_lon`, `shape_pt_sequence`.  - `name`: El nombre de este artículo.  - `owner`: Una lista que contiene una secuencia de caracteres codificada en JSON que hace referencia a los identificadores únicos de los propietarios  - `seeAlso`: lista de uri que apuntan a recursos adicionales sobre el artículo  - `source`: Una secuencia de caracteres que indica la fuente original de los datos de la entidad en forma de URL. Se recomienda que sea el nombre de dominio completo del proveedor de origen o la URL del objeto de origen.  - `type`: Tipo de entidad NGSI. Tiene que ser GtfsShape    
Propiedades requeridas  
- `id`  - `location`  - `type`    
Véase [https://developers.google.com/transit/gtfs/reference/#shapestxt](https://developers.google.com/transit/gtfs/reference/#shapestxt). Representa una "forma" GTFS.  
## Descripción del modelo de datos de las propiedades  
Ordenados alfabéticamente (haga clic para ver los detalles)  
<details><summary><strong>full yaml details</strong></summary>    
```yaml  
GtfsShape:    
  description: 'GTFS Shape'    
  properties:    
    alternateName:    
      description: 'An alternative name for this item'    
      type: string    
      x-ngsi:    
        type: Property    
    dataProvider:    
      description: 'A sequence of characters identifying the provider of the harmonised data entity.'    
      type: string    
      x-ngsi:    
        type: Property    
    dateCreated:    
      description: 'Entity creation timestamp. This will usually be allocated by the storage platform.'    
      format: date-time    
      type: string    
      x-ngsi:    
        type: Property    
    dateModified:    
      description: 'Timestamp of the last modification of the entity. This will usually be allocated by the storage platform.'    
      format: date-time    
      type: string    
      x-ngsi:    
        type: Property    
    description:    
      description: 'A description of this item'    
      type: string    
      x-ngsi:    
        type: Property    
    distanceTravelled:    
      description: 'An array of the distance travelled when reaching each of the points that make the `LineString` or `MultiLineString` that represents this shape. It shall match the same number of elements as the corresponding `LineString` or `MultiLineString`.'    
      items:    
        minimum: 0    
        type: number    
      minItems: 1    
      type: array    
      x-ngsi:    
        type: Property    
    id:    
      anyOf: &gtfsshape_-_properties_-_owner_-_items_-_anyof    
        - description: 'Property. Identifier format of any NGSI entity'    
          maxLength: 256    
          minLength: 1    
          pattern: ^[\w\-\.\{\}\$\+\*\[\]`|~^@!,:\\]+$    
          type: string    
        - description: 'Property. Identifier format of any NGSI entity'    
          format: uri    
          type: string    
      description: 'Unique identifier of the entity'    
      x-ngsi:    
        type: Property    
    location:    
      description: 'The geographical shape associated to this entity encoded as GeoJSON `LineString` or `MultiLineString`. The coordinates shall be obtained from the `shapes.txt` feed file as per the value of `shape_id`, `shape_pt_lat`, `shape_pt_lon`, `shape_pt_sequence`.'    
      oneOf:    
        - $id: https://geojson.org/schema/LineString.json    
          $schema: "http://json-schema.org/draft-07/schema#"    
          properties:    
            bbox:    
              items:    
                type: number    
              minItems: 4    
              type: array    
            coordinates:    
              items:    
                items:    
                  type: number    
                minItems: 2    
                type: array    
              minItems: 2    
              type: array    
            type:    
              enum:    
                - LineString    
              type: string    
          required:    
            - type    
            - coordinates    
          title: 'GeoJSON LineString'    
          type: object    
        - $id: https://geojson.org/schema/MultiLineString.json    
          $schema: "http://json-schema.org/draft-07/schema#"    
          properties:    
            bbox:    
              items:    
                type: number    
              minItems: 4    
              type: array    
            coordinates:    
              items:    
                items:    
                  items:    
                    type: number    
                  minItems: 2    
                  type: array    
                minItems: 2    
                type: array    
              type: array    
            type:    
              enum:    
                - MultiLineString    
              type: string    
          required:    
            - type    
            - coordinates    
          title: 'GeoJSON MultiLineString'    
          type: object    
      x-ngsi:    
        type: Geoproperty    
    name:    
      description: 'The name of this item.'    
      type: string    
      x-ngsi:    
        type: Property    
    owner:    
      description: 'A List containing a JSON encoded sequence of characters referencing the unique Ids of the owner(s)'    
      items:    
        anyOf: *gtfsshape_-_properties_-_owner_-_items_-_anyof    
        description: 'Property. Unique identifier of the entity'    
      type: array    
      x-ngsi:    
        type: Property    
    seeAlso:    
      description: 'list of uri pointing to additional resources about the item'    
      oneOf:    
        - items:    
            format: uri    
            type: string    
          minItems: 1    
          type: array    
        - format: uri    
          type: string    
      x-ngsi:    
        type: Property    
    source:    
      description: 'A sequence of characters giving the original source of the entity data as a URL. Recommended to be the fully qualified domain name of the source provider, or the URL to the source object.'    
      type: string    
      x-ngsi:    
        type: Property    
    type:    
      description: 'NGSI Entity type. It has to be GtfsShape'    
      enum:    
        - GtfsShape    
      type: string    
      x-ngsi:    
        type: Property    
  required:    
    - id    
    - type    
    - location    
  type: object    
```  
</details>    
## Ejemplo de carga útil  
#### GtfsShape NGSI-v2 key-values Ejemplo  
Aquí hay un ejemplo de un GtfsShape en formato JSON-LD como valores-clave. Esto es compatible con NGSI-v2 cuando se utiliza `options=keyValues` y devuelve los datos de contexto de una entidad individual.  
```json  
{  
  "id": "urn:ngsi-ld:GtfsShape:101",  
  "type": "GtfsShape",  
  "location": {  
    "type": "LineString",  
    "coordinates": [  
      [-4.421394, 36.73826],  
      [-4.421428, 36.73825],  
      [-4.421505, 36.738186],  
      [-4.421525, 36.738033]  
    ]  
  }  
}  
```  
#### GtfsShape NGSI-v2 normalizado Ejemplo  
Aquí hay un ejemplo de un GtfsShape en formato JSON-LD normalizado. Esto es compatible con NGSI-v2 cuando no se utilizan opciones y devuelve los datos de contexto de una entidad individual.  
```json  
{  
  "id": "urn:ngsi-ld:GtfsShape:101",  
  "type": "GtfsShape",  
  "location": {  
    "type": "geo:json",  
    "value": {  
      "type": "LineString",  
      "coordinates": [  
        [-4.421394, 36.73826],  
        [-4.421428, 36.73825],  
        [-4.421505, 36.738186],  
        [-4.421525, 36.738033]  
      ]  
    }  
  }  
}  
```  
#### GtfsShape NGSI-LD key-values Ejemplo  
Aquí hay un ejemplo de un GtfsShape en formato JSON-LD como valores-clave. Esto es compatible con NGSI-LD cuando se utiliza `options=keyValues` y devuelve los datos de contexto de una entidad individual.  
```json  
{  
  "id": "urn:ngsi-ld:GtfsShape:101",  
  "type": "GtfsShape",  
  "location": {  
    "type": "GeoProperty",  
    "value": {  
      "type": "LineString",  
      "coordinates": [  
        [  
          -4.421394,  
          36.73826  
        ],  
        [  
          -4.421428,  
          36.73825  
        ],  
        [  
          -4.421505,  
          36.738186  
        ],  
        [  
          -4.421525,  
          36.738033  
        ]  
      ]  
    }  
  },  
  "@context": [  
    "https://smartdatamodels.org/context.jsonld",  
    "https://uri.etsi.org/ngsi-ld/v1/ngsi-ld-core-context.jsonld"  
  ]  
}  
```  
#### GtfsShape NGSI-LD normalizado Ejemplo  
Este es un ejemplo de un GtfsShape en formato JSON-LD normalizado. Esto es compatible con NGSI-LD cuando no se utilizan opciones y devuelve los datos de contexto de una entidad individual.  
```json  
{  
  "@context": [  
    "https://smartdatamodels.org/context.jsonld",  
    "https://uri.etsi.org/ngsi-ld/v1/ngsi-ld-core-context.jsonld"  
  ],  
  "id": "urn:ngsi-ld:GtfsShape:101",  
  "location": {  
    "coordinates": [  
      [  
        -4.421394,  
        36.73826  
      ],  
      [  
        -4.421428,  
        36.73825  
      ],  
      [  
        -4.421505,  
        36.738186  
      ],  
      [  
        -4.421525,  
        36.738033  
      ]  
    ],  
    "type": "LineString"  
  },  
  "type": "GtfsShape"  
}  
```  

Consulte [FAQ 10](https://smartdatamodels.org/index.php/faqs/) para obtener una respuesta sobre cómo tratar las unidades de magnitud
