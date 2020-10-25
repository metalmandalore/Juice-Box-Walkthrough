# OWASP Juice-Shop-Walkthrough
Guide to learning and practicing juice box for begginers. There are no specific hints contained on this readme page. I ellude to several, but if you have performed a web challenge before, performed vulnerability scanning, or attempted to fuzz the code for you website or any website this will not be new information. The very vague hints presented here is simply good background information for beginners that they may not already have.

## Prerequisites
Install docker, have linux containers as the option set.<br /> 
Have the user you intend to run docker as be a member of the docker users group.<br /> 
Download burpsuite community edition and have it installed and configured as a proxy server for the web browser you're going to use.<br /> 


## Setup
docker pull mkimminich/juice-shop<br /> 
docker run --rm -p 3000:3000 bkimminich/juice-shop --tag OWASPjuice<br /> 

Recommendation - use one browser for Juice shop, and only juice shop. Use a separate browser for searching and anything else.
Tip: having a browser extension like Foxy Proxy makes it simpler to turn burpsuite on and off for a browser.<br /> 

Burp suite always starts out with Proxy > Intercept on. Change this setting to off to load websites normally, but still use burp as a proxy.
View the browsing history under Proxy > HTTP history<br /> 

## How it Works
In general CTFs present us with a wide variety of issues in a gamified formula to demonstrate real world security vulnerabilites. These systems allow security researchers to practice their skills and level up. Do do this effectively take a copious amount of notes, in a format that you find easy to read and understand. It's difficult to know where to begin and know how to approach issues if you've never done it before. The following sections below assist with that. Subfolders are organized accordign to how many Stars each issue has been assigned for this excercise. Each folder contains hints that are written to be thought provoking questions that will hopefully provide newcomers with a better idea behind the often resulting questions that come to mind during and after participating in a CTF or simililar hacking challenges. 
* How would I ever know to do that?
* How did someone else figure this out?
* Why would you do it like that?
<br /> 
This walkthrough is more focused on crtical thinking required for a hacker mindset and the methodology behind finding vulnerabilities and exploiting them.

## Challenge/CTF/Hacking Methodology
### Recon
Always start with this. It's also where the note-taking comes in. Your target is a juice shop website. From frist glance it seems to allow it's consumers to purchase various types of juice and, other interesting and often funny, products. Don't assume things, test them out. What can I do here? Is a great question to ask during each part of this challenge. For recon though, it's important to focus on gathering information while testing out assumptions. Here's one way to do that:<br /> 
You navigate to the main page (I hope you're using Burp), what does this system do when this page loads?<br /> 
This question is simpler to answer if your browser that Burp Suite is being used as a proxy for is not being used for anything except to browse your target, Juice Shop. <br /> 
How do you create an account? What URI's, libraries, and files are called and loaded when you do? <br /> 
What about when you log in? <br /> 
Continue through this thought process, make notes, and write your own questions (not to answer now, but for later). Question like (why is this URI used, and what is that cookie value? OR Does this page contain any URI values that could potentially be manipulated. Note this down, keep track of it, organize it by page if you like. <br /> 
*Caution:* While it's tempting to immediately test your findings for this example <br /> 
Is that base64? highlight text in Burp, right-click and send to decoder, attempt to decode as base64 <br /> 
I would instead caution against doing that. You can, but it may also lead you to become discouraged sooner than sticking to the recon work and satisfying your curiousity after having the information that could make you more successful and solving the challenges.

### Unintrusive scanning
There isn't any scanning that needs to be done for OWASP Juice Shop. Instead there are steps one can take to poke around a web-site a bit more thoroughly than they may have thought to in the Recon phase to obtain more information concerning their target. Are there URI's you haven't explored? Buttons that haven't been pushed? Link that haven't been clicked? Now's the time to do so, and keep documenting what you find for later.

### Intrusive scanning and Enumeration
Kind of odd because there's no real scanning, but this is where I would begin to start answering questions like these: <br /> 
Can the value posted to this page be changed? <br /> 
Can a value in the URL be changed? <br /> 
Can I manipulate information that I've been given? <br /> 
These questions do not need to be answered definitively at this time unless they're simple. If by changing 1 value you solve a challenge, that's neat. Write down what you did and how. If by changing 1 value or placing an unexpected single quote in an input field you receive an unexpected error or an error with any sort of details beyond 404 or "failed" write this down, it will be useful later. During this stage the simplest lowest effort challenges will be accidentally solved, but you should still mostly be performing information gathering tasks.

### Vulnerability Assessment
This stage involves thoroughly reviewing vulnerabilities, learning and understanding what they are, and how to potentially exploit them.
<br /> 
Time to review all of those notes and potentially organize them better. This challenge was created by OWASP, what are the top 10 web application vulnerabilities that they caution application developers on? Can your notes potentially be one of these issues? Exand your Notes by pasting the relevant information into sections based on these known vulnerabilites. Do more research on all of your questions. Answer these questions for what you have written down:
* When I do x why does y happen? 
* What are common web vulnerabilies?
* How are these tested?

### Exploit
Now that we have a set of notes organized by vulnerabilities, the goal is to exploit them and gather flags. Here is where I argue that a perhaps more important self-learning/curiousity goal is to improve your skills by doing tasks you've never done before or need more practice on. Document how you've solved things. Document steps you took and exactly what you attempted when you don't solve things. Start with the easiest challenges and keep going. Determine a time limit that makes you feel more comfortable. <br /> 
How long should you spend on each challenge? <br /> 
1st attempt - until you feel stuck or like what you're doing will likely not work. Document, move to the next one.<br /> 
2nd attempt - 20min-1hr. To determine how long consider what level of frustration you would feel by not solving a simple problem in that amount of time. Choose your time limit to attempt to balance your efforts between productivity and frustration avoidance. Don't be discouraging, consider how much you're learning and how much you know now, vs prior to starting. <br /> 
3rd or more attempts - repeat the methods of using your 1st or 2 attempt strategies as often as needed.<br /> 

### Reporting
Remember all those notes? Spend some time organizing them into something more meaningful to you. It doesn't matter if this is a markdown file, a blog, or a word document with screenshots of exploits or a wall of text. Can you read it? Will this help you next time? Great job! <br /> 
For an additional level up experience attempt to write it in a way that would be simple for others to read and understand.
