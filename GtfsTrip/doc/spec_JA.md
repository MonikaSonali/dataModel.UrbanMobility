エンティティGtfsTrip  
==============








- `hasRoute`  



<details><summary><strong>full yaml details</strong></summary>    

GtfsTrip:    
  description: 'GTFS Trip'    
  properties:    
    alternateName:    
      description: 'An alternative name for this item'    
      type: string    
      x-ngsi:    
        type: Property    
    bikesAllowed:    
      description: "Same as GTFS `bikes_allowed`. Enum:'0, 1, 2'. See [GTFS](https://developers.google.com/transit/gtfs/reference/#tripstxt)"    
      enum:    
        - 0    
        - 1    
        - 2    
      type: number    
      x-ngsi:    
        model: https://schema.org/Number    
        type: Property    
    block:    
      description: 'Same as GTFS `block_id`'    
      type: string    
      x-ngsi:    
        model: https://schema.org/Text.    
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
    direction:    
      description: 'Same as GTFS `direction_id`. Enum:''0, 1'''    
      enum:    
        - 0    
        - 1    
      type: number    
      x-ngsi:    
        model: https://schema.org/Number    
        type: Property    
    hasRoute:    
      anyOf:    
        - description: 'Property. Identifier format of any NGSI entity'    
          maxLength: 256    
          minLength: 1    
          pattern: ^[\w\-\.\{\}\$\+\*\[\]`|~^@!,:\\]+$    
          type: string    
        - description: 'Property. Identifier format of any NGSI entity'    
          format: uri    
          type: string    
      description: 'Same as `route_id`. It shall point to an Entity of type GtfsRoute'    
      type: string    
      x-ngsi:    
        model: http://schema.org/URL    
        type: Relationship    
    hasService:    
      anyOf:    
        - description: 'Property. Identifier format of any NGSI entity'    
          maxLength: 256    
          minLength: 1    
          pattern: ^[\w\-\.\{\}\$\+\*\[\]`|~^@!,:\\]+$    
          type: string    
        - description: 'Property. Identifier format of any NGSI entity'    
          format: uri    
          type: string    
      description: 'Same as GTFS `service_id`. It shall point to an Entity of type GtfsService'    
      x-ngsi:    
        model: http://schema.org/URL    
        type: Relationship    
    hasShape:    
      anyOf:    
        - description: 'Property. Identifier format of any NGSI entity'    
          maxLength: 256    
          minLength: 1    
          pattern: ^[\w\-\.\{\}\$\+\*\[\]`|~^@!,:\\]+$    
          type: string    
        - description: 'Property. Identifier format of any NGSI entity'    
          format: uri    
          type: string    
      description: 'Same as GTFS `shape_id`. It shall point to an Entity of type GtfsShape'    
      x-ngsi:    
        model: http://schema.org/URL    
        type: Relationship    
    headSign:    
      description: 'Same as GTFS `trip_headsign`'    
      type: string    
      x-ngsi:    
        model: https://schema.org/Text.    
        type: Property    
    id:    
      anyOf: &gtfstrip_-_properties_-_owner_-_items_-_anyof    
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
    name:    
      description: 'The name of this item.'    
      type: string    
      x-ngsi:    
        type: Property    
    owner:    
      description: 'A List containing a JSON encoded sequence of characters referencing the unique Ids of the owner(s)'    
      items:    
        anyOf: *gtfstrip_-_properties_-_owner_-_items_-_anyof    
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
    shortName:    
      description: 'Same as GTFS `trip_short_name`'    
      type: string    
      x-ngsi:    
        model: https://schema.org/Text.    
        type: Property    
    source:    
      description: 'A sequence of characters giving the original source of the entity data as a URL. Recommended to be the fully qualified domain name of the source provider, or the URL to the source object.'    
      type: string    
      x-ngsi:    
        type: Property    
    type:    
      description: 'NGSI Entity type. It has to be GtfsTrip'    
      enum:    
        - GtfsTrip    
      type: string    
      x-ngsi:    
        type: Property    
    wheelChairAccessible:    
      description: 'Same as GTFS `wheelchair_accessible`. Enum:''0, 1, 2'''    
      enum:    
        - 0    
        - 1    
        - 2    
      type: number    
      x-ngsi:    
        model: https://schema.org/Number    
        type: Property    
  required:    
    - id    
    - type    
    - hasRoute    
    - hasService    
  type: object    
```  
</details>    





  "id": "urn:ngsi-ld:GtfsTrip:Spain:Malaga:1",  
  "type": "GtfsTrip",  
  "hasService": "urn:ngsi-ld:GtfsService:Malaga_LAB",  
  "headSign": "San Andrés",  
  "direction": 0,  
  "hasRoute": "urn:ngsi-ld:GtfsRoute:Spain:Malaga:1",  
  "hasShape": "urn:ngsi-ld:GtfsShape:Shape01"  
}  
```  




  "id": "urn:ngsi-ld:GtfsTrip:Spain:Malaga:1",  
  "type": "GtfsTrip",  
  "direction": {  
    "value": 0  
  },  
  "headSign": {  
    "value": "San Andr\u00e9s"  
  },  
  "hasRoute": {  
    "type": "Relationship",  
    "value": "urn:ngsi-ld:GtfsRoute:Spain:Malaga:1"  
  },  
  "hasService": {  
    "type": "Relationship",  
    "value": "urn:ngsi-ld:GtfsService:Malaga_LAB"  
  },  
  "hasShape": {  
    "type": "Relationship",  
    "value": "urn:ngsi-ld:GtfsShape:Shape01"  
  }  
}  
```  




  "id": "urn:ngsi-ld:GtfsTrip:Spain:Malaga:1",  
  "type": "GtfsTrip",  
  "direction": {  
    "type": "Property",  
    "value": 0  
  },  
  "headSign": {  
    "type": "Property",  
    "value": "San Andr\u00e9s"  
  },  
  "hasRoute": {  
    "type": "Relationship",  
    "object": "urn:ngsi-ld:GtfsRoute:Spain:Malaga:1"  
  },  
  "hasService": {  
    "type": "Relationship",  
    "object": "urn:ngsi-ld:GtfsService:Malaga_LAB"  
  },  
  "hasShape": {  
    "type": "Relationship",  
    "object": "urn:ngsi-ld:GtfsShape:Shape01"  
  },  
  "@context": [  
    "https://smartdatamodels.org/context.jsonld",  
    "https://uri.etsi.org/ngsi-ld/v1/ngsi-ld-core-context.jsonld"  
  ]  
}  
```  




  "@context": [  
    "https://smartdatamodels.org/context.jsonld",  
    "https://uri.etsi.org/ngsi-ld/v1/ngsi-ld-core-context.jsonld"  
  ],  
  "direction": 0,  
  "hasRoute": "urn:ngsi-ld:GtfsRoute:Spain:Malaga:1",  
  "hasService": "urn:ngsi-ld:GtfsService:Malaga_LAB",  
  "hasShape": "urn:ngsi-ld:GtfsShape:Shape01",  
  "headSign": "San Andr\u00e9s",  
  "id": "urn:ngsi-ld:GtfsTrip:Spain:Malaga:1",  
  "type": "GtfsTrip"  
}  
```  

