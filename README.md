# Eat Safe, Love

The `NoSQL_setup.ipynb` sets up and updates the database. The `NoSQL_analysis.ipynb` queries relevant information for analyses and converts results into Pandas DataFrame. The data provided in the `establishments.json` file was imported using Terminal with `mongoimport --type json -d uk_food -c establishments --drop --jsonArray establishments.json`. 

### Set Up and Update Database
* Insert the new halal restaurant opened in Greenwich to the Database.
    `establishments.insert_one(new_restaurant)`
    
* Update the new restauarant with the correct BusineesTypeID.
    `establishments.update_one(new_restaurant, {'$set': {'BusinessTypeID': 1}})`
    
* Drop all establishments that has Dover as their Local Authority from the database. 
    `establishments.delete_many({'LocalAuthorityName': 'Dover'})`
    
* Convert latitude and longitude to decimal numbers.
    `establishments.update_many({}, [{'$set': {'geocode.longitude': {'$toDouble': '$geocode.longitude'}, 
                                               'geocode.latitude': {'$toDouble': '$geocode.latitude'}
                                              }
                                     }
                                    ]
                               )`
    
### Exploratory Analysis
1. 
2.
3. 
4. 