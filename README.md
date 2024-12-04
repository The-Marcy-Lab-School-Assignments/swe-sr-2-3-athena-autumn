# Technical Writing Assignment

**Fixed Version**

For guidance on setting up and submitting this assignment, refer to the Marcy lab School Docs How-To guide for [Working with Short Response and Coding Assignments](https://marcylabschool.gitbook.io/marcy-lab-school-docs/fullstack-curriculum/how-tos/working-with-assignments#how-to-work-on-assignments).

## Prompt 1

What are the main differences between Flexbox and Grid layouts? Describe scenarios where each layout system would be more suitable.

### Response 1

CSS provides two crucial layout systems to help a developer design and align elements properly on a webpage. These layout systems allow for easier spacing and positioning; developers no longer have to precisely position every element.

1. **Flexbox** offers a **1-dimensional** layout system that aids in _alignment_ of items, particularly in a **single row or column**. You have many styling properties available in terms of positioning these items, such as _creating even space between them, or aligning the items to be in the center of the page_. These are built-in to CSS, so you do not need to meticulously style each element to use these properties.
2. **Grid** offers a **2-dimensional** layout system, allowing us to place and style elements in different **vertical and horizontal alignments at the same time**. Grid allows us to control exactly how many rows/columns we want certain elements to take up. Similar to **Flexbox**, you can align and space items in a variety of preformatted ways.

When you want to style items in a **single** row or column, use **Flexbox**. When you want to style items in **multiple** rows and columns, use **Grid**.

## Prompt 2

What is the difference between `justify-content` and `align-items` in Flexbox? How does each property control the positioning of flex items within the container?

### Response 2

In Flexbox, there are built-in properties that allow us to vertically and horizontally align items. We must select our `flex-direction` first, either row, or column. The flex direction then dictates what the properties `justify-content` and `align-items` do.

`justify-content` controls alignment of items on the main axis of the Flexbox. This axis will be the same as your `flex-direction`.

`align-items` controls alignment of items on the cross axis. This axis is perpendicular to the `flex-direction`.

For example, if I wanted to adjust a row of items to be aligned to the bottom right of the page, the code would look something like this:

```css
.container {
  display: flex;
  flex-direction: row;
  justify-items: end;
  /* moves items to the right of screen */
  align-items: end;
  /* moves items to the bottom of screen */
}
```

## Prompt 3

Describe the difference between `grid-template-areas` and `grid-template-columns`/`grid-template-rows`. When might you prefer one approach over the other?

### Response 3

There are a few ways to create and size grids in CSS. The first way is using the `grid-template-areas` property. This property allows you to created named areas in a grid using **strings** (or words). The exact placement of these strings will create **defined containers** in the grid with those strings as labels.

For example: this grid is a rough draft of the main elements of a webpage. Notice how there are no elements missing and a full grid is created. This is necessary when using this property.

```css
.container {
  display: grid;
  grid-template-areas:
    "header header"
    "sidebar main"
    "footer footer";
}
```

The other way to create grids using CSS is by using `grid-template-columns`/`grid-template-rows`. These properties allow for more **precise control** over specific sizing of each elements column/row size. It's good practice to use **fractional units** when defining the exact sizing of your columns/rows. This makes sure your elements are **proportional** to each other. Here is an example of how you would create a grid using these properties:

```css
.container {
  display: grid;
  grid-template-columns: 1fr 3fr;
  grid-template-rows: auto 1fr auto;
}
```

## Prompt 4

Explain the `min-width` and `max-width` keywords in media queries. How do they help create responsive breakpoints for different screen sizes?

### Response 4

> The `min-width` and `max-width` keywords in media queries are used to define **minimum** and **maximum** constraints for applying specific styles. They help create responsive breakpoints by targeting different screen sizes and adjusting the layout accordingly.
>
> - `min-width`: applies styles when the viewpoint width is at least the specified value, often used for mobile first approach. Additional styles are applied as the screen size increases.
> - `max-width`: applies styles when the viewpoint width is no greater than the specified value, often used in desktop first approach, where styles for larger screens are defined first and scaled down for smaller devices.
>
> Example 1 applies to styles to screens smaller than or equal to `1250px`:
>
> ```css
> @media (max-width: 1250px) {
>   /* ... */
> }
> ```
>
> Example 2 applies styles to screens between `30em` and `50em` wide:
>
> ```css
> @media (min-width: 30em) and (max-width: 50em) {
>   /* ... */
> }
> ```

## Prompt 5

Imagine you are teaching a brief lesson on **mobile first design**. Your lesson should include the following information:

- An explanation of mobile first design and a few of the benefits of this approach
- A CSS code example demonstrating how to use media queries to adjust the layout of a container from mobile to desktop with either Flexbox or Grid (choose one).
- An explanation of the code example.

### Response 5

> **Mobile first design** is an approach where developers design websites starting with the smallest screens (mobile) and then progressively enhance the layout and functionality for larger screens like tablets and desktops.
>
> **Benefits of Mobile First Design:**
>
> - It ensures the website is responsive, effective, and user-friendly on mobile devices, where most users access the web.
> - The approach prioritizes core content and functionality, making it easier to build up features for larger screens without overloading the design.
> - It enhances the user experience across devices, increasing website traffic and engagement.
>
> **Example:**
>
> ```css
> /* Mobile styling */
> .container {
>   display: flex;
>   flex-direction: column;
>   gap: 10px;
>   padding: 10 px;
> }
>
> .item {
>   text-align: center;
>   padding 20px;
>   border: 1px solid;
> }
>
> /* Tablet and larger screens styling */
> @media (min-width: 768px) {
>   .container {
>     flex-direction: row;
>   }
> }
> ```
>
> **Explanation:**
>
> - In _mobile styling_, the `.container` uses flexbox with `flex-direction: column`, so the items are stacked vertically. A gap of `10px` adds spacing between items.
> - For _larger screens styling_ with the minimum width of `768px`, the `@media` query applies when the screen width is at least `768px`. The `.container` switches to a horizontal layout, `flex-direction: row`, displaying items side by side.
>   This approach demonstrates how **mobile first design** prioritizes smaller devices and enhances the layout progressively as the screen size increases.
