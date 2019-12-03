TapSearch (MVC)
A simple program called TapSearch that takes in multiple paragraphs of text, assigns a unique ID To each paragraph and stores the words to paragraph mappings on an inverted index. This is similar to what elasticsearch does. This paragraph can also be referred to as a ‘document’. Given a word to search for, it lists out the top 10 paragraphs in which the word is present.

Tokenize to words by splitting at whitespace

Convert all words to lowercase

Index these words against the documents they are from

Generate a unique ID for every document that is index

A paragraph is defined by two newline characters

Tech stack:
1.NodeJS
2.Express
3.MongoDB
4.Postman
5.Horeku
Base URL : https://example67.herokuapp.com/

Table of Contents

Save paragraphs

Search words in paragraphs

Remove paragraphs

Reference : https://docs.mongodb.com/manual/core/index-text/#create-text-index
db.paragraphs.createIndex( { tags: "text" } )

API Documentation
Save paragraphs
Index a given document (After having split the input into paragraphs a.k.a document)

Request
https://example67.herokuapp.com/home/index

Headers
Content-Type : application/json

HTTP method

POST

{
    
    "paragraphs" : string
    
}
Response
{

    "message": string
    
}
Search words in paragraphs
Given a word, search for it and retrieve the top 10 paragraphs (Documents) that contain it.

Request

https://example67.herokuapp.com/home/search

Headers
Content-Type : application/json

HTTP method

POST

{

    "query" : string
    
}
Response

{
    "paragraphs": {
        "tags" : array,
        "_id" : string,
        "text" : string,
        
    }
}
Remove paragraphs

Clear the index and all indexed documents.

Request
https://example67.herokuapp.com/home/clear

Headers
Content-Type : application/json

HTTP method
GET

Response

{
    "message": string
}
