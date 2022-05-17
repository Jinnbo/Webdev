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


## **The Box Model** 
- Everything on a webpage is a rectangular box 

        * {
            border: 2px solid red;
        }

- Padding:
  - Space between edge of box and content inside box

- Margin:
  - Space between box and other things around the box
  - Can specify area with: margin-top, margin-bottom, margin-left, margin-right

- Border:
  - Space between margin and padding 
  - border-width: 5px;
  - border-color: red;
  - border-style: solid;
  - border: 5px solid red;

<br>

- box-sizing: border-box;
  - Size of content is the actual width and height of element
  - If border-box was not included, you would need to add padding, margin, border in order to find the actual width and height 

### **Collapsing margins**
- For vertical (top and bottom) margins, only the **larger** px value will take effect
- In example below, the margin will be **40 px**

        h2 {
            margin: 0 0 20px 0;
        }

        div {
            margin-top: 40px;  
        }

        p {
            margin-top: 30px;
        }
    
<br>

### **Negative Margins**
- Negative margins pull element itself in that direction 


<br>

## **Block**
- Block elements appear stacked atop of each other, so each new element is on a new line 
- Always takes up full width
- Commonly used with < p> and < div>
- Uses syntax:
  - display: block;
- Elements don't sit side by side but rather on top of each other 


## **Inline**
- Appear in line with the element they are placed beside 
- The < a> tag will not start on a new line, but rather on the same line
- display: inline - width and height are not respected so things may overlap
- display: inline-block - width, height, padding are respected so no overlap and elements sit side by side 


### **Span**
- Like a div but inline and used for grouping parts of text

        <p>
        Lorem ipsum dolor sit amet <span class="highlight"> quis nostrud <a href="https:/   /www.dictionary.com/browse/   exercitation">exercitation</a>
        ullamco laboris</span> nisi ut aliquip ex ea commodo    consequat.   
        </p>

<br>

## **FlexBox**
- Method of positioning/arranging items into rows or columns
- A flex container includes:
  - display: flex;
- A flex item is any element inside the flex container 
- flex syntax:
  - flex: flex-grow flex-shrink flex-basis (percentage);
  - flex: 0 1 0% <- Default property 

<br>

### Flex-grow
- Growth factor 
- <mark>flex: 1</mark> tells every div inside container to grow by same amount 
- Applying <mark>flex: 2</mark> to only one div will make that div 2x the size compared to others 

<br>

### Flex-shrink
- Shrink factor 
- Only applied if size of all flex items is larger than parent container

<br>

### Flex-basis
- Sets initial size of flex item 
- In percentage

<br>

## **Axes**
- flex-direction: column; <- puts main axis vertical; affects height 
- flex-direction: row; <- puts main axies horizontal; affects width
- Default is flex-direction: row;
- Cross axes is perpendicular to main axes
- When using flex-direction, set flex-basis to auto

<br>

## **Alignment**
- Use <mark>justify-content:</mark> to align items across main axis
- Defaults to flex-start
- Possible values: 
  - flex-start
  - flex-end
  - center
  - space-around
  - space-between
  - space-evenly

- Use <mark>align-items:</mark> to align items across cross axis 
- Defaults to stretch 
- Possible values:
  - stretch;
  - flex-start
  - flex-end
  - center
  
- Applying <mark> gap: 10px</mark> on a flex container sets space between flex items
    
- Use <mark>flex-warp: wrap;</mark> to make divs wrap if there is not enough space
  
- Use <mark>flex-wrap: nowrap;</mark> to make divs shrink to fit container

- <mark>flex: flow</mark> combines flex-direction and flex-wrap together 