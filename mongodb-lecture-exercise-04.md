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

## 






