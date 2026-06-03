# CSS-Theory
Cascading Style Sheets (CSS) is a styling language used to design web pages ✨. It changes colors 🎨, fonts 🔤, layouts 📐, and makes websites attractive 🌈 and responsive 📱.

---

## **Q1. What is CSS and how do you add it to an HTML page?**

**Ans:** CSS stands for (Cascading style sheets). It is Used to design and style web pages. CSS changes the colors, fonts, spacing, layout, and overall look of a website.

CSS solves the problem of making websites attractive and organized. Without CSS, web pages only show simple HTML content without styling.

**There are three ways to add CSS to an HTML document:** 

### **1. Inline CSS**
- Inline CSS is written inside the HTML tag using the style attribute.
```html
<p style="color: blue;">Hello World</p>
```

### **2. Internal CSS**
- Internal CSS is written inside the `<style>` tag in the `<head>` section.
```html
<head>
<style>
h1 { 
    color: red;
}
</style>
</head>
```

### **3. External CSS**
- External CSS is written in a separate .css file and linked with HTML.

**HTML:**
```html
<head>
<link rel="stylesheet" href="style.css">
</head>
```

**Style.css:**
```css
body{
    background-color: lightgray;
}
```

**Which method is recommended?**
- ✅ External CSS is recommended in real projects because:
  - Code stays clean
  - One CSS file can style many pages
  - Easy to manage and update
  - Faster website maintenance

---

## **Q2. Explain CSS Selectors with examples?**

**Ans:** CSS Selectors are used to target HTML elements and apply styles.

### **1. Element Selector**
- Targets HTML tags directly
```css
p{
    color: green;
}
```

### **2. Class Selector**
- Targets elements with a class name.
```css
.note{
    color: blue;
}
```
```html
<p class="note">Text</p>
```

### **3. ID Selector**
- Targets a unique element using ID.
```css
#title{
    color: red;
}
```
```html
<h1 id="title">Heading</h1>
```

### **4. Group Selector**
- Applies same style to multiple elements.
```css
h1, p{
    font-family: Arial;
}
```

### **5. Descendant Selector**
- Targets elements inside another element.
```css
div p{
    color: purple;
}
```

### **6. Child Selector**
- Targets direct element only.
```css
div > p{
    color: orange;
}
```

### **7. Universal Selector**
- Targets all elements.
```css
*{
    margin: 0;
}
```

**Important Points:**
- ⚠️ ID selector has higher specificity than class selector
- ✅ A class can be used on multiple elements
- ✅ An ID should only be used once on a page
- ✅ Descendant selector targets all nested elements
- ✅ Child selector targets only direct children

---

## **Q3. What is the CSS Box Model?**

**Ans:** The CSS Box Model explains how every HTML element is shown as a rectangular box.

**It has four Layers:**

### **1. Content**
- The actual text or image inside the element.
```css
width: 200px;
height: 100px;
```

### **2. Padding**
- Space between content and border.
```css
padding: 20px;
```

### **3. Border**
- The outline around padding and content.
```css
border: 2px solid black;
```

### **4. Margin**
- Space outside the border.
```css
margin: 15px;
```

**Box-Sizing**

### **content-box** (Default)
- Default sizing method
```css
box-sizing: content-box;
```
- Width and height only include content.

### **border-box**
- Width and height include content, padding, and border.
```css
box-sizing: border-box;
```

**Which is used in professional projects?**
- ✅ **border-box** is mostly used in professional projects because it makes layouts easier and more accurate.

**Other Points:**
- 🔹 Innermost Layer: content
- 🔹 Padding: Inside the Border
- 🔹 `margin: 0 auto`: Sets top/bottom margin 0, left/right auto. Centers a block element horizontally if it has a fixed width.
- 🔹 `box-sizing: border-box`: Yes, width includes padding + border. Total width stays 300px. With content-box the total would be 300px + 20px×2 + 2px×2 = 344px.

**Code Task - CSS rule:**
```css
.box {
    width: 300px;
    padding: 20px;
    border: 2px solid black;
    margin: 16px;
    box-sizing: border-box;
}
```

