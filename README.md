# Async programming with jQuery's $.Deferred()

## Background

On February 25, at the HTML5-IL meetup event, I presented a session on jQuery's $.Deferred() object, and its usage for asynchronous JavaScript programming.
The slides for this session can be found here: https://docs.google.com/presentation/d/1rR7erNBn1HCBFK1lqv0W_S9zevXAAgcFBiCSM70Udsk/edit?usp=sharing

As part of this session, I included several "homework" exercises to test the attendees’ knowledge of JavaScript, and their understanding of information presented. Here are the questions:

## Homework

### Exercise #1

List JavaScript APIs inside the browser that are blocking, besides windows.alert(), window.confirm() and window.prompt()

### Exercise #2

What is the output for:

    $(document.body).append('<div>1</div>');
    var d = $.Deferred();
    d.done(function () {
        $(document.body).append('<div>2</div>');
    });
    $(document.body).append('<div>3</div>');
    d.resolve();
    $(document.body).append('<div>4</div>');
    d.done(function () {
        $(document.body).append('<div>5</div>');
    });
    $(document.body).append('<div>6</div>');

### Exercise #3

Describe how to use #.when() to wait on a list of deferreds, contained in a JavaScript array

### Exercise #4

Create $.wait() that generates promise that resolves within specified duration

    $.wait(1000).done(function () {
        alert("done");
    });

Instead of

    setTimeout(function () {
        alert("done");
    }, 1000);
	
### Exercise #5

Modify $.wait() to return a deferred, so that:
1. .reject() on the deferred cancels timer
2. .resolve() cancels timer, but immediately executes callbacks
