#Mongo DB - lecture 02 - exercise

## Exporting pokemons
	```
	mongoexport -d test -c pokemons -o pokemons.json

	2018-03-13T10:46:44.248-0300	connected to: localhost
	2018-03-13T10:46:44.250-0300	exported 5 records
	```

## Importing pokemons
	```
	mongoimport -d be-mean-pokemons -c pokemons --drop --file pokemons.json 

	2018-03-13T10:48:02.735-0300	connected to: localhost
	2018-03-13T10:48:02.736-0300	dropping: be-mean-pokemons.pokemons
	2018-03-13T10:48:03.501-0300	imported 5 documents
	```

## Creating a database
	```
	use be-mean-pokemons
	```

## Showing collections(tables)
	```
	show collections
	```

## Viewing data from the collection
	```
	db.pokemons.find()
	```

## Assinging an object from the collection
	```
	var query = {name: 'Pikachu'}
	var poke = db.pokemons.findOne(query)
	```

## Modifying data from the assigned object
	```
	var poke.description = 'There\'s nothing cute here'
	db.pokemons.save(poke)
	```



	
