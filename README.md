# Writing (210A): Tutorial Blog - JSON

## What is JSON and how is it used?

  JSON is a data format designed to send data between a server and a browser, and allows the developer to organize the data, pairing keys to values in a way that both the developer and computer can easily read. The syntax of JSON is very similar to JavaScript but has strict rules. The main technology that will be incorporrated is call "localStorage". It is a storage system that is built into every web browser and it lets web browsers store small portions of data onto the user's computer. Every web browser has it's own seperate localStorage so as to block a site from accessing the data of another. The storage limit of localStorage is about 5 MB and the data persistes even after a browser is closed in contrast to regular variables that disappear when closed, or cookies that have expiration dates. The two rely on each other to store, process and handle the data. LocalStorage can only store strings and not arrays or objects, thus it uses JSON to convert those objects into strings. LocalStorage then stores the strings, and gives them back to JSON to revert back to arrays and objects when the browser needs them. JSON makes this process run a lot smoother, as it can convert the complex data in a clean way.

## How it's done

### Set Up

  There is a simple way to get started whether for practice or you're actual project. First you need to open a basic HTML file, some places to do that are VS Code (the one I use), Notepad (Windows), TextEdit (Mac), Sublime Text, or any other similar one. Next, it's important to understand 3 of the common JavaScript methods used to process the JSON data. 
  * First, ```localStorge.setItem()``` sets the data key and value in localStorage. For example,
```
localStorage.setItem("age", 22)
```
sets the value 22 to the key "age". Altough local storage only takes strings like I said earlier, Javascript converts it automatically. However when retreived like in getItem below, it returns it as a string and needs to be convereted back to an object. 
  * Next, ```localStorage.getItem``` retrieves the item from localStorage and returns the value thats paired with the key. For example,
```
localStorage.getItem("age")
```
gets the value connected with "age", which in this case is 22.
  * Finally, ```localStorage.removeItem``` deletes a specific value paired with the key from localStorage. For example,
```
localStorage.removeItem("age")
```
would delete 22 from localStorage.

*Tip: You can open browser tools (F12 or right click -> inspect) -> Application tab -> Local Storage, to see immediate changes as you code.*

### *Important Side Note*

Lots of time whem coding in JavaScript, data is usually stored as an object. An example would be,
```
let age = {
  age: 22
  birth year: "December"
}
```
If you try to save that directly into localStorage, it won't know how to handle the object, so it will just save it to something like ```[22 december]``` which can't be used for anything. This is why JSON is so useful, because you can use functions  like 