---

## **Q4. Explain CSS Colors. What are the different ways to define a color?**

**Ans:** CSS colors set text, background, border colors, etc.

**5 Main Formats:**

### **1. Named**
- Predefined color names. Most readable but limited.
```css
color: orange;
```

### **2. HEX**
- 6-digit hex code, #RRGGBB. Most commonly used by developers.
```css
color: #f97316;
```

### **3. RGB**
- Red, Green, Blue values 0-255.
```css
color: rgb(249, 115, 22);
```

### **4. RGBA**
- RGB + Alpha for transparency. A in RGBA stands for Alpha (opacity 0 to 1).
```css
color: rgba(249, 115, 22, 0.5);
```

### **5. HSL**
- Hue, Saturation, Lightness. Easier for humans to adjust shades.
```css
color: hsl(24, 94%, 53%);
```

**Code Task - #f97316 in all 5 formats:**
```css
color: orange;                   /* Named */
color: #f97316;                  /* HEX */
color: rgb(249, 115, 22);        /* RGB */
color: rgba(249, 115, 22, 1);    /* RGBA */
color: hsl(24, 94%, 53%);        /* HSL */
```

**Opacity vs RGBA difference:**
- 🔹 `opacity: 0.5` makes the whole element + all child elements 50% transparent
- 🔹 `rgba(0,0,0,0.5)` only makes the background color 50% transparent. Child elements stay full opaque
- ⚠️ Opacity affects children, RGBA does not

---

## **Q5. What are CSS Units? Explain px, %, rem, em, vh, and vw.**

**Ans:** CSS units define sizes.

### **1. px - Pixels**
- Fixed, absolute units. 1px = 1 screen dot
- **Use case:** Borders, fixed UI elements
```css
border: 2px solid black;
```

### **2. % - Percent**
- Relative to parent element's same property
- **Use case:** Fluid layouts, responsive widths
```css
width: 50%; /* 50% of parent Width */
```

### **3. rem - Root em**
- Relative to root html font-size
- Default 1rem = 16px unless changed
- **Use case:** Font-size, spacing. Scales with user browser setting = better for accessibility
```css
font-size: 1.5rem; /* 24px if root is 16px */
```

### **4. em - Element em**
- Relative to parent element's font-size
- **Use case:** Padding/margin that should scale with text-size
- If parent font-size: 20px, then 1em = 20px

### **5. vh - Viewport Height**
- 1vh = 1% of browser window Height
- **Use case:** Full-screen sections, hero banners
```css
height: 100vh; /* full screen Height */
```

### **6. vw - Viewport Width**
- 1vw = 1% of browser window Width
- **Use case:** Font-size that scales with screen width
```css
font-size: 5vw;
```

---

## **Q6. What is CSS specificity and how does the Cascade work?**

**Ans:** Specificity = rules for which CSS selector "wins" when multiple rules target the same element. Browser gives each selector a score.

**Specificity score order (high to low):**
- 🔴 Inline style > 🟠 ID > 🟡 Class/Pseudo-class/Attribute > 🟢 Element/Pseudo-Element

**Score:**
- Inline = 1000
- ID = 100
- Class = 10
- Element = 1

**1. Class vs Element:**
- Class has higher specificity. `.text` = 10, `p` = 1

**2. Inline style score:**
- 1000 - Example: `<p style="color: red">`

**3. Equal specificity:**
- Last rule in source order wins - "last declared wins"

**4. !important:**
- Overrides everything except another !important later in code
- ⚠️ Should be avoided because it breaks the cascade and makes debugging hard

**Cascade = how browser decides:**
1. Source order
2. Specificity
3. Inheritance

**Code task:**
```html
<p id="intro" class="text">Hello</p>
```

```css
p { color: blue; }          /* Score 1 - loses */
.text { color: green; }     /* Score 10 - loses */
#intro { color: red; }      /* Score 100 - WINS */
```

✅ Red wins because ID has highest specificity.

---

