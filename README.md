# GSOC2021_FINAL_REPORT
This summer, I was quite fortunate to work on the “Improve the suitcase Application” project as part of the Google Summer of Code 2021. I’d like to take a moment now that the program is over to summarize what I’ve done, recall the many things learned over a series of successes and failures in this journey of open source, and talk about future work to be done in the space.

The proposal for the project can be found here :

**Project Abstract**

ODK-X Suitcase is a cross-platform tool that allows the user to upload, download, and update data on an ODK-X Cloud Endpoint from a personal computer . Users can either use the Graphical user interface or the command line interface to perform operations . Users can upload their data in CSV format and access them later. So , Sync endpoint server has to be configured to use the suitcase application.

**For this project I will focus on five tasks.**

    1) Presenting user a list of existing table id’s and allowing multiple table download at once.
    2) Save user credentials and keep user logged in.
    3) Improve error handling and display error message to the user for failed requests.
    4) Writing unit tests and GUI tests.
    5) Improve the documentation.

**MY MENTORS:**

Li Lin ,Jeff Beorse , Waylon Brunette, Vyankatesh Sawalapurkar.

Github Git Repositories in which I made changes :

Suitcase

Sync-Client

ODK-X docs

The coding part of the project was done in following order:

   1) Adding the drop down in the download tab to select a Table to download.
   2) Implementing Feature to select multiple tables for download at once.
   3) Improving the UI.
   4) Writing Test Cases.
   5) Save user credentials in preferences to keep user logged in if save password option is selected also implement a
   6) Implementing new features to delete and update a table from GUI.
   7) Updating documentation with new screen shots.
   8) Changing colors of buttons and other UI components.

**Pull Requests for major features:**

Table ID dropdown implementation, Multiple table ID selection, UI improvements and new tabs for update and delete and reset option.

Link to PR : 

Save login credentials to keep user logged in and logout option

Link to PR

AssertJ tests for login, upload, update, download, reset and delete.

Link to PR

Update docs with new features and screen shots

Link to PR

**Other Pull Requests for minor changes :**

Adding error response as message to exception in Sync-Client

Link to PR

Adding Logo to login page

Link to PR

Updating screen shot in Scan application documentation

Link to PR

Here are the screen shots of the Updated Suitcase application.

Login page :

Download tab :

Upload tab :

Update tab :

Clear tab :

**Challenges faced**

    The first challenge I faced was during error handling. Sync-Client returns response as JSON object. When there is an error and response is not in JSON then it throws a JSON exception. We needed the HTML message returned in response to Sync Client. Creating a new exception class was not possible because it would change the method signature. So we finally passed the entire HTML response to JSONException as message and parsed it in Suitcase.
    The Second challenge was writing login test. After the login starts we waited for 15 seconds to check if login is successful or not. But doing more research we found another Java Library Awaitility that simplified the process. Awaitility takes a method that returns weather operation is complete or not and test is complete at the moment the task is successful. The tests ends after a particular interval of time if there is no response and test is declared failed.
    The most interesting problem was saving credentials in a secure way. In a desktop application we need a private key to store the credentials in an encrypted format. But we faced problem in securing this key. If someone gets access to this key then it will be very easy to get the password. Currently we are simply storing password and username in Java preferences.

**Lessons Learned:**

I gained a lot of technical knowledge in Java from other members of the community as well as while working with the code. But I also learned some general advice that I will continue to follow in the future as well.

    1) Always make sure that it is easy for others to understand your code.
    2) Communicate as much as possible so that you can get multiple ways to solve any problem that you face.
    3) Never expect that you will finish a task in a short span of time. Even the most easy looking tasks will have problems that you start to know only when you start working on them.

**Future works :**

    We need to improve the security of the application and find a good way to encrypt stored password.
    There is scope for more improvement in the CLI documentation.

**Final Remarks**

GSoC 2021 has been a key point in my path as a developer, it improved my Java skills a lot and gave me solid grounds in understanding general software development practices. Furthermore, seeing my commitment being rewarded and completing what I had been selected for, is a great satisfaction, that kind of confidence boost is good for everyone. I will like to continue contributing to my organization ODK-X and help future GSOC students.

**And at last Thank you Google for this wonderful experience :-)** .
