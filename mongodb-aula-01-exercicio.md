#Mongo DB - Lecture 01 - Exercise

## Importing restaurants

	```
	mongoimport -d be-mean -c restaurant --drop --file myJson.json 

	2018-03-13T09:30:03.598-0300	connected to: localhost
	2018-03-13T09:30:03.598-0300	dropping: be-mean.restaurant
	2018-03-13T09:30:04.857-0300	imported 25359 documents

	```
## Counting the restaurants
	
	```
	mongo
	use be-mean
	db.restaurant.find({}).count()
	

	
