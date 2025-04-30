1) 

 
{ 

  "properties.amenity": "hospital", 

  "geometry": { 

    "$near": { 

      "$geometry": { 

        "type": "Point", 

        "coordinates": [23.332956, 42.695833] 

      } 

    } 

  } 

} 

 

2) 

 

{ 

  "$or": [ 

    { "properties.leisure": "park" }, 

    { "properties.amenity": "park" } 

  ], 

  "geometry": { 

    "$near": { 

      "$geometry": { 

        "type": "Point", 

        "coordinates": [23.332956, 42.695833] 

      }, 

      "$maxDistance": 3000 

    } 

  } 

} 

 

3) 

{ 

  "geometry": { 

    "$geoWithin": { 

      "$geometry": { 

        "type": "Polygon", 

        "coordinates": [[ 

          [23.3180, 42.6740], 

          [23.3420, 42.6740], 

          [23.3420, 42.6880], 

          [23.3180, 42.6880], 

          [23.3180, 42.6740] 

        ]] 

      } 

    } 

  } 

} 

 

4) 

 

{ 

  "properties.amenity": "bus_station", 

  "geometry": { 

    "$geoIntersects": { 

      "$geometry": { 

        "type": "LineString", 

        "coordinates": [ 

          [23.2719271, 42.6727419],   // Ovcha Kupel 

          [23.3162766, 42.7267681]    // Sofia North 

        ] 

      } 

    } 

  } 

} 

 

5) 

{ 

  "properties.name:en": /National/i, 

  "properties.tourism": "museum", 

  "geometry": { 

    "$near": { 

      "$geometry": { 

        "type": "Point", 

        "coordinates": [23.3199, 42.6983] 

      }, 

      "$maxDistance": 1000 

    } 

  } 

} 

 

6) 

{ 

  "$or": [ 

    { "properties.amenity": "shelter" }, 

    { "properties.amenity": "clinic" } 

  ], 

  "geometry": { 

    "$near": { 

      "$geometry": { 

        "type": "Point", 

        "coordinates": [23.3199, 42.6983] 

      }, 

      "$minDistance": 5000 

    } 

  } 

} 

 

 
