# shivanshu_shippable

Link to the app :

https://glacial-hollows-6610.herokuapp.com/


Solution :
Firstly, I am getting the total issue counts. And from the link header, I am taking the value of the last page number. Now that I know how many pages are there, I iterate through each page and within each page I iterate through each issue and check if it is a pull request or not. If it is not a pull request, then I increment the count of the total issues. These total issues now include the total number of opened issues ignoring the pull requests. 

After getting the total opened issues, I now calculate the issues opened since last 24 hours, issues opened after 24 hours but less than 7 days ago and the issues opened after 7 days.

For the issues opened in the last 24 hours, I iterate through every issue and check the "created_at" timestamp. If the timestamp is less than 24 hours old, then I increment the count of the issues opened in last 24 hours.

For the issues opened after 24 hours but less than 7 days ago, I iterate through every issue and check the "created_at" timestamp. If the timestamp is less than 7 days old, then I increment the count of the issues opened since last 7 days. Now I subtract this value from the issues opened since last 24 hours.


For issues opened before 7 days, I subtract the total number of issues with the issues which are created since the last 7 days.



If given more time :
-I will work on the UI to display it more nicely.

- Github api as of now does not provide any parameter to be passed to the url to fetch an open issue directly. For each issue, we have to look at the "created_at" timestamp and compare the times. It does provide the feature to fetch the issue by looking at the "updated_at" timestamp using the "since" parameter in the url. In future, if github provides a parameter which directly fetches the issues by looking at "created_at" timestamp, I would definitely like to use that feature so as to improve performance as less comparisons will be required then.

