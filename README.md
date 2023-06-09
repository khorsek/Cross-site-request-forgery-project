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

# Now that I have the parameters, I open up the index.html file with nano and fill in the fields with the information taken:
<img src="images\10.PNG">

# Now that the information is filled in, I send Alice another message with the link:
<img src="images\11.PNG">

# I'd definitely make a great scammer.

# Alice’s starting profile before clicking the link:
<img src="images\12.PNG">

# As soon as I click the link, the page immediately reloads and my bio is changed:
<img src="images\13.PNG">

# Q&A

# Q: The forged HTTP request needs Boby’s user id (guid) to work properly. If Alice targets Boby specifically, before the attack, she can find ways to get Boby’s user id. Alice does not know Boby’s Elgg password, so she cannot log into Boby’s account to get the information. Please describe how Alice can find out Boby’s user id.
# A: A quick look at the members source code shows a vulnerability as it displays all of the users’ names and their user ID as seen in this screenshot:
<img src="images\14.PNG">

# Q: If Alice would like to launch the attack to anybody who visits her malicious web page. In this case, she does not know who is visiting the web page beforehand. Can she still launch the CSRF attack to modify the victim’s Elgg profile? Please explain.
# A: Unless she adds some further scripting to see who is visiting her profile, and then a way to gain their user ID, all the while adding these new bits of information into the current scripts that require the user name and id, then she will probably not be able to launch the attack.

# Now to enable countermeasures for elgg. I open up the /elgg/engine/lib directory and open up actions.php. I scroll all the way down and then I comment out the “return true;” statement:
<img src="images\15.PNG">

# I then save the file and go to alice’s profile, where I manually change the bio myself.
<img src="images\16.PNG">

# After clicking on the link, I notice that this time, the page doesn’t automatically refresh and open the profile page, it’s just stuck on this page:
<img src="images\17.PNG">

# The page was also acting acting weird so I opened up elgg and logged in again, when I got this on the right:
<img src="images\18.PNG">

# Checking the page with the network inspector active just shows nothing.
<img src="images\19.PNG">

# The reason why the attacker can’t send these secret tokens is because they are being randomly generated every time and they aren’t being stored on the webpage this time so they can’t be found and thus, we get an error.
<img src="images\20.PNG">