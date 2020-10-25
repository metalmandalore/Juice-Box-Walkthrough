# Skill Walkthrough
This does not contain the actual answer for this challenge, but it does contain a walkthrough of how to create a wordlist and fuzz the URI of a website by using Burp Suite Intruder.
If these directions are followed, this challenge will be solved. Can you solve this challenge without fuzzing? Yes, but manually fuzzing things is slow and doesn't teach useful skills.

## Wordlist
Fuzzing is best done with wordlists. Burp Suite comes with many basic ones, but these are unavailable to those whose corporations pay the money to give them the professional version. Customized wordlists are more useful. </br>
*Tip* Intruder on Burp Suite community edition is throttled, which means it's ridiculously slow. Make your wordlists as small and concise as possible. </br>

### Creating a Wordlist
What is the term we're looking for here? Our wordlist should create variations of those words and nothing else. </br>
A typical way to create wordlists is to use a tool that performs webscrapping and the creation of the wordlist automatically. There are several available and they generated wordlists of hundreds or thousands of words in minutes.<br /> 
However, we're using Burp Suite Community Edition, which is throttled, we really want 50 words or less. The smaller this list is, the better because it will take less time. I'm not recommending any automated wordlist generators for that reason. </br>
Instead, we're going to think of a few things to manually create our .txt file.
*Create your text file and put it in the folder for other files that may be created or used for to solve the Juice Box challenges. It will start empty, that's ok.
Spaces are not allowed in a URL, so first think of what are common ways this worked around for URLS. Take this URI portion of this URL that says "Juice-Box-Walkthrough" for example. This is one way that spaces are avoided. Other common options are ommision of the space, using an underscore or plus symbol, or using the URL encoding equivilent of a space %20. </br>
*Note* Wordlists consist of 1 word per line, no comma, semicolon, or other character used for word seperation needed. Just use a new line for each word.
*Edit your text file to include a small wordlist with variations of the term we're looking for, the title of this file.

## Manual Fuzzing
This should be done, but honestly the status and length codes of the requests in burpsuite intruder for this challenge are the same for the correct scoreboard site as they are for the incorrect one. Which make the end results less excited.
* Attempt to add the word variations from your list to the end of the URL in your browser. The correct variation will take you to the Score Board. After completing this challenge it will be accessible from the menu icon on the top left of the page.

## BurpSuite Intruder - the Advanced Way
* On BurpSuite, navigate to Proxy > HTTP history </br>
*Click the # on the far left to filter the requests so that your most recent request is on top (if it says 1, click it again, these numbers increment every time your browser loads a page).
I know I said we'd use intruder, but like using repeater, it's best to right-click on a page you've browsed to and and send it to Intruder. Then we'll go to the Intruder tab.
* In your browser Navigate to the main site page
Look at the URL for the main site once it loads in your, this is what you will need to mimic.
You'll notice a lot of URI options to select here. Some of these are "/" to "/rest/products/search?q=" and "/rest/languages". Any of these will work, but the smaller the URI the simpler this will be.
* In BurpSuite right-click on that request and select Send to Intruder (or use the keyboard shorcut CTRL+i)
* Select the Intruder tab
* The Target tab will contain the host and port for Juice Shop
* Select the Positions tab
* Use the Sniper Attack type
* Click the button that says Clear §
* Verify there are no § symbols in the request that is loaded
The URI is in the very top line of the GET request. It includes everything that is after the word GET and before HTTP/1.1. 
</br> What's the difference in the URL in your brower and the one you're looking at in intruder?
</br> REALLY look or you won't find the answer
* Highlight everything in the URI after the 1st /
* Click the Add § button
* Select the Payloads tab
The default Payload set is 1 and the default Payload type is Simple list. Leave these defaults.
* Under the Payload Options section click the Load ... button
* Navigate to your .txt file and click Open
You can look around at other options in the Payloads or Options tab if you like, but nothing else needs to be changed.
* Click the Start Attack Button in the upper right
* Click OK on the pop-up warning that Burp Introder is throttled in community edition

