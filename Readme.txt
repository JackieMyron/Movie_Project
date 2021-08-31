-----------
Information
-----------

I used the IDE NetBeans to create and run this program
It will also use GlassFish Server
In order to run the code you will need to create a Database called MovieDB and then execute the SQL.txt file in order to 
populate the Database.

-----------
Inputs
-----------

StartPage.xhtml
The 5 digit zip codes to enter are 75080 & 75081

PaymentScreen.xhtml
This will take any 16 digit number

-----------
Web Pages
-----------

StartPage.xhtml
This web page is a form with output label that says "Enter ZipCode: ", an input box for the zip code with a validation aspect
that makes sure the length of the zip code is 5, and a button that says done that moves to the next page "ShowTheaters.xhtml". This 
also has a CSS style sheet at the top that corresponds to each aspect changed.

ShowTheaters.xhtml
This web page is a form with a data table that shows the theater that corresponds to the zip code entered as well as a command
link that when clicked on will take you to the next page "showMovies.xhtml". It also has a back button that will take you to the 
previous page. This also has a CSS style sheet at the top that corresponds to each aspect changed.

showMovies.xhtml
This web page is a form with a data table that shows the movie that corresponds to the theater picked as well as a command
link that when clicked on will take you to the next page "PaymentScreen.xhtml". This page has the information about each
movie shown such as a description and start time. It also has a back button that will take you to the previous page. 
This also has a CSS style sheet at the top that corresponds to each aspect changed.

PaymentScreen.xhtml
This web page has a panel grid that shows that title, start time, as well as the price of the movie chosen. It also has a place
to enter a credit card number in which depending on if the number is 16 digits a message will appear under it saying if it was
successful or not. It has a done button and a back button to go to the previous page. This also has a CSS style sheet at the top
that corresponds to each aspect changed.

-----------
Java Pages
-----------

StartPageBean.java
This is a JSF CDI bean for StartPage.xhtml in which there are a constructer and getters and setters for the 2 variables
that could be used, The EJB and the variable that contains the zip code entered on the start page.

ShowTheatersBean.java
This is a JSF CDI bean for ShowTheaters.xhtml in which there are a constructer and getters and setters for the 2 variables
that could be used, The EJB and the variable that contains the zip code that is needed for the other methods. It has a method
called showTheaters in which when evoked it will transfer the given zip code into this bean’s zip code variable and switch
the page to the ShowTheaters.xhtml page. The other method is called TheaterList in which the method will call the EJB method
with the zip code variable in order to return a list of theaters that correspond to the zip code.

ShowMoviesBean.java
This is a JSF CDI bean for ShowMovies.xhtml in which there are a constructer and getters and setters for the 3 variables that
could be used which are the EJB, the variable that contains the id, and the variable that contains the theater, all of which
is needed for the other methods. It has a method called showMovies in which when evoked it will transfer the given theater into
this bean’s theater variable and switch the page to the ShowMovies.xhtml page. The other method is called MovieList in which
the method will call the EJB method with the theater variable in order to return a list of movies that correspond to the theater.

PaymentScreenBean.java
This is a JSF CDI bean for PaymentScreen.xhtml in which there are a constructer and getters and setters for the 4 variables that
could be used which are the EJB, the variable that contains the movie, the variable that contains the message, and the variable
that contains the credit card number, all of which is needed for the other methods. It has a method called paymentScreen in which
when evoked it will transfer the given movie into this bean’s movie variable and switch the page to the PaymentScreen.xhtml page.
The other method is called validate which is where it will check that the credit card number variable is 16 digits long.

MoviesEJB.java
This is a EJB bean in which there is a persistence method, a method that will find theaters based on a zip by invoking a query
in the Theaters.java page and return the resulting list, and a method that will find movies based on a theater by invoking a
query in the Movies.java page and return the resulting list.

Movies.java
This is an entity that was created automatically by our database MovieDB. I added a query to find movies based on the theater id.

Theaters.java
This is an entity that was created automatically by our database MovieDB. 