## **Q7. Explain CSS Flexbox. How does it differ from block layout?**

**Ans:** Flexbox = 1D layout system for arranging items in one row or column. Set `display: flex` on parent container to make it a flex container. Children become flex items.

**Block layout Vs Flexbox:**
- 🔹 Block stacks elements vertically, takes full width, hard to center
- ✅ Flexbox gives 1D control over alignment, spacing, and order both horizontally + vertically

**Key properties:**

### **1. flex-direction**
- Row or column
- `row` = horizontal, `column` = vertical

### **2. justify-content**
- Align items on main axis
- Values: `center`, `space-between`, `flex-end`

### **3. align-items**
- Align items on cross axis
- `center` = vertically center

### **4. flex-wrap**
- Wrap lets items move to next line instead of shrinking

### **5. gap**
- Space between items

### **6. flex: 1**
- Item grows to fill available space equally

**justify-content vs align-items:**
- 🔹 Main axis vs cross axis
- 🔹 For `flex-direction: row`, justify = horizontal, align = vertical

**Center both axes:**
```css
justify-content: center;
align-items: center;
```

**Real-world use cases:**
- ✅ Navbars
- ✅ Card layouts
- ✅ Centering elements

**Code task - Navbar:**
```css
.navbar {
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 2rem;
}
```

---

## **Q8. What are CSS Pseudo-classes and Pseudo-elements?**

**Ans:** Both style elements without adding HTML, but different:

- 🔹 **Pseudo-classes:** Style elements based on state/position
- 🔹 **Pseudo-elements:** Style parts of an element or add virtual content

### **Key Pseudo-classes:**

**1. :hover**
- When mouse is over element
```css
button:hover { background: orange; }
```

**2. :focus**
- When input/element is clicked/selected

**3. :nth-child(2n)**
- Select even elements
- `2n+1` = odd, `3n` = every 3rd

**4. :not()**
- Selects elements NOT matching
```css
p:not(.skip) { color: blue; }
```

### **Key Pseudo-elements:**

**5. ::before, ::after**
- Insert virtual content before/after element
- Need `content: ""` property or they won't show
- ⚠️ Does NOT add real HTML

**6. ::placeholder**
- Styles placeholder text in inputs

**Code task:**
```css
button:hover {
    background: orange; /* turns orange on hover */
}

.featured::before {
    content: "* "; /* adds star before .featured items */
}

input::placeholder {
    color: grey; /* styles placeholder text */
}
```

---

## **Q9. CSS Transitions vs Animations?**

**Ans:**
- 🔹 **Transition** = Smooth change from A to B. Needs trigger like `:hover`
- 🔹 **Animation** = Uses `@keyframes`. No trigger needed, runs on load

**Syntax:**
```css
transition: property duration timing delay;
animation: name duration timing forwards;
```

**Key Points:**
- 🔹 `ease` = slow-fast-slow, `linear` = constant speed
- 🔹 `forwards` = stays at final keyframe
- 🔹 `infinite` = loops forever
- ✅ Use `transform` + `opacity` for speed. `width`/`margin` = slow

**Code task:**
```css
.card {
    transition: transform 0.3s;
    animation: fadeUp 0.6s forwards;
}

.card:hover {
    transform: translateY(-10px);
}
```

---

## **Q10. Responsive Web Design?**

**Ans:** RWD = Site adjusts to all screen sizes.

**Media Query:**
```css
@media (min-width: 768px) { ... }
```
- `min-width` = mobile-first
- `max-width` = desktop-first

**Breakpoints:**
- 📱 Mobile < 640px
- 📱 Tablet 768px
- 🖥️ Desktop 1024px+

**Dark Mode:**
```css
@media (prefers-color-scheme: dark) { ... }
```

**CSS Variables:**
```css
--color: blue;
```
- Defined in `:root`
- Use with `var(--color)`
- Dark mode easy: `[data-theme='dark'] { --bg: black; }`
- JS can read/change variables too

**Mobile-first = Better:**
- ✅ Base CSS for mobile, then add with `min-width`
