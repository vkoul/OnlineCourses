
# Recommender Systems: Udemy 

Recommender Systems High Level:

- Amazon uses them to look at your past purchases to buy new things. Billions of dollars of sales have resulted from this
- Finds relationships between users and items just based on actions. Shows stuff users might want even before they know it. 
- It also gets used in content, food, music like in Nytimes, Swiggy and Pandora/Spotify
	- This is also based on the properties of the music. Check Pandora's genome project
- Modern search results do personalisation which involves recommendations, it suggests things based on your past search 
- It can have a good impact on company's sales

Understanding through Implicit and Explicit Ratings

- It boils down to understanding you and other users and getting the collective behviour of the users
- How to get the data? Explicit interests
	- Like button
	- ask users for feedback 
- However the problem with the system is 
	- Not everyone is bothered to do this, so there is lot of missing or sparse data for the companies. 
	- everyone has a different opinion in terms of rating. A 4 star for me may mean different thing for you. Some people may be more critical than others

###  Implicit Behaviour
- What people do to deduce the interest of the users
- Your click data speaks a lot about what you prefer, its great data to have. However, just basing recommendations on click data is faulty as
	- But clicking on data is also highly suspectible to fraud as there are a lot of bots
	- People might click on things by accident
	- There are a lot of click-bait items to induce clicking 
- Another way to make recommendations is based on purchasing data, as that is a very strong signal of what people prefer
	- very resistant to fraud. 
	- Amazon has so much data on purchases that they don't require fancy algos
- Consumption is also an important indictor, as Youtube uses it rather than click data 

- Explicit data is great if we convince the users to provide us with the data, [we will do the analysis in the movie-lens data]
- However it is genrally sparse in nature. Implicit is always more data and purchasing data is the best source of the data 
- Good data and lots of it is a key to building a good recommender system

### Top- N Recommender Architecture

- All of the recommenders we have seen is an example of the top-N recommender system. 
- That means they are expected to generate a top list of n-recommendations for a user
- Like on Amazon, they recommend 100 items, with 5 recommendations on one page and 20 pages. Here n = 100
-  Researchers usually focus on predicting what the user might give to a new product. However, in a commercial setting, what matters is what are the top-N things that a user might like
	- This a different problem than the researchers are focussing on 
- The main problem is to put what people will love and not predict what they will hate

- Start with some data stores with interest, purchases, 






