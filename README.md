# Webdev Notes


## **CSS Foundations** 
<br>

## **Selectors**: 
- Universal Selector:
  - Sets every element to be purple 

            * {
                color: purple;
            }


- Type Selectors:
    - Sets the div to be white 
            <html>

            <div> Hello World!</div>


            <css>

            div {
                color: white;
            }

        

- Class Selectors:
    - Applies attribute to specific selected class 
    - Not unique so able to reuse as many times 
    - Use '.'

            <html>

            <div class="text"> Hello there. </div>


            <css>

            .text {
                color: red;
            } 

- ID Selectors:
  - Applies attribute to specified id 
  - Uses '#'
  - Element can only have one ID 
  - ID cannot be repeated and should have no whitespace

        <html>

        <div id = "title"> TITLE </div>


        <css>
        
        #title {
            background-color: red;
        }

- Grouping Selectors: 
  - Group two elements together if they share some traits

        .one,
        .two {
            color: red;
            background-color: black;
        }

- Chaining Selectors:
    - If two elements have same first word as a class we can chain class selectors together

            <html>
        
            <div>
                <div class="subsection header"> P </div>
                <p class="subsection preview"> P </p>
                <p class="subsection id="index"> P </p>
            </div>


            <css>

            .subsection.header{
                color: red; 
            }

            .subsection#index{
                color: blue; 
            }

- Descendant Combinator 
    - Selects a descendant of an ancestor
    - Uses the format: .ancestor .child to select
    - In Example, only C and D will be selected not D 

            <!-- index.html -->

            <div class="ancestor"> <!-- A -->
              <div class="contents"> <!-- B -->
                <div class="contents"> <!-- C -->
                </div>
              </div>
            </div>

            <div class="contents"></div> <!-- D -->


            /* styles.css */

            .ancestor .contents {
              /* some declarations */
            }

<br>

## **Properties**
- color: red; 
  
- background-color: red;
  
- font-family: "Times New Roman", sans-serif; 
  
- font-size: 22px;
  
- font-weight: bold, or (number between 1 and 1000);
  
- text-align: center;

- For images, use auto so image proportions are still the same 
  
        img {
            height: auto;
            width: 500px;
        }


## **Adding CSS to HTML**


### External CSS
- Most common method
- Create a seperate CSS file and link it inside HTML's head tag

        <head>
            <link rel="stylesheet" href="styles.css">
        </head>

### Internal CSS
- Adding CSS within HTML file 
- Inside the head tags

        <head>
            <style>
              div {
                color: white;
                background-color: black;
              }

              p {
                color: red;
              }
            </style>
        </head>
        <body>...</body>

### Inline CSS
- Adding CSS directly to HTML elements
- Can get pretty messy so not recommended 

<br>

    <body>
        <div style="color: white;"> ... </  div>
    </body>