# Trivia-Json-To-Insert-Commands
This is a simple one page website for fetching trivia question from an API and transforming data to SQL INSERT commands

I made it to avoid manual insertation of question to my MSSQL Database

The website use this Trivia Qustion API to get questions in a JSON format : https://opentdb.com
By using this url structure : https://opentdb.com/api.php?amount=[Amount_Of_Questions]&category=[Category_Id]&difficulty=[Difficulty]&type=[Multiple Answers/True-False Answers]
Specify in the url your parameters
An example url : https://opentdb.com/api.php?amount=10&category=15&difficulty=easy&type=multiple

The information is fetch via AJAX GET request to the chosen url of the API
The information is recieved in JSON format and then each question is transformed into SQL INSERT command.
The order of the question is randomized and the correct answer place also get randomized.

My Database table for questions is of the following structure:
`
--custome types definition
EXEC sp_addtype 'Question_String', 'nvarchar (150)', 'not null'
EXEC sp_addtype 'Question_Option', 'nvarchar (100)', 'not null'
EXEC sp_addtype 'Category_String', 'nvarchar (30)', 'not null'
EXEC sp_addtype 'User_String', 'nvarchar (15)', 'not null'
GO

-- Table definition
CREATE TABLE [Questions] (
	[Id] [smallint] IDENTITY(1,1) NOT NULL  ,
	[Category_Code] [smallint] ,
	[Question_Text] [Question_String],
	[Option1] [Question_Option] ,
	[Option2] [Question_Option] ,
	[Option3] [Question_Option] ,
	[Option4] [Question_Option] ,
	[Answer] [smallint] not null
	 	  
)
`
Please Note That : 
*The new SQL INSERT commands will contain Category_Id field of 5555 
This is usefull for later search & replace of all occurrences of 5555 to your desired Category_Id
*You manualy fix the new SQL INSERT commands by adding ' before all ' occurrences inside a string
for example : 'Mom's Cooking' will end up like this - 'Mom''s Cooking'

Enjoy!
