Royce Le
INFO 415
HW3 - Advanced XSS Payloads Homework

--------- Vulnerabilities ---------
*I don't have my files as an HTML file in a zip folder because some of my html & css attributes are dependent on being ran on a server, so, I hosted the three levels on my website for easy access. Here are the links to the vulnerabilities.

--------- The Report ---------
*What is clickjacking and why is it bad?
	Clickjacking is also known as a 'UI redress attack', which is where an attacker utilizes transparent/opaque layers on an html page to trick users into clicking something that the user implemented to activate a malicious action when the user meant to click on a button, link, picture, etc.... 

*Give a mitigation recommendations for stopping clickjacking. A couple sentences - what to do, how it works, and why you would choose that mitigation over others.
	Some mitigation suggestions to stop clickjacking would be to use a frame-buster script or X-Frame-Options HTTP response headers that instruct the browser not to allow framing of other domains.

	First, as a defender, the frame-buster script method is where you write javascript (i.e. try {if (top.location.hostname != self.location.hostname) throw 1;} catch (e) {top.location.href = self.location.href;}) that will detect if your website is being placed in a frame, and if so, the script reloads your website in the main browser to escape the hack. The con with frame-buster scripts is that it's easily hackable with methods like the sandbox attribute on an iframe that prevents jacascript. 

	Furthermore, the other mitigation where you have X-Frame-Options response headers to prevent your site from being placed within a frame is pretty easy to implement by puting in the header whether or not a browser should be allowed to render a page in a <frame> or <iframe> with the implementation of values "DENY", "SAMEORIGIN", or "ALLOW-FROM uri". The pro of this method is that it is simple, but, the con of this method is that the method works only on some browsers and that to have this header option, you need to have access to webserver configuration and/or scripting language on the server. I would choose this method over the frame-buster mainly because it has been proven over and over again to be a legacy prevention method that has been hacked into many times, and I don't want to implement layers of protection just for one method of defense when X-Frame-Options are pretty secure and easy to implement.

--------- My resources ---------
*How to make my button into a small square
	*https://www.w3schools.com/bootstrap/bootstrap_buttons.asp
*How to get past the redirect in question 3
	*https://javascript.info/clickjacking
*Where I got my inspiration for my website
	*http://www.quackit.com/html/templates/simple_website_templates.cfm
	*http://www.quackit.com/html/templates/download/bootstrap/business-2/index.html
	*https://standfortrees.org/en/
*How I was able to answer the question posted for the hw
	*https://www.owasp.org/index.php/Clickjacking_Defense_Cheat_Sheet
	*https://www.owasp.org/index.php/Clickjacking
	*http://blog.kotowicz.net/2009/12/5-ways-to-prevent-clickjacking-on-your.html