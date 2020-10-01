# jQuery and Paired Programming

jQuery is useful when we need to use JavaScript tasks and is consistent across all browsers with no fallback using three methods:

1. **Select Elements** - Like CSS, jQuery uses selectors.

2. **Perform Tasks** - Simplified way to manipulate the DOM in one line of code.

3. **Handle Events** - Attach event listeners to the elements without fallback codes for browsers.

To use jQuery, we use `jQuery()`, or `$()` for shorthand, and inside the parenthasis, we put a CSS-style selector.

An example is can be shown below:

```
$('li.hot').addClass('complete');
```

```
$(':header').addClass('headline');
$('li:lt(3)').hide().fadeln(l5OO);
$('li').on('click', function() {
  $(this).remove();
});
```

Pros:

- Simple selectors
- Common tasks in less code
- Cross-browser compatibility 


# Pair Programming

Pair Programming is where two people are working on code together, but each person has a different role. Pair Programming consists of two roles: Driver and Navigator.

Driver - Writes code and handles the mechanics wuch as switching files, version control, and writing code.
Navigator - Guides the driver and thinks about what to do next and converts algorithms to code. The Navigator can look up solutions on another screen, but doesn't write code.
There are six benefits to pair programming:

Greater Efficiency - Pair programming may be slow, but can produce high-quality code, which means less time debugging.

Engaged Collaboration - The focus is to get the code done and people are less likely to slack-off when they are relying on each other.

Learning from Fellow Students - We can learn new methods from each other, opening up new ideas to attack problems.

Social Skills - Navigating code can help with communication skills.

Job Interview Readiness - Pair programming can show-off your collaboration skills to the employer. Learning from others and working well with them is a desired skill.

Work Environment Readiness - Pair programming can equip us with skills that normal Computer Science Majors dont have after graduating college.

[Back to Home Page](https://kmangub.github.io/reading-notes-master/)