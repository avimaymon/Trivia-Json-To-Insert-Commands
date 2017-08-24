# Trivia-Json-To-Insert-Commands
* ### This is a simple one page website for fetching trivia question from an API and transforming data to SQL INSERT commands

* ### The purpose of this project is to avoid manual insertation of questions to my MSSQL Database

* ### This website use this Trivia Qustion API to get questions in a JSON format : 
#### https://opentdb.com 
## By using this url structure : 
#### https://opentdb.com/api.php?amount=[Amount_Of_Questions]&category=[Category_Id]&difficulty=[Difficulty]&type=[Multiple Answers/True-False Answers]
### Specify your parameters in the index.html url field
#### An example url : https://opentdb.com/api.php?amount=10&category=15&difficulty=easy&type=multiple
## Information Handling
* ### The information is fetch via AJAX GET request to the chosen url of the API
* ### The information is recieved in JSON format and then each question is transformed into SQL INSERT command.
* ### The order of the question is randomized and the correct answer place also get randomized.

## Questions table structure:


![myTable](http://i.imgur.com/JippIoR.png)

## Please Note That : 
* ### The new SQL INSERT commands will contain Category_Id field of 5555 
* ### This is usefull for later search & replace of all occurrences of 5555 to your desired Category_Id
* ### You manualy fix the new SQL INSERT commands by adding ' before all ' occurrences inside a string
* ### for example : 'Mom's Cooking' will end up like this - 'Mom''s Cooking'

# Enjoy!
