---
layout: posts
title: Why I Dig CSS Variables
date: 2018-12-12
categories: [webdev, tutorial]
share: true
---

I dig CSS variables. I had no idea such a cool thing existed before I came across them in FreeCodeCamp’s Responsive Web Design certification, but after refactoring the CSS for this site using them, I love it. I’ll admit, my admiration for CSS variables came entirely from my being extremely lazy to learn how to use SCSS with WordPress, but hey. It’s something new to me, and I enjoy it. Lets talk about it!

CSS variables can be extremely useful in reducing repetition in CSS, and in advanced cases, they can be used for cool effects like theme switching.

## Repetition in CSS

We’ve all been there. Repetition and clutter plague us all at some point, whether we like to admit it or not. Repeating color values is an example of CSS that is used constantly through a web page in order to keep styles consistent. The issue with repeating the color values in your CSS is that it’s potentially error-prone. Sure, you could “find and replace” all the things, but it could get dangerous.

## Enter Custom Properties, aka Custom Properties

These are CSS variables in a nutshell:

{% highlight css %}
:root {
    --background-color: #4ABDAC;
    --header-color: #FFFFFF;
    --text-color: #DFDCE3;
    --accent-color: #F7B733;
}

body {
    background: var(--background-color);
}

h1,h2,h3,h4 {
    color: var(--header-color);
    font-family: 'Open Sans';
}
{% endhighlight %}

Pretty simple, right? You define the variables in :root, which means they can be accessed throughout the entire document. Then, you call them when you need them with var(). Supes easy.

## Cascading and Inheritance

Just as CSS is subject to cascading and inheritance, so are its custom properties. Check it out!

{% highlight css %}
a {
    color: var(--acent-color);
}

a:hover,
a:focus {
    --accent-color: green;
}

@media (min-width: 600px) {
    a {
        --accent-color: midnightblue;
    }
}
{% endhighlight %}

.. And there you have it! By using the same custom property, we're able to have different values in different places on the same page. Neato!

## Conclusion

So that's my take on CSS variables and how I use them. I like the organizational aspect that comes with using them, and I know for a fact that there are a lot more use cases for them out there. Hoping to pick more of these up as I go, but it looks like I found a replacement for SCSS

Check out the accompanying repo I made to go with this blog post on [Github](https://github.com/aechagen/css-variables)