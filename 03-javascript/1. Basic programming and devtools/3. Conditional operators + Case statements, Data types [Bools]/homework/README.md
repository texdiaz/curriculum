## Important
For follow exercise, you'll need use **alert** and **prompt**.
And you always should use the template for to do exercises.

- The **prompt(message, defaultOption)** displays a dialog with an optional message prompting the user to input some text.
  The second parameter is optional.Te second parameter print option for default.

Example:
```javascript
     let name = prompt("Please enter your name", "Harry Potter");
     console.log(name);
    
     let response = prompt("How are you?");
     console.log(response);
```
![prompt](prompt.jpg)

- The **alert(message)** method displays an alert dialog with the optional specified content and an OK button.

Example:
```javascript
    alert("this is one message");
```

![alert](alert.jpg)


#Homework

 1. You ask "What are you name" for this use alert and print the next greeting with the user answer.

 2. You ask "What is the main conditional structure?" if that answer is equal "if" you show "correct", otherwise show "incorrect".

 3. You ask "Which is current temperature?" if temperature is less than zero you show "you need blanket", otherwise show "you are fine".  

 4. You ask "How old are you?" and if the user is of legal age or mayor you show "you are of legal age" otherwise show "you aren't of legal age".
 
 5. You ask "How much is 1 + 1?" and before you ask "How much is 5 x 10?"
        - if both answers are fail you show "Sorry, you you answered incorrectly all question. You can try again."
        - if only answered correctly the first you show "Congratulations, you answered correctly the first question"
        - if only answered correctly the second you show "Congratulations, you answered correctly the second question"
        - if answered correctly all question you show "Congratulations, you answered correctly the second question"
