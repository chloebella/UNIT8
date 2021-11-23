# Project 8 - Pentesting Live Targets

Time spent: 5 hours spent in total

> Objective: Identify vulnerabilities in three different versions of the Globitek website: blue, green, and red.

The six possible exploits are:

* Username Enumeration
* Insecure Direct Object Reference (IDOR)
* SQL Injection (SQLi)
* Cross-Site Scripting (XSS)
* Cross-Site Request Forgery (CSRF)
* Session Hijacking/Fixation

Each color is vulnerable to only 2 of the 6 possible exploits. First discover which color has the specific vulnerability, then write a short description of how to exploit it, and finally demonstrate it using screenshots compiled into a GIF.

## Blue

Vulnerability #1: SQL Injection

Description: When clicking on the salesperson page of the blue site, you are able to play with the URL a bit. When editing the id reference by adding the SQL injection 'OR SLEEP(5)=0--', after refreshing or trying to reaccess the page, when closely watching the GET responses and times, this then delays the response time by 5 seconds. Thus leaving the oppurtunity to inject any delay or another instance to the URL if aiming to. 

<img src="blue-vuln1.gif">

Vulnerability #2: Session Hijacking

Description: Given the usage of the tool provided by CodePath : "public/hacktools/change_session_id.php , when opening the link in both Chrome and Firefox, attaining the session ID from Chrome and inserting the PHP session of the site onto Firefox, this allows me to be able to be signed onto the site given the information without having to re-log in since it is hijacking the information and session from the link. Any malicious user, could use this information to hijack the site session and use it to any advantage they please with having access to hidden informations with little effort. 

<img src="blue-vuln2.gif">

## Green

Vulnerability #1: Cross Site Scripting

Description: When playing around on the green site, it is soon noticable that when accessing the Contact and Feedback forms, one can use xss to display as a pop up threat/alert. If you are to go into the feedback,leave your email and insert the XSS script of choice, when logging in to access the feedback information, if injected properly, the message will display on a pop up script before going to the feedback information. Using <script>alert("(Whatever Message Here)"</script> into the comment box, when logged in and accessing, the message will alert the user. 

<img src="green-vuln1.gif">

Vulnerability #2: User Enumeration

Description: When accessing the green site, approaching the login, you are met with the vulnerability of seeing which users are in the system and not. When entering a valid username and wrong password, it is bolded to see that it exists in the database. When entering a false username, the "Login Unsuccessful" changes and is no long bold giving away the information that the user is not in the database. 

<img src="green-vuln2.gif">


## Red

Vulnerability #1: 
IDOR (Insecure Direct Object Reference)

Description: 

Users are able to access to hidden information through the access control vulnerability of Insecure Direct Object Reference on the red site. Given the hyperlink https://35.184.88.145/red/public/salesperson.php?id= when clicking on a direct salesperson, it gives the oppourtunity to change the specified ID for instance, when clicking Robert Hamilton, his id = 4. Irene Boulding is id = 3. 

When playing with the reference id's, when inserting 11 for the reference number, it gives access to a fired salesperson with shown reason by the name of "Lazy Lazyman" option which is not showcased on the directory. This is a vulnerability that may allow attackers to access hidden or fired salespeople just by inserting numbers until finding a hidden account. 





Vulnerability #2: __________________

Description:

<img src="red-vuln2.gif">


## Notes

Describe any challenges encountered while doing the work

Main challenges I faced with this work is the uploading of my GIFs. I provided an example of what the GIFs turn out to when I upload them, however after trying both GiphyCapture and LICEcap, none of them are showing my screen, only showing the screensaver of my computer. It shows my cursor and usage of clicking on the links and accesses however it is not showing what it is I am actually doing. I have been trying to fix it and download other apps and nothing is working for me. This work is easy to show however I am unsure why they are not capturing the tab and just the screen behind it.

* MY GIFs ARE NOT SHOWING THE TAB I AM TRYING TO RECORD, IT ONLY SHOWS MY SCREENSAVER AND MY CURSOR AS IF IT WAS SHOWING MY OPEN TAB, DO NOT KNOW HOW TO FIX THIS BUT I HAVE BEEN TRYING AND NOTHING IS WORKING.

ex: ![Red GIF](https://user-images.githubusercontent.com/41569042/142978977-cfee8a22-cfcf-4ab4-af0f-274171f8bace.gif)
