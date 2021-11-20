# Developing a Simple Webserver
## AIM:
To develop a simple webserver to display top five programming languages. 

## DESIGN STEPS:
### Step 1: 
HTML content creation
### Step 2:
Design of webserver workflow
### Step 3:
Implementation using Python code
### Step 4:
Serving the HTML pages.
### Step 5:
Testing the webserver

## PROGRAM:
```
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<!DOCTYPE html>
<html>
<head>
<title>My webserver</title>
</head>
<body>
<h1 style="color:navy">TOP FIVE PROGRAMMING LANGUAGES</h1>


<h1 style="color:darkmagenta">1.JavaScript</h1>
<img src=https://thumbs.dreamstime.com/z/moscow-russia-june-javascript-js-logo-sign-program-code-background-illustrative-editorial-189667712.jpg alt="Javascript logo" style="width:500px;heigth:500px;">

<p style="color:mediumblue">Designed by : Brendan Eich of Netscape initially; others have also contributed to the ECMAScript standard.</p>

<h2 style="color:blueviolet">About :</h2>

<p>JavaScript (often shortened to JS) is a lightweight, interpreted, object-oriented language with first-class functions, and is best known as the scripting language for Web pages, but it's used in many non-browser environments as well. It is a prototype-based, multi-paradigm scripting language that is dynamic, and supports object-oriented, imperative, and functional programming styles.</p>

<h2 style="color:blueviolet">Applications of JavaScript Programming Language :</h2>

<p>JavaScript runs on the client side of the web, which can be used to design / program how the web pages behave on the occurrence of an event. JavaScript is an easy to learn and also powerful scripting language, widely used for controlling web page behavior.</p>


<h1 style="color:darkmagenta">2.Python</h1>
<img src=https://miro.medium.com/max/2000/1*to0Tp8CBi-vbKvu-ljPukg.png alt="Python logo" style="width:500px;heigth:500px;">

<p style="color:mediumblue">Designed by : Guido van Rossum</p>

<h2 style="color:blueviolet">About :</h2>

<p>Python is an interpreted high-level general-purpose programming language. Its design philosophy emphasizes code readability with its use of significant indentation. Its language constructs as well as its object-oriented approach aim to help programmers write clear, logical code for small and large-scale projects.</p><p>Python is dynamically-typed and garbage-collected. It supports multiple programming paradigms, including structured (particularly, procedural), object-oriented and functional programming. It is often described as a "batteries included" language due to its comprehensive standard library.</p>

<h2 style="color:blueviolet">Applications of Python Programming Language :</h2>

<p>Python is commonly used for developing websites and software, task automation, data analysis, and data visualization. Since it's relatively easy to learn, Python has been adopted by many non-programmers such as accountants and scientists, for a variety of everyday tasks, like organizing finances.</p>


<h1 style="color:darkmagenta">3.C++</h1>
<img src=https://latx-technologies.com/wp-content/uploads/2021/04/c-programming-course-1024x553.jpg alt="C++ logo" style="width:500px;heigth:500px;">

<p style="color:mediumblue">Designed by : Bjarne Stroustrup</p>

<h2 style="color:blueviolet">About :</h2>

</p>C++ is a general-purpose programming language created by Bjarne Stroustrup as an extension of the C programming language, or "C with Classes". The language has expanded significantly over time, and modern C++ now has object-oriented, generic, and functional features in addition to facilities for low-level memory manipulation. It is almost always implemented as a compiled language, and many vendors provide C++ compilers, including the Free Software Foundation, LLVM, Microsoft, Intel, Oracle, and IBM, so it is available on many platforms.</p><p>C++ was designed with an orientation toward system programming and embedded, resource-constrained software and large systems, with performance, efficiency, and flexibility of use as its design highlights.</p>

<h2 style="color:blueviolet">Applications of C++ Programming Language :</h2>

<p>C++ can be used to develop operating systems, browsers, games, and so on. C++ supports different ways of programming like procedural, object-oriented, functional, and so on. This makes C++ powerful as well as flexible.</p><p> C++ has also been found useful in many other contexts, with key strengths being software infrastructure and resource-constrained applications, including desktop applications, video games, servers (e.g. e-commerce, web search, or databases), and performance-critical applications (e.g. telephone switches or space probes).</p>


<h1 style="color:darkmagenta">4.Java</h1>
<img src=https://www.clipartkey.com/mpngs/m/107-1073107_java-programming-language-logo.png alt="Jave logo" style="width:500px;heigth:500px;">

<p style="color:mediumblue">Designed by : James Gosling</p>

<h2 style="color:blueviolet">About :</h2> 

<p>Java is a high-level, class-based, object-oriented programming language that is designed to have as few implementation dependencies as possible. It is a general-purpose programming language intended to let programmers write once, run anywhere (WORA), meaning that compiled Java code can run on all platforms that support Java without the need for recompilation. Java applications are typically compiled to bytecode that can run on any Java virtual machine (JVM) regardless of the underlying computer architecture.</p><p> The syntax of Java is similar to C and C++, but has fewer low-level facilities than either of them. The Java runtime provides dynamic capabilities (such as reflection and runtime code modification) that are typically not available in traditional compiled languages.</p>

<h2 style="color:blueviolet">Applications of Java Programming Language :</h2>

<p>Mobile App Development, Desktop GUI Applications, Web-based Applications, Gaming Applications and so on.</p>


<h1 style="color:darkmagenta">5.R Language</h1>
<img src=https://miro.medium.com/max/990/0*l9-9V7yetcbz-YKC.jpg alt="R language logo" style="width:500px;heigth:500px;">

<p style="color:mediumblue">Designed by : Ross Ihaka and Robert Gentleman</p>

<h2 style="color:blueviolet">About:</h2>

<p>R is a programming language and free software environment for statistical computing and graphics supported by the R Core Team and the R Foundation for Statistical Computing.It is widely used among statisticians and data miners for developing statistical software and data analysis.</p><p> Polls, data mining surveys, and studies of scholarly literature databases show substantial increases in R's popularity;since August 2021, R ranks 14th in the TIOBE index, a measure of popularity of programming languages.</p>

<h2 style="color:blueviolet">Applications of R Programming Language :</h2>

<p>R is primarily used for descriptive statistics. Descriptive statistics summarize the main features of the data. R is used for a variety of purposes in summary statistics like central tendency, measurement of variability, finding kurtosis and skewness.</p>

</body>
</html>
"""
class myhandler(BaseHTTPRequestHandler):
    def do_GET(self):
        print("request received")
        self.send_response(200)
        self.send_header('content-type', 'text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())
server_address = ('',8080)
httpd = HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()
```
## OUTPUT:

## Client Side Output :
![Output 1](/images/Output1.png)

## Server Side Output :
![Output 2](/images/Output2.png)

## RESULT:

A Simple webserver to display top five programming languages is developed . 


