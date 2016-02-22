# Using pynswers #

Using pynswers is very easy. It is just one file Answers.py, with one class having four methods.

Yahoo answers has four available calls
  1. questionSearch
  1. getByCategory
  1. getQuestion
  1. getByUser
Pynswers has four methods called(wonder!)
  1. questionSearch
  1. getByCategory
  1. getQuestion
  1. getByUser

Each method returns a list of dictionaries.

To use Pynswers, import the class and
```
>>>app = Answers()
>>>app.appid = 'your secret yahoo appid'
>>>questions = app.questionSearch({'query':'cats',})
>>>print questions[0]['UserId']
```

## questionSearch ##
Find questions that match your query.
Parameters listed [here](http://developer.yahoo.com/answers/V1/questionSearch.html) are accepted. query is a required parameter.
### usage ###
```
>>>app = Answers()
>>>app.appid = 'your secret yahoo appid'
>>>app.questionSearch({'query':'cats',})
```

## getByCategory ##
List questions from one of our hundreds of categories, filtered by type. You'll need the category name or ID, which you can get from questionSearch.
Parameters listed [here](http://developer.yahoo.com/answers/V1/getByCategory.html) are accepted. Either category\_id or category\_name is a required.
### Usage ###
```
>>>app.getByCategory({'category_id':'396546304'})
```
## getQuestion ##
Found an interesting question? getQuestion lists all the details for every answer to the question ID you specify, including the best answer, if it's been chosen. Get that question ID from questionSearch or getByCategory.
Parameters listed [here](http://developer.yahoo.com/answers/V1/getQuestion.html) are accepted. question\_id is a required parameter.
### Usage ###
```
>>>app.getQuestion({'question_id':'20070331070321AAlyopp'})
```
## getByUser ##
List questions from specific users on Yahoo! Answers. You'll need the user id, which you can get from any of the other services listed above.
Parameters listed [here](http://developer.yahoo.com/answers/V1/getByUser.html) are accepted. user\_id is a required parameter.





