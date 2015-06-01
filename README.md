# Overview
This project investigates the technologies used to implement websites, and how they can be exploited to enhance their efficiency. It then looks at their architecture by outlining their client-server interrelated elements. Finally, it explores a different set of technologies that could be applied to offer a comparable solution.

# The Task
The project required that I build a small set of web pages for the Open University Running Club (OURC). There are 3 web pages that I needed to develop to demonstrate:

1.	Use of a form to submit data to a database table where the data is validated on the client side. 

2.	Use of a PHP web page to receive form data and store this data in a database table. 

3.	Use of a PHP web page to retrieve and display data from a database table in a format specified by data from a form. 

# Form to submit data to a database 
The operation of the form to submit data to a database table is outlined here. The form contains a range of fields for entering data. This data needs to be validated on the client side using JavaScript. When the form is submitted to the server a page containing PHP scripts extracts the data from the posted information and stores this, using SQL ‘insert’, into a database table.

# PHP to store values 
After completing the form to submit data to the server the next stage was to develop PHP code to take the values from the form when they reach the server and insert them into a database table. 
I accomplished these two operations through two procedures:

1.	The PHP '$_POST' superglobal variable which contains all the values submitted by a (posted) form. So for example the value of a form field named ‘date’ is referenced by '$_POST['date']' 

2.	SQL within the PHP page to which uses an ‘insert’ statement.

I had to be extremely careful when handling some of these values in PHP and while building SQL statements. For example a value such as ‘00:55:12’ had to be quoted inside an SQL statement to be legal. So if I had built the start of an SQL statement in a variable $start and I wanted to append this value which is help in '$_POST['FinishTime']' then to do this and create an SQL statement I needed to introduce quotes: 
$myQuery = $start . "'" . $_POST['FinishTime'] . "'";

My PHP needed to:

1.	establish a connection with some database using a username and password authorised by a server administrator. 

2.	take the values posted by the form, for example $_POST['RunnerID'], as the value for the RunnerID item and put them into an appropriate SQL statement to insert the data into the Results table. 

3.	output a message for the user confirming what data has been added to the table. This can be done by simply echoing a message and the data values to the user. 

The last item ‘3’ simply means that after submitting the form the user must be returned an HTML page confirming the data has been stored.

# The Data and Database Tables
The project demonstration draws on relational database theory by employing a simplified database table system. This includes some details of the database tables that are used to hold information about events, event organisers, runners, runner categories and event results. To enter data into a database, a set of forms is used. Each form can submit data to one or more of the database tables. However for my project demo, I only needed to employ a single table. So, here I will focus on just the ‘Results’ table.

The ‘Results’ table has eight fields:

1. RunnerID. This is a unique number assigned to a runner when they join parkrun which is used to identify the runner. A runnerID is between 1 and 99999, as numbers with up to five digits are allowed.

2. EventID. This is a unique number assigned to an event. This has the same format as ‘RunnerID’.

3. Date. This is the date of the event (and result). A date has the format YYYY-MM-DD.

4. FinishTime. This is the time taken by the runner to complete the event. A time has the format HH:MM:SS.

5. Position. This is the runner’s finishing position. The finishing number is within the range 1-10000.

6. CategoryID. This is a classification of the runner by age and gender. A category is a number in the range 1-100.

7. AgeGrade. This is a calculated number which “Gives an indication of how well the runner has done relative to their age and gender”. The format of this is a percentage with two decimal places, for example 99.36 or 13.45.

8. PB (personal best). This indicates if the time for the event ‘FinishTime’ represents this runner’s best ever time. It has the format ‘1’ representing ‘true’ or ‘0’ (i.e. ‘false’).

The table was created using the following SQL statement:

CREATE TABLE Results 
( 
   RunnerID int, 
   EventID int, 
   Date date, 
   FinishTime time, 
   Position int, 
   CategoryID int, 
   AgeGrade float, 
   PB boolean 
);

Note that the table is called ‘Results’ and that this is NOT equivalent to ‘results’ or ‘RESULTS’.

# Implementation Technology 
Before proceeding further, it is worth clarifying the meaning of the term architecture in this context. In software parlance, architecture is a phrase applied to describe the layout of its elements and how they interact with one another. This definition entails a broad paradigm that correlates with concepts such as, how architecture is fragmented into multiple elements; how these elements collaborate together; and which architectural decisions are made. It also sets the scene whereby the technologies that are to be implemented by the website are portrayed.

There are multiple approaches to architecture. In this project however, the recommended technologies, and how they are employed under the architectural methodology proposed for OURC, are divided into four categories consisting of four core technologies as elucidated by the following subsections:

1.	Client tier – this category exploits the browser as its technology. The Web browser is used to send requests to a Web server, through the Internet. Here, emphasis is placed on adopting ‘open source’ products that abide by the W3C standards, thereby conforming to standards-compliant browsers, e.g. Firefox, allowing users to choose any type of browser. For enhanced functionality, OURC will have to incorporate a 'thick client' with an embedded JavaScript language used to validate forms before the browser submits them to the server; this can be achieved by combining multiple technologies into a group of intertwined methodologies, thus creating a technique called AJAX, i.e. Asynchronous JavaScript and XML, described as ‘a new approach to web applications’ (Garrett, 2005).

2.	Server tier – this is the second category which represents the Web server as its technology. The Web server is used to hold data in conjunction with the database. Similarly, an open source product is recommended for this category in order to circumvent all ‘licensing’ concerns that would otherwise have to be dealt with under a proprietary product. Here, the installation of an open source Apache Web server is preferred, as it offers a ‘free’ version of its product (Apache, 2013).

3.	Middle tier – this third category embodies the 'business logic'. This tier upholds the business operations, requiring a scripting language to fulfil its task. An open source-oriented technology implementation is preferable for this category too. PHP, a scripting language for server-side operations, is the preferred product for the business logic because it is a straightforward open source technology for a standard website, as compared to other ‘complex’ technologies deployed for complex websites.

4.	Data tier – this is the fourth category under the architecture proposed. The data tier can be used to split data in different varieties depending on its mode of functionality, e.g. dynamic data such as runners ‘finish time’ and static data such as their date of birth. Like the aforementioned technologies, a free, open source product is highly recommended for this category. MySQL, which permits multiple databases to be deployed, is deemed as an apt open source technology for this category. 

# Alternative technologies
Many sets of technologies may well be deemed comparable to the aforementioned technologies set. One of those sets is the Microsoft technologies package, i.e. Internet Information Services (IIS) for the Web server on the server tier category; ASP.NET for the business logic on the middle tier category; and Microsoft SQL Server on the data tier (Microsoft Corporation, n.d.). This package consists of technologies that play exactly the same type of roles played by the previously discussed technologies set up on the Apache Web server. 
