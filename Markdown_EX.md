# CREDITS - https://commonmark.org/ 
# TUTORIAL LINK: https://commonmark.org/help/tutorial/

# Reference:

[Emphasis](#emphasis-and-emphasis)\
[Paragraph](#paragraphs)\
[Headings](#headings)\
[Blockquotes](#blockquotes)\
[Lists](#lists)\
[Links](#links)\
[Images](#images)\
[Code](#code)\
[Nested Lists](#nested-lists)


<!-- EMPHASIS -->

# *EMPHASIS* and **EMPHASIS**

## PART I

_INPUT:_

`The music video for Rihanna’s song __AMERICAN OXYGEN__ depicts various moments from American history, including the inauguration of Barack Obama.`

_OUTPUT:_
>The music video for Rihanna’s song __AMERICAN OXYGEN__ depicts various moments from American history, including the inauguration of Barack Obama.
>

_INPUT:_

`Why, sometimes I’ve believed as many as *SIX* impossible things before breakfast.`

_OUTPUT:_
>Why, sometimes I’ve believed as many as *SIX* impossible things before breakfast.
>

_INPUT:_

`**Everyone _MUST_ attend the meeting at 5 o’clock today.**`

_OUTPUT:_

>**Everyone _MUST_ attend the meeting at 5 o’clock today.**
>

## PART II

_INPUT:_

``` 
I am totally awesome.* 
\* for certain very small values of awesome
```

_OUTPUT:_
>
>I am totally awesome.* \
>\* for certain very small values of awesome
>

## THE END.
#
<!-- PARAGRAPHS -->

# PARAGRAPHS

PARAGRAPHS \
PARAGRAPHS \
PARAGRAPHS

EXPLAIN: 
```
A paragraph is consecutive lines of text with one or more `blank lines` between them.

For a line break, add either a backslash `\` or two blank spaces at the end of the line.
```

## EXAMPLES

_INPUT:_

```
The sky above the port was the color of television, tuned to a dead channel.

It was a bright cold day in April, and the clocks were striking thirteen.
```

_OUTPUT:_
>The sky above the port was the color of television, tuned to a dead channel.
>
>It was a bright cold day in April, and the clocks were striking thirteen.
>

_INPUT:_
```
I have eaten\
the plums\
that were in\
the icebox
```

_OUTPUT:_
>I have eaten\
>the plums\
>that were in\
>the icebox

## THE END.
#
<!-- HEADINGS -->
# HEADINGS

EXPLAINS:
```
Starting a line with a hash `#` and a space makes a header.

The more `#`, the smaller the header.
```

## EXAMPLES

### USAGE 1:

_INPUT:_
```
## Chapter 1
Something about the room made him uneasy.
## Chapter 2
It's behind you! Hurry before it
```

_OUTPUT:_
>## Chapter 1
>Something about the room made him uneasy.
>## Chapter 2
>It's behind you! Hurry before it

### USAGE 2:

_INPUT:_
```
# After the Big Bang
A brief summary of time
## Life on earth
10 billion years
## You reading this
13.7 billion years
```

_OUTPUT:_
># After the Big Bang
>A brief summary of time
>## Life on earth
>10 billion years
>## You reading this
>13.7 billion years

## THE END.
#
<!-- BLOCKQUOTES -->
# BLOCKQUOTES

EXPLAIN:
```
To create a blockquote, start a line with greater than '>' followed by an optional space.

Blockquotes can be nested, and can also contain other formatting.
```

## EXAMPLES

### USAGE 1:

_INPUT:_
```
The quote 
>Somewhere, something incredible is waiting to be known

has been ascribed to Carl Sagan.
```

_OUTPUT:_
>The quote 
>>Somewhere, something incredible is waiting to be known
>
>has been ascribed to Carl Sagan.

# USAGE 2:

_INPUT:_
```
My favorite Miss Manners quotes:

>Allowing an unimportant mistake to pass without comment is a wonderful social grace.
>
>Ideological differences are no excuse for rudeness.
```

_OUTPUT:_
>My favorite Miss Manners quotes:
>
>>Allowing an unimportant mistake to pass without comment is a wonderful social grace.
>>
>>Ideological differences are no excuse for rudeness.

## THE END.
#
<!-- LISTS -->
# LISTS

EXAPLAIN:
```
Unordered lists can use either asterisks '*', plus '+', or hyphens '-' as list markers.

Ordered lists use numbers followed by period '.' or right paren ')'.
```

## EXAMPLES

## USAGE 1:

_INPUT:_
```
- Flour
+ Cheese
* Tomatoes
```

_OUTPUT:_
>- Flour
>+ Cheese
>* Tomatoes

## USAGE 2:

_INPUT:_
```
1. Four steps to better sleep:
3. Stick to a sleep schedule
4. Create a bedtime ritual
86. Get comfortable
2198. Manage stress
```

_OUTPUT:_
>1. Four steps to better sleep:
>3. Stick to a sleep schedule
>4. Create a bedtime ritual
>86. Get comfortable
>2198. Manage stress

## USAGE 3:

_INPUT:_
```
1986\. What a great season. Arguably the finest season in the history of the franchise.
```

_OUTPUT:_
>1986\. What a great season. Arguably the finest season in the history of the franchise.

## THE END.
#
<!-- LINKS -->
# LINKS

EXPLAINS:
```
Links can be either inline with the text, or placed at the bottom of the text as references.

Link text is enclosed by square brackets [], and for inline links, the link URL is enclosed by parens ().
```

## EXAMPLES

## USAGE 1 `<"url">`:

_INPUT:_
```
You can do anything at <https://github.com/>
```

_OUTPUT:_
>You can do anything at <https://github.com/>

## USAGE 2 `["name"]("url/header")`
>If the ["header"] contains a '/', ignore it and join the words together. \
> Examples: `[IDS/IPS Suricata](#idsips-suricata)`.

_INPUT:_
```
The [University of Rwanda](http://www.ur.ac.rw) was formed in 2013 through the merger of Rwanda’s seven public institutions of higher education.
```

_OUTPUT:_
>The [University of Rwanda](http://www.ur.ac.rw) was formed in 2013 through the merger of Rwanda’s seven public institutions of higher education.

## USAGE 3 `['name']['reference_number'] and [reference_number]:'url'`:

_INPUT:_
```
[Hurricane][1] Erika was the strongest and longest-lasting tropical cyclone in the 1997 Atlantic [hurricane][1] season.

[1]:https://w.wiki/qYn
```

_OUTPUT:_
>[Hurricane][1] Erika was the strongest and longest-lasting tropical cyclone in the 1997 Atlantic [hurricane][1] season.
>
>[1]:https://w.wiki/qYn

## THE END.
#
<!-- IMAGES -->
# IMAGES

EXPLAIN:
```
Images are almost identical to links, but an image starts with an exclamation point !.
```

## EXAMPLES

## USAGE 1 `![]('image_path')`:

_INPUT:_
```
![](https://commonmark.org/help/images/favicon.png)
```

_OUTPUT:_
>![](https://commonmark.org/help/images/favicon.png)

## USAGE 2: 
```
!['alternative_text'][reference_number]

[refernce_number]:'url'"title_text"
```

_INPUT:_
```
![Logo][1]

[1]: https://commonmark.org/help/images/favicon.png "Creative Commons licensed"
```

_OUTPUT:_
><p><img src="https://commonmark.org/help/images/favicon.png" alt=""></p>

## THE END.
#
<!-- CODE -->
# CODE

EXPLAIN:
```
To create inline code, wrap with backticks `.

To create a code block, either indent each line by 4 spaces, or place 3 backticks ``` on a line above and below the code block.
```

# USAGE 1 `code`:

_INPUT:_
```
When `x = 3`, that means `x + 2 = 5`
```

_OUTPUT:_
>When `x = 3`, that means `x + 2 = 5`

## USAGE 2 '''code''':

_INPUT:_
```
    Who ate the most donuts this week?
    ```
    Jeff  15
    Sam   11
    Robin  6
    ```
```

_OUTPUT:_
>Who ate the most donuts this week?
>```
>Jeff  15
>Sam   11
>Robin  6
>```

## MORE EXAMPLES:

_INPUT:_
```
    A loop in JavaScript:
    ```
    var i;
    for (i=0; i<5; i++) {
    console.log(i);
    }
    ```

    What numbers will this print?
```

_OUTPUT:_
>A loop in JavaScript:
>```
>var i;
>for (i=0; i<5; i++) {
>  console.log(i);
>}
>```
>
>What numbers will this print?

## THE END.
#
<!-- NESTED LISTS -->
# NESTED LISTS

EXPLAIN: 
```
To nest one list within another, indent each item in the sublist by four spaces. You can also nest other elements like paragraphs, blockquotes or code blocks.
```

## EXAMPLES

## USAGE 1:

_INPUT_:
```
* Fruit
  * Apple
  * Orange
  * Banana
* Dairy
  * Milk
  * Cheese
```

_OUTPUT_:
>
> * Fruit
>   * Apple
>   * Orange
>   * Banana
> * Dairy
>   * Milk
>   * Cheese

## USAGE 2:

_INPUT_:
```
+ World Cup 2014
  1. Germany
  2. Argentina
  3. Netherlands
+ Rugby World Cup 2015
  1. New Zealand
  2. Australia
  3. South Africa
```

_OUTPUT_:
> + World Cup 2014
>   1. Germany
>   2. Argentina
>   3. Netherlands
> + Rugby World Cup 2015
>   1. New Zealand
>   2. Australia
>   3. South Africa

## MORE EXAMPLES:

_INPUT_:
```
1. Ingredients

    - spaghetti
    - marinara sauce
    - salt

2. Cooking

   Bring water to boil, add a pinch of salt and spaghetti. Cook until pasta is **tender**.

3. Serve

   Drain the pasta on a plate. Add heated sauce. 

   > No man is lonely eating spaghetti; it requires so much attention.

   Bon appetit!
```

_OUTPUT_:
><ol>
><li>
><p>Ingredients</p>
><ul>
><li>spaghetti</li>
><li>marinara sauce</li>
><li>salt</li>
></ul>
></li>
><li>
><p>Cooking</p>
><p>Bring water to boil, add a pinch of salt and spaghetti. Cook until pasta is <strong>tender</strong>.</p>
></li>
><li>
><p>Serve</p>
><p>Drain the pasta on a plate. Add heated sauce.</p>
><blockquote>
><p>No man is lonely eating spaghetti; it requires so much attention.</p>
></blockquote>
><p>Bon appetit!</p>
></li>
></ol>

# THE END!!!
