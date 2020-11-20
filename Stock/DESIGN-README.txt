Virtual Stock Trading Application 

Design: 

1. We have designed the whole Application in MVC Architecture. All the back end logic are in the Model. 
Front end comprises of Text based interface which just takes input from User and pass it on to Controller. 
The controller based on the User input will call appropriate method in the model to get the required output. 

2. We have designed controller using Command Design pattern. Each command is a class file and controller 
invoke appropriate command class corresponding to operation to be executed. 

3. We have used Builder design pattern for model creation and it is inner static class in the stock exchange, 
so that it can be instantiated with out creating object at the same time restricting it from unsecured use. 

4. The Model Logic goes something like this, We have a StockExchange which keeps map of portfolio and Portfolio 
is basically collection of Stock Object using Map and each stock object maintains the transaction occurred. 
We have used Map so that we can access the object in no time or less time. 

5. We have used cache concept to fetch the value of stock price using alphavantage API. We are maintaining this
cache in the StockExchange class. We will first check whether the stock entry is there in cache or not. 
If the stock entry is there we will fetch the data from Map, else we will query from alphavantage. So the fetch
is faster in case we are planning to purchase same stock.

6. While enhancing the feature we make sure that Model is not touched and we added new Interface to extend any
update either in controller or in Model.

7. We have modularized the View. Each view i.e each page is a separate Java file and Gui controller holds the 
control between model and view. 

8. View have complete control over the action listener and page loading, while it doesn't have control over model
or controller. For fetching any data to show, the view depeneds on controller and controller talks to model to 
fetch data.

9. Controller is designed in such a way that, even if view changes it will not impact controller and view 
can be replaced with any other view.

10. For addition of new commands, we just added a few command classes and also, we have followed the SOLID
principles. For the addition of new features in the model, we just added a new interface in model thereby,
resulting in not touching the existing functionalities.

11. For Investment amounts Strategy implementation, we created new command classes in the controller and correspondingly
new interface in the model incorporating these changes. View will have seperated classes for each of the features, thus 
enhancing modularity. 
