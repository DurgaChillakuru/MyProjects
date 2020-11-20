Steps to follow:
------------------

1) Download the jar file from the server.
2) Make sure you have Java installed on your machine.
3) Navigate to the location where you have saved your jar application file in the command prompt and run the jar by the following command.
4) Type- "java -jar Stock.jar gui" for gui view .
Type- "java -jar Stock.jar cli" for command line console.
5) Now, play with the stock simulator as per the instructions in the menu.
6) The Console prompt will look as follows:-
---------------MENU------------
Press 1 for Creating a portfolio
Press 2 to buy stocks
Press 3 to view portfolio
Press 4 to view full portfolio
Press 5 to list portfolios
Press 6 to get the total cost basis of a portfolio
Press 7 to get the total value of a portfolio
Press 8 to buy Stocks with money
Press 9 to Save the portfolio
Press 10 to Retrieve the portfolio
Press 11 to Add stocks to existing portfolio
Press 12 to Invest in a portfolio with varying weights
Press 13 to Invest in a portfolio with equal weights
Press 14 to Create and save a Strategy
Press 15 to Retrieve a strategy
Press 16 to Invest in a portfolio with varying weights periodically
Press q/Q to exit
Please enter the command:

6) You can choose any of the options.
	say, For creating portfolio, press 1
7) Based on the command selected, you will be prompted to enter some additional details based on
the option chosen.
	say, for buying a stock, the command prompt will look like-
Please enter the command:

8
Enter the ticker symbol:

goog
Enter the portfolio name :

chandu
Enter the amount in dollars: 

10000000
Press Yes to buy with commission or any other key apart from Yes to exit

yes
Enter the commission amount in dollars less than 10 dollars: 

1
Enter the date(dd) of the month at which the stock has to be bought:

12
Enter the month(mm) of the date at which the stock has to be bought:

12
Enter the year(yyyy) of the date at which the stock has to be bought:

2016 
Stocks has been bought successfully and the remaining amount 737.3700000010431 transferred back

8) In order to quit type- q/Q.

Important Notes:
Buying stocks on holiday is not allowed.
Periodic investment strategies may call for executing a transaction on a holiday. In this case, our program chooses the next available day to invest. 
For periodic investments, our program considers the end-of-day prices. 
If the stocks are bought or a transaction is made, then the user has an option to enter commission amount for the same, or he may not select add commission amount.
The commission amount is deducted from the amount to invest and the number of shares are bought from the remaining amount to invest.
Total cost basis of a portfolio will remain the same after the purchase date except for periodical investments.
Trying to determine total value basis of a portfolio on a Holiday(say, saturday) will return you the portfolio value on Friday.
The user has the option to split equally while he is investing periodically also or he can give his own ratios for the stocks.
For investments strategies also, the user can include/exclude the commission amount.

Assumptions for the new features:
--------------------------------------------
For Add Stocks to existing portfolio command, the user is expected to create a portfolio first using create portfolio command, and then only he can add stocks to it.
For one time transactional commands like ("Invest in a portfolio with varying weights" and "Invest in a portfolio with Equal weights"), the user is expected to first create a portfolio using create command and then he should be adding stocks to that portfolio using "Add stock to portfolio" command before calling the transactional commands.
The user cannot execute invest periodically on an existing portfolio.
The user cannot retrieve an investment strategy and apply it to an existing portfolio.
When the user creates and saves a strategy, the investment strategy will be stored in a JSON file in same folder as the jar file is. 
The user needs to give the input for the ratio's as 40 for 40%, 25 for 25%.

We are maintaing a cache, storing the api results for a particular stock after one retreival. Say, for once GOOG stock is being fetched, then when trying to add GOOG stock to a portfolio will not fetch from API. A cache is being maintained.
GUI 
Command to run the GUI is mentioned above. Once customer launched the GUI, The UI is self explanatory. We are posing some restriction and is below
1. All the fields are mandatory and if not specified Error dialogue will be displayed.
2. Commision amount is between 1 and 9 per transaction(inclusive). 
3. Date, Month and Year format is explained in GUI itself. 
4. While investing some amount in Stock, Since we are not maintaining the User information and account, We are buying the nearest integer volume
of share and returning the remaining amount to user. For ex. if the goog share price is 1000 today and user invested 1500, then we are buying 
one share and returning 500 back.
5. When we save the portfolio, it will create folder named "portfolio" under the same location where user is running the command and store 
the content in JSON file, with portfolio name user provided. 
6. While retriving the portfolio, if the same portfolio name is there, then it will override the content with saved data.  
