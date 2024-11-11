## Document.designMode

![image](https://github.com/user-attachments/assets/dd0d258b-79a6-43ef-af4a-d45031d48239)

Ahora hago clic en los textos y puedo reescribir lo que yo quiera haciendo click.

## Document.title
![image](https://github.com/user-attachments/assets/82237634-775e-48fe-99b7-c087a9741794)

## Document.URL
![image](https://github.com/user-attachments/assets/693c2d44-3c59-4bef-92bb-9d70a431ad6c)

## Document.cookie
![image](https://github.com/user-attachments/assets/f93f4ea6-9bea-4514-bda4-9a5b9c593a5e)

## Document DOM

**document.getElementById()**
  
      // Select the div by its ID
      const myDiv = document.getElementById("myDiv");

  **document.querySelector()**
      
      // Select the first paragraph within the container
      const firstParagraph = document.querySelector(".container p");

  **document.querySelectorAll()**
  
      // Select all elements with the class "paragraph"
      const paragraphs = document.querySelectorAll(".paragraph");
    


### Consumen muchos recursos
  **document.getElementsByName()**

    // Select all elements with the name attribute
    const inputFields = document.getElementsByName("*");
    
  **document.getElementsByClassName()**

    // Select all elements with the class "special"
    const specialElements = document.getElementsByClassName("special");

  **document.getElementsByTagName()**

    // Select all paragraph elements
    const paragraphs = document.getElementsByTagName("p");
