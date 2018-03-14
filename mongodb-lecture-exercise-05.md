#Mongo DB - lecture 03 - exercise

#2. Distinct by 'cuisine' in restaurants
	```
	var p = db.restaurant
	p.distinct('cuisine')
	```

#3. Distinct by 'types' in pokemons
	```
	var p = db.pokemons
	p.distinct('types')
	```

#4. The first 3 pages with .limit() and .skip() of pokemons (5 to 5)
	```
	p.find().limit(5).skip(0)
	p.find().limit(5).skip(5)
	p.find().limit(5).skip(10)
	```

#5. Group or Aggregate counting the quantity of each type of pokemon
	```
	db.pokemons.group({
  		initial: { total: 0 },
    		reduce: function (curr, result) {
        		curr.types.forEach(function (type) {
            			if (result[type]) {
                			result[type]++;
            			} else { result[type] = 1; }
            			result.total++;
        		});
   		 }
	});	
	```	

#6. Do the 3 following counts in pokemons
-> all 
-> only fire type
-> defense greater than 70
	```
	p.count()	
	p.find({types: {$in:['fire']}}).count()
	p.find({defense: {$gt: 70}}).count()
	```
