# nosql-challenge

## Instructions

The UK Food Standards Agency evaluates various establishments across the United Kingdom, and gives them a food hygiene rating. You've been contracted by the editors of a food magazine, Eat Safe, Love, to evaluate some of the ratings data in order to help their journalists and food critics decide where to focus future articles.

## Contents

- Resources - Directory containing our json file that will be imported for the assignment.
- NoSQL_setup.ipynb - Notebook where we import and clean the data to be used int he analysis. 
- NoSQL_analysis.ipynb - Notebook containing our analysis.

## Notes

- Used "mongoimport --type json -d uk_food -c establishments --drop --jsonArray establishments.json" to import the dataset

## Resources

https://www.geeksforgeeks.org/mongodb-updatemany-method-db-collection-updatemany/
https://www.mongodb.com/docs/manual/reference/method/db.collection.updateMany/

Used the websites above to derive the proper syntax to change the data type from string to decimal. Originally I set the type to double but on the advice of an ASK BCS agent I corrected it.

``` 
establishments.update_many({}, [{"$set": {"geocode.longitude": {"$toDecimal" :"$geocode.longitude" },
                                          "geocode.latitude": {"$toDecimal" :"$geocode.latitude"}}}])
```
