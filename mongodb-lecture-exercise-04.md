#Mongo DB - lecture 04 - exercise

## Adding 2 attack at the same time to the following pokemons: Pikachu, Squirtle, Bulbassauro e Charmander
	```
	var query = {name: {$in:[/pikachu/i, /squirtle/i, /bulbassauro/i, /charmander/i]}}
	var mod = {$inc:{attack: 2}}
	var option = {multi:true}
	db.pokemons.update(query, mod, option)
	```

## Adding a move in all pokemons: 'desvio'.
	```
	var query = {}
	var mod = {$push: {moves: 'desvio'}}
	db.pokemons.update(query, mod, option)
	```

## Adding the pokemon 'AindaNaoExisteMon' case he doesn't exist, with all data set to null and the description: 'Sem maiores informações'
	```
	var query = {name: 'AindaNaoExisteMon'}
	var mod = {$setOnInsert: { active: null, attack: null, defense: null, height:null, description: 'Sem maiores informações'}}
	db.pokemons.update(query, mod, option)
	```

## Search all the pokemons who own the attack 'investida' and one more that you hava added, choose your favorite
	```
	var query = {moves: {$in: [ /inve.*/i, /nao.*/i] }
	db.pokemons.find(query)
	```

## Search all the pokemons who own an attack added, choose your favorite
	```
	var query = {name: {$in:[/pikachu/i, /squirtle/i, /bulbassauro/i, /charmander/i]}}
	var query = {name: /pikachu/i}
	db.pokemons.find(query)
	```	

## Search for all pokemons without type eletric
	```
	var query = {type: {$nin: ['eletric']}}
	db.pokemons.find(query)	
	```

## Search for all pokemons who own the attack 'investida' and own defense not less or equal to 49
	```
	var query = {$and: [{moves: {$in:['investida']}}, {defense: {$not: {$lte: 49}}}]}
	db.pokemons.find(query)
	```

## Remove all pokemons with type water and attack less than 50
	```
	var query = {$and: [{type:'água'}, {attack : {$lt:50}}]}
	db.pokemons.remove(query)
 






