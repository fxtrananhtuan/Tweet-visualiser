# Tweet-visualiser
Short Sumary 
The goal of this project is to predict events in an area by analyzing trend of the tweets of
users and provide guidance to the concerned authority to take measures, better prepare in
terms of resource allocation to tackle unwanted events.
It is a completely new product. It is a standalone application. And what we create in this
project is a prototype.
The final product provide is a windows desktop application. User can search for
anything by type a keyword in input field and click search button next to it. The system will
automatically send request to Twitter API and get new tweets based on the input keyword,
then extract useful word in all tweets get from Twitter API, then another call to dbpedia will
be made to get reference data for validating the words extracted from tweets. Finally, system
will show all words that pass the validation in the interface of application, I provide
different functions of visualization of the final data, so user can choose whether to see a
force-directed graph which indicates the relationship of all words or a heat map which inform
the location of those tweets that actually provide related valid words. Also charts for detail
understanding of final data is provided as part of visualization function.

![picture2](https://user-images.githubusercontent.com/14042198/35665856-e867924c-077b-11e8-9d41-3dae7dcac76c.jpg)


The key objective for the product is to deliver an interactive system for displaying visualized
tweets. I developed interface receive keywords input from user and send request to
backend program, then a Twitter API call will be made and tweets sentences data sent back
from Twitter API will be analysed and fragmented into keywords, then API call to DBpedia
will retrieve relative data which will be processed by NLP/LDA algorithm and general
meaningful data and send back to the interface. By compare keywords from tweets and data
from DBpedia, we can get rid of useless data and keep those keywords that actually
meaningful and those tweets that provide the meaningful keywords. Multiple visualization
tools are used to display the final data results.

System Architecture
Data Access Layer classes (DAO) along with Data Transfer Layer classes (DTO) will be
create for access database and make API call to get data from Twitter API and dbpedia, also
transfer data from/to web interface. Interface receive input from user, then send request to
DAO, which decide where to get data and where to send data to. Below is the rough
structure graph for application logic.

![3 tie server](https://user-images.githubusercontent.com/14042198/35665980-4f78ba56-077c-11e8-87fd-4ec76d75dbb2.jpg)

DTO - Data Transfer Object : this library have all class of data type
DAO - Data Access Layer : this Library content all connection between application
and outside activity BUS - Business Logic Layer : this Library content all the function
can be use in main application Presentation - this is An Interface for application
Web server - is place have all configure all library for d3 to work
It can be simplified as below
![3 tie layer](https://user-images.githubusercontent.com/14042198/35666057-9a8be734-077c-11e8-81cb-14bb4afc7fc9.jpg)
And below is the high level architecture of the whole application system we
developed in this project:
![picture1](https://user-images.githubusercontent.com/14042198/35666077-b3748c6a-077c-11e8-883a-e0799c5de683.jpg)

Based on desktop application, we also leveraged the power of Amazon cloud
computing and Amazon NoSQL database DynamoDB. Part of system’s function
actually sitting on Amazon EC2 cloud system, and desktop application use those
functions by making an API call to the cloud system we deployed there.
