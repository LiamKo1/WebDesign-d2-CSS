# Problem: Accessible HTML Forms

In this exercise, you'll practice working with HTML, in particularly modifying content to be more **accessible** by using semantic elements. You'll also learn to structure HTML forms!

To complete the exercise, modify the included `index.html` file (which displays a simple blog) based on the below instructions. You will **not** need to modify the CSS (which has been included to make the page look at little nicer, _AND_ to give some visual hints when you're on the right track!).

In particular, you will need to make the following changes:

1. Web pages should be organized using _semantic sectioning_ elements, which makes them easier to navigate for screen readers by providing ARIA navigation landmarks. Note that adding these elements will also apply some styling (so you can visually check that it's right!). Add the following elements:

	- Both the "Page Title" elements should be in a single `<header>` element.

	- All of the "Image Post" and the "Comment Form" elements should be in a `<main>` element. The "Image Post" elements should then be in a `<section>` (inside of the `<main>`), while the "Comment Form" elements should be a second `<section>` in the `<main>`.
	
	- In addition, the first two elements of the "Image Post" ("The Cutest Puppy!" and "Posted last year") should be in a `<header>` element that is inside of that `<section>`&mdash;the header of that section!

  - The "Author Info" elements should be in a single `<footer>` element.

2. Heading elements (e.g., `<h1>`, `<h2>`) should be used appropriately. 

	- Headings should be **meaningful**, used for actual headings and not for styling. Change the `<h6>` element so that it is instead a paragraph element with the class **`time-posted`**; that class will apply the provided CSS to style the element (rather than using the styling provided by the `<h6>` tag)

	- Headings should also be **hierarchical** (in order, `h3` following `h2 ` without skipping levels). Change the `<h3>` so it is the appropriate level. Headings are used to define a "table of contents" for your page!

3. HTML elements can provide further annotations to help machines semantically understand them (for search engine optimization, etc). Wrap the words "last year" (in "Posted last year") in a [`<time>` element](https://css-tricks.com/time-element/). Be sure to include an attribute to indicate that the phrase "last year" in this case refers to the date "Sep 01, 2019". 

4. Make sure the image has an `alt` attribute so that is properly read by screen readers (the description is up to you&mdash;remember that `alt` should finish the sentence "an image of...").

5. The text currently include a number of `<i>` elements. This element has no actual semantic meaning, so you should fix that!

	- Where the `<i>` is used for emphasis, replace it with an `<em>` element.
	- Where the `<i>` is used to mark a citation, replace it with a `<cite>` element.

6. The "Comment Form" is an example of a **form**&mdash;a set of elements that collect user input for processing. Users can type values into the `<input>` boxes. But you'll need to make some modifications to ensure that this form is accessible and functional:

	- An `<input>` element can have a `type` attribute which indicates what kind of input it is. Give the "email" input a `type` of `"email"` and the "password" input a `type` of `"password"`. The later has the most noticable effect, hiding the password being typed.

	- Each input element will need an attribute `name` that will let form processing identify which field the user input is for. Give the "email" input a `name` of `"email"`, the "password" input a `name` of `"password"`, and the "comment" input (the `<textarea>`) a `name` of `"comment"`. 
	
		Yes, this makes forms have a lot of redundancy. The `id` is used for referring to the element, the `type` indicates what it's used for, and the `name` is used for tracking the value of that input.

	- The text describing what each `input` is for should be put in a `<label>` element (to indicate that it is a label for that input). Each `<label>` will need a `for` attribute whose value is the `id` of the `input` that label is associated with. When this is set up, you can click on the label and the cursor will jump to the appropriate input!

		Add a `<label>` for _each_ of the 3 input: the two `<input>` elements and the `<textarea>`.
	
	- The "submit" button just has a picture of a pencil instead of a readable word. To make sure that image is understood by screen readers, give the icon (the `<i>` element) and `aria-label` attribute with a value of `"Submit"`. This is similar to adding an `alt` attribute, but works for elements that aren't `img`.

7. Finally, the footer needs some additional markup to make its semantic meaning clear:

	- The sentence containing contact information ("Contact me at...") should be inside of an [`<address>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/address) element instead of a `<p>`. Note that the `<address>` element is only for contact information, not for general postal addresses.

	- Make sure that the [email](https://css-tricks.com/snippets/html/mailto-links/) and [telephone](https://css-tricks.com/the-current-state-of-telephone-links/) number are both links (`<a>`) with proper URI protocols!

	- Replace the word "copyright" with an [HTML Character Entity](https://developer.mozilla.org/en-US/docs/Glossary/Entity) for the copyright symbol. This will ensure that the symbol renders no matter the language settings of the computer.
