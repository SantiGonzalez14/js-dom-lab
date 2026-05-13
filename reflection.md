## `Array.isArray(divList)` returns false even though `divList` looks like an array. Why is that, and which workaround did you use in TODO 2 (and why)?

`divList` is actually a `NodeList`, not a true array object, so `Array.isArray(divList)` returns `false`. Although a `NodeList` looks similar to an array, 
it does not support all array methods. To solve this, I used the spread operator (`...`) to copy the `NodeList` into a real array so that array methods could be used on it.

## What does `event.preventDefault()` do in TODO 5, and what happens if you forget it? (Try removing it and see.)

`event.preventDefault()` prevents the browser’s default behavior for an event. In this case, it prevents the page from reloading when the form is submitted, 
allowing the custom JavaScript behavior to finish running. If it is removed, the page reloads immediately after submission, which can interrupt or reset the JavaScript changes on the page.

## In TODO 4a you used `btn.dataset.member` instead of writing four separate event listeners. Why is the `data-*` approach better as the app grows?

Using `btn.dataset.member` makes the code more scalable and maintainable. Instead of writing a separate event listener for every button, the same logic can 
work for all buttons dynamically. If more buttons are added later, no additional event listener code is needed.

## `.innerText` vs `.innerHTML` — when would you reach for each one? Bonus: what's a security risk with putting user-typed text into `.innerHTML`?

`.innerText` is used when working with plain text content inside an element. `.innerHTML` is used when you need to read or modify the HTML structure inside an 
element, including tags and nested elements.

A security risk of using `.innerHTML` with user-provided input is that users could inject malicious HTML or JavaScript into the page. This can lead to Cross-Site 
Scripting (XSS) attacks, where harmful scripts are executed in another user’s browser.
