# Browser render process of HTML, CSS, JS to DOM

## ***1. Abstract***

In this paper, we discuss how browsers render HTML, CSS, JS to DOM and the mechanism behind it. Generally when web browsers attempt to load the pages like HTML, CSS, JS it follows a certain process to convert these files into a webpage. The process need to be followed is shown in below fig

![GitHub Dark](https://miro.medium.com/max/1248/1*srfAe9f1ryMc3qoMOASmhg.png) 

## ***2. Introduction***

## 2.1 What is browser rendering?

Browser rendering is a process that converts the website code like HTML, CSS, JS into interactive pages which we see on a website. Browser rendering is also known as a browser engine. There are different types of browser engines like Webkit for Apple's Safari, Blink for Chrome, and Gecko for Firefox. Browser rendering converts the data of HTML, CSS, and JS to DOM and CSSOM.

## 2.2 what is DOM?

DOM is known as Document Object Model. DOM is the structured representation of the HTML document created by the browser. It allows Javascript to manipulate, structure, and style the website. Document object is the entry point of the DOM for accessing any HTML element. DOM tree represents an HTML document as nodes. Each node is referred to as an Object.

 ## ***3. The mechanism behind browser rendering process:***

* Whatever the code we have written in files HTML, CSS, JS when we try to attempt them in a web browser, the browser didn't read them directly. The first browser receives them in a binary format and sets the parser to convert the HTML  into DOM. In CSS when the parser comes across resources it will get those files, while in JS it defaults to block the HTML parser and the JS file is loaded and parsed. 

![Data reading from files](https://res.cloudinary.com/practicaldev/image/fetch/s--g91gy7_g--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://cdn-images-1.medium.com/proxy/1%2AGSw1oqEpbPo0NmwG_73bPw.png)
* 2But the raw bytes of data is not understandable for the browser. So the browser needs to work with DOM.
* Now it converts the raw bytes of data into characters.
* Now these characters are again converted into tokens.
* Now these tokens are converted the start tags and end tags into nodes.
* Now these nodes are linked to a tree-like structure known as DOM, which is the Javascript representation of HTML, Simultaneously by following this process web browser converts CSS code to CSSOM. 
![DOM](https://blog.logrocket.com/wp-content/uploads/2018/09/image10.jpg)

![CSSOM](https://blog.logrocket.com/wp-content/uploads/2018/09/image4.jpg)

* After the browser created the DOM and CSSOM it creates a tree known as Render tree. The render tree only consists of nodes that are visible on the screen. If the node is marked as none then it won't be a part of the Render Tree.

![Render Tree](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/images/render-tree-construction.png)
* After completion of the Render tree, the next process is the Layout stage.
* Layout is also known as reflow which gives the position and size calculation based on render tree construction. After the completion of the layout stage, the next process is Paint setup. It rasterizes the blocks and text, decodes the image, and resizes if any changes need to be done.
* Finally the last stage is Layer composition. It compose the visual layers which were processed and painted independently.

## ***4. References***
[Render-tree Construction, Layout, and Paint by Ilya Grigorik](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/render-tree-construction)

https://www.html5rocks.com/en/tutorials/internals/howbrowserswork/

