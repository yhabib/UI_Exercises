# Buttons Exercise - Cascade and inheritance

## Concepts
For this exercise we are going to make use of two of the most important characteristics of CSS

### Inheritance
So as we have seen with JS and Java Inheritance is about how properties and methods trickle down from an element to its children. In the case of CSS, we only care about properties.

In order to understand how it works, first we need to think about if it always makes sense to have inheritance, through these two examples:
* `font-family` is a property where we define which font do we want to use. By default all elements have it defined to `inherit` meaning that if we define it for the `body`, all its children (the whole page) are going to have this same font. If this property wasn't defined as `inherit` by default we should define for EACH element its font. 
* `background-color`: In this case the default value is `transparent`, meaning that if we define the background as red, it is not going to affect its children, and that makes sense because this property should be defined per element.


### Cascade
The cascade is about what take precedence when there is a conflict. The rules of the cascade include:

1. Later properties override earlier properties.
2. More specific selectors override less specific selectors.
3. Specified properties override inherited properties.

The cascade solves any conflict situations. It is the order in which properties are applied.


### Specificity
Is the calculation used to determine selector priority in the cascade. When two selectors apply to the same element, the one with higher specificity takes precedence.

* Inline styles have a very high specificity (1000)
* ID's have a specificity of 100
* classes/attributes and pseudo-classes add 10
* elements and pseudo-elements add 1
* Adding up all the parts in a selector chain to determine the total specificity. In case of a tie, the last selector takes precedence.

Edge-cases:
* `!important` trumps everything. 


## Example
We don't want to style each element individually, but we want to identify those common classes that we could apply to more than one element.

Lets try to style the first button of the first and second row:
```html
/* Option A */
<button class="button1Row1">Click</button>  /* Don't */
<button class="button1Row2">Click</button>  /* Don't */

/* Option B */
<button class="btn btn-default">Click</button>
<button class="btn btn-round btn-default">Click</button>
```
We can of course style each of them separately(option A) but that will be a looot of work and by definition programmers are *lazy*.

Instead of that, we can take advantage of the cascading and inheritance nature of CSS. So we identify first which styles are going to be shared through some buttons and then we make use of these classes in the button.

Now lets check what is inside these classes:

```css
.btn {
  border: 1px solid transparent;
  background-color: rgb(192, 192, 192);
  border-radius: 4px;
  width: 90px;
  height: 40px;
  font-size: 14px;
  color: rgb(51, 51, 51);
  cursor: pointer;
}

.btn-round {
  width: 80px;
  height: 80px;
  border-radius: 50%;
}

.btn-default {
  background-color: white;
  border-color: rgb(204, 204, 204);
}
```
* `.btn`: It contains the basic styles for all buttons. These styles could be later overwritten but by default every single time that we create a new button with this class is going to look like this.
* `.btn-round`: We override three properties from the `.btn` class in order to get a round button.
* `.btn-default`: We override the color propterties, so all buttons that have this class are going to have these colors.

## Description
Now is your turn to recreate the rest of the buttons, and trying to encapsulate similar styles in classes.

Some CSS attributes that are going to be useful for this exercise:
* `box-shadow`
* `transition`
* `transform`
* `flexbox`, optional