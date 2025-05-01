mongoimport --db=bulgaria_ego --collection=places --file=features.json --jsonArray


1/
db.places.find({ "properties.amenity": "hospital", "geometry": { $near: { $geometry: { type: "Point", coordinates: [23.332956, 42.695833] } } } })
2/
db.places.find({ $or: [ { "properties.leisure": "bar" }, { "properties.amenity": "bar" } ], "geometry": { $near: { $geometry: { type: "Point", coordinates: [23.332956, 42.695833] }, $maxDistance: 3000 } } })
3/
db.places.find({ "geometry": { $geoWithin: { $geometry: { type: "Polygon", coordinates: [[[23.3180, 42.6740], [23.3420, 42.6740], [23.3420, 42.6880], [23.3180, 42.6880], [23.3180, 42.6740]]] } } } })
4/
db.places.find({ "properties.amenity": "bus_station", "geometry": { $geoIntersects: { $geometry: { type: "LineString", coordinates: [ [23.2719271, 42.6727419], [23.3162766, 42.7267681] ] } } } })
5/
db.places.find({ "properties.name:en": /National/i, "properties.tourism": "museum", "geometry": { $near: { $geometry: { type: "Point", coordinates: [23.3199, 42.6983] }, $maxDistance: 1000 } } })
6/
db.places.find({ $or: [ { "properties.amenity": "shelter" }, { "properties.amenity": "clinic" } ], "geometry": { $near: { $geometry: { type: "Point", coordinates: [23.3199, 42.6983] }, $minDistance: 5000 } } })
