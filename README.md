# Writing (210A): Tutorial Blog - JSON

## What is JSON and how is it used?

  JSON is a data format designed to send data between a server and a browser, and allows the developer to organize the data, pairing keys to values in a way that both the developer and computer can easily read. The syntax of JSON is very similar to JavaScript but has strict rules. The main technology that will be incorporrated is call "localStorage". It is a storage system that is built into every web browser and it lets web browsers store small portions of data onto the user's computer. Every web browser has it's own seperate localStorage so as to block a site from accessing the data of another. The storage limit of localStorage is about 5 MB and the data persistes even after a browser is closed in contrast to regular variables that disappear when closed, or cookies that have expiration dates. The two rely on each other to store, process and handle the data. LocalStorage can only store strings and not arrays or objects, thus it uses JSON to convert those objects into strings. LocalStorage then stores the strings, and gives them back to JSON to revert back to arrays and objects when the browser needs them. JSON makes this process run a lot smoother, as it can convert the complex data in a clean way.

## How it's done

### Set Up

  There is a simple way to get started whether for practice or you're actual project. First you need to open a basic HTML file, some places to do that are VS Code (the one I use), Notepad (Windows), TextEdit (Mac), Sublime Text, or any other similar one. Next, it's important to understand 3 of the common JavaScript methods used to process the JSON data. 
  * First, ```localStorge.setItem()``` sets the data key and value in localStorage. For example:
```
localStorage.setItem("age", 22)
```
sets the value 22 to the key "age". Altough local storage only takes strings like I said earlier, Javascript converts it automatically. However when retreived like in getItem below, it returns it as a string and needs to be convereted back to an object. 
  * Next, ```localStorage.getItem``` retrieves the item from localStorage and returns the value thats paired with the key. For example:
```
localStorage.getItem("age")
```
gets the value connected with "age", which in this case is 22.
  * Finally, ```localStorage.removeItem``` deletes a specific value paired with the key from localStorage. For example:
```
localStorage.removeItem("age")
```
would delete 22 from localStorage.

*Tip: You can open browser tools (F12 or right click -> inspect) -> Application tab -> Local Storage, to see immediate changes as you code.*

### *Important Side Note*

Lots of time whem coding in JavaScript, data is stored as an object. An example would be:
```
let student = {
  age: 22
  major: "Cybersecurity"
}
```
If you try to save that directly into localStorage like this:
```localStorage.setItem("student", student)```
it won't know how to handle the object, so it will just save it to something like ```[22 Cybersecurity]``` which can't be used for anything. This is why JSON is so useful, because you can use functions like ```JSON.stringify()``` inside of the code above (were the second "age" is) and it will convert it into the proper JSON format as a string string so that it can be stored. Then when you want to retreive it back from localStorage, you use ```JSON.parse()``` to convert it back to a usable JavaScript object.

### Storing JSON Data

Let's revisit that example of using age, major, and lets add in graduation year, to show how you would save it correctly as JSON data. The object like above would be something like this:
```
let student = {
  age: 22
  major: "Cybersecurity"
  graduation: 2028
}
```
To stringify it (like above) and save it, you simply write:
```
localStorage.setItem("StudentInformation", JSON.strigify(student))
```
Thats it! 
And it will be the same format for getItem and other JavaScript functions, sometimes with other JSON functions like ```JSON.parse()```. In this example, StudentInformation is the key and the stringified object is the value. This key will be used later to find the data later, so vague names like just "data" or "info" can get confusing, especially when using them for mutliple things. Also of note that it is best to not include a space when using multiple words, as the program can also treat the space differently and get confused. 

### Accessing the JSON Data

The main function used for this is the JavaScript ```getItem()```, which pulls that string back out of localStorage, and uses ```JSON.parse()``` as explained earlier, to revert back to a usable object. ALothough  Of note is that if nothing is stored, ```getItem()``` will return ```null``` which can lead to your code crashing so always check! Using an if statement can be a very good method ensuring that it won't return null

When retrieving the data, it is also possible to access each property in the object individually. That is done by including the key name "dot" the property name. Here is an example using the object above:
```
let student = {
  age: 22
  major: "Cybersecurity"
  graduation: 2028
}
let retrieved_data = JSON.parse(localStorage.getItem("StudentInformation")
console.log(retrieved_data.age) // this outputs 22
console.log(retrieve_data.major) // this outputs Cybersecurity
```
Notice how we first set the object of "retrieved_data", and then we use that object to get the sepcific properties.


###  Displaying the Data on the Page

Dis playing the data, requires both HTML, and JavaScript. First, in the HTML, you need to include a paragraph tag ```<p>``` with an ```id``` of something such as the word "display". Next, in your JavaScript, you need to use a function called 
```document.getElementById(<your id>).textContent = <your object>.<your property>```
By doing this, the JavaScript finds the HTML element that has the id, and sets it's text to the object property from the localStorage. Another option is to use ```innerHTML``` instead of ```textContent``` which uses element tags inside the string, versus just taking it as a literal string such as "<b>Josh</b>". 

Here are a couple screenshots to show the before and after, when using this function, along with what the local storage looks like. The screenshots are taken before and after clicking the "Save Student" button.

[




