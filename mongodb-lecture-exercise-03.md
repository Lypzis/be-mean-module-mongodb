# Mongo DB - lecture 03 - exercise

## Listing all pokemons with height less than 0.5 
	```
	var query = {height: {$lt: 0.5}}
	db.pokemons.find(query)
	```

## Listing all pokemons with height greater than 0.5
	```
	var query = {height:{$gt: 0.5}}
	db.pokemons.find(query)
	```

## Listing all pokemons with height greater or equal 0.5 and of type grass

	```
	var query = {$and:[{height:{$gte: 0.5}},{type: 'grama'}]}
	db.pokemons.find(query)
	```
	 
## Listing all pokemons with name 'Pikachu' or attack less or equal than 0.5
	```
	var query = {$or: [{name:'Pikachu'},{attack:{$lte: 0.5}}]}
	db.pokemons.find(query)
	```

## Listing all pokemons with attack greater or equal than 48 and with height less than or equal 0.5
	```
	var query = {$and: [{attack:{$gte:48}},{height: {$lte: 0.5}}]}
	db.pokemons.find(query)
	```
