# Cross-site-request-forgery-project

# The purpose of this project is to attempt to undergo Cross-Site Request Forgery attacks. It involves a user holding an active session with a trusted site while going to a malicious site, which can intercept the exchange and put an HTTP request into the user’s session, which can be dangerous.

# In order to do this project, I am using the Labtainers provided by the Naval Postgraduate School.
# Link here: <a href="https://nps.edu/web/c3o/labtainers">Labtainers</a>

# To start off the project, I first launch up the Labtainer VM, log in, and start up the CSRF lab.

# I then begin by starting firefox on both alice and boby’s terminal:
<img src="images\1.PNG">

# I then log into Elgg as alice on her “victim” terminal:
<img src="images\2.PNG">

# I open up the network inspector and grab Alice’s cookie session ID:
<img src="images\3.PNG">

# Now, I login as charlie and add boby as my friend, noting down his url and his friend id:
<img src="images\4.PNG">

# I then use the img src command and add it to my index.html file:
<img src="images\5.PNG">

# I send a message to alice as boby to get her to open the link:
<img src="images\6.PNG">

# I open the link as Alice:
<img src="images\7.PNG">

# Refresh the activity page and it works!
<img src="images\8.PNG">

# Boby was able to get Alice to accept his friend request through a csrf attack!

# Now for doing a CSRF attack using a POST Request. 

# Boby wants to do another attack on Alice and have her have the sentence: “I support seed project!” in her profile through another phishing attempt in her messages. To start this out, I first log in as alice and edit her profile to something random like “I hate Boby”. I then check the post request and write down the parameters as seen below:
<img src="images\9.PNG">

