# Computer basics

## Shortcuts

When dealing with computers on a daily basis, you need to know that the keyboard and the mouse are your best friends. And if you want to be as fast as you can get, you should try to use your keyboard way more than the mouse. Why would you realy on two buttons when you have **10 fingers on one whole keyboard**?

We'll come back here later, but as an example, look at this [cheatsheet](https://code.visualstudio.com/shortcuts/keyboard-shortcuts-windows.pdf), see how far you can get in [VS Code](https://code.visualstudio.com/download) just using your keyboard? Isn't that awesome?

This is great, but first, we need to get used to the most basic shortcuts we can use in a computer for the most basic tasks. These few shortcust will save you so much time you won't believe you didn't know them until now. Enjoy! :D


| Shortcut   | Effect                                               |
|------------|:----------------------------------------------------|
|`ctrl + c`  | Use this command to **copy** into your clipboard any kind of content, either files or text fragments |
|`ctrl + x`| Similar to copy, this command **cuts** the content and removes it from where it was before typing it.|
|`ctrl + v` | Use this to **paste** whatever you've just either copied or cut.|
|`ctrl + o` | In your editor, this command will **open** a new window from where you can open an existing file. |
|`ctrl + n` | This command will open a **new file** in another tab from your editor.|
|`ctrl + m` | This command will **minimize** the window you're currently working with.|
|`ctrl + s` | Use this command to **save** your file in the location it currently is.|
|`ctrl+⇧+s` | Use this to **save** your file to a **new location**.|
|`ctrl + w` | Use this to **close** the tab you're currently in.|
|`ctrl + t` | In your **browser**, use this shortcut to open a **new tab**.|
|`ctrl + q` | Normally, this command is used to close the application you're currently in.|


###### Exercise

Practice with these commands as long as you need to get familiarized with them. Try to copy, cut and paste files, text fragments, whatever comes to your mind. Try to open files, close them, etc. Try to use all the commands at least once.
___

## How the web works

Have you ever wondered what happens when you open your browser, type in any address ([Madrid For Refugees](http://madridforrefugees.org/es/) web for instance), and in just a few seconds (depending on your connection speed of course) you see the [above-the-fold](https://thetechreviewer.com/tech-tips/web-design-101-what-does-above-the-fold-mean/) content? We take this process for granted but let me tell you, there are **so many things** going on that it feels like magic when you see that everything happens within a few parts of a second. Let's dive in!

For a webpage to load in your computer, and to keep it short, we need 5 things:
- Your personal computer
- A web browser (**the client**)
- An internet connection
- A web server (**the server**)
- Routers & Switches

If we had to chronologically lay out what happens when we type an address in our web browser and see it displayed in our screen, we could divide the process as it follows:

##### DNS
First of all, you have to take into account that computers are really (like **REALLY**) bad with human language. At their core, they only understand two things: 1 (on) and 0 (off) (what is called [binary system](https://www.computerhope.com/jargon/b/binary.htm)) so every layer that becomes more understandable for us dumb humans, is another layer of abstraction that we need to get rid off for the computer to understand what we really want it to do.

Having said this, you should imagine by now that the words that you're going to type don't really mean anything to the web server that is going to serve you all the content you just requested. Websites are stored in these web servers (other computers really, but generally without a GUI and permanently running in massive warehouses) and have a unique **IP address** associated (Internet Protocol address). These IP addresses are a group of numbers that generally look something like this *107.95.207.18*. Rings a bell? Think of any other thing on your daily life that looks like that... phone numbers anyone?

DNS, or **D**omain **N**ame **S**ervers, are basically the phonebook of the internet. Imagine storing in your brain all of your friends' phone numbers. That would be, besides impossible, pretty much inefficient. Why would you do that when you can store the numbers in alphabetical order and look them up when you need them?
This is what DNS are for. When you type, let's say www.madridforrefugees.org, your browser sends a request to one of these DNS and looks up its unique IP. When that said IP is found, the request is sent back by the browser to the web server with that IP using the **HTTP protocol**, which for a computer is much easier to find than using human readable words. Once that server is found, the requested files are served (html files, css files, images, etc) back to the web browser installed in your computer, rendering it and displaying the content in your screen.

Let's make this process a little bit more understandable with a human conversation:

- **Chrome**: Hey Internet! I'm 107.95.207.18! Can I get the content for www.madridforrefugees.org?
- **DNS**: Come on Chrome, you know this is not how it works. You can't get that far with that, let me help you. I'll look that gibberish you just told me in my super huge IP address book... (DNS doing its thing) Whoah! Found it! Here, try with this: 162.220.60.225
- **Chrome**: Wow! Thank you DNS, what would I do without you <3.
- **DNS**: That's what I'm for! Hey, wanna hear a joke?
- **Chrome**: Hmmm, well sure, I mean I work pretty fast, I guess I have time for one joke.
- **DNS**: There are 10 types of people, those who know binary and those who don't. 👉&nbsp;&nbsp;👉
- **Chrome**: :joy:&nbsp;&nbsp;Oh my god DNS, you're such a character. Well, I better get going or my human is [going to start throwing things out the window](http://www.websiteoptimization.com/speed/tweak/psychology-web-performance/).See you later alligator 🐊 !
- **Chrome**: Hey Internet! I'm 107.95.207.18. Can I get the content for 162.220.60.225.
- **Server @162.220.60.225**: Oh! Hi Chrome! Sure, let me find the files for you. Here! There you have them. Let me know if you need anything else.

In short, we can identify 5 steps to answer the question of the title:
1. The user (you) types an URL in your browser and hit enter. This request is sent to a Domain Name Server.
2. The DNS gives back an IP address for the web server that is hosting the website you requested.
3. The user's browser requests again the page, this time using the obtained IP address.
4. The Web server returns the page specified by the browser.
5. The browser gets all the information and displays it in your computer.

As you imagine, this is a really summarized example of what happens when you want a website to be displayed. However, this will probably be more than enough to get you going through the course. In any case, if you want to lear more, go to the [more info](#more-info) section

###### Exercise

Even though you don't know yet, there's an application in your computer called **terminal** that will be extremely helpful for you in the following months. Don't worry about it yet, just trust me and open it now, don't be scared!

For this exercise, just type the following command in your terminal and you should be able to identify some things that we've just discussed here.
```
curl -v https://www.madridforrefugees.com
```
The output should show you several things that you won't be able to identify yet, but don't worry, give it some time and come back here in a few months. You'll be amazed of how many more things you can understand! For now, you should at least identify the IP address, along with some other things like the request date, the used HTTP protocol and the host name.

Try with some other URLs and see the different IPs that are used for each one.
___



##### More info

[How internet works](https://www.youtube.com/watch?v=e4S8zfLdLgQ)

[Client and servers](https://www.youtube.com/watch?v=SwLdKeC8scE)

[DNS and IP Address](https://computer.howstuffworks.com/dns1.htm)