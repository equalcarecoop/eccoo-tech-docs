---
description: >-
  This page outlines the key design patterns that we will use when building the
  code
---

# design patterns

We will inform our development with a series of principles and policies that help make sensible design decisions. In may cases, this means adopting a well known or documented pattern. This is associated with our first \(and fundamendal\) design principle: _We don't believe that "Not Invented Here" is a good justification for not adopting things that someone else has designed_. 

## Frontend

### Form handling will use the Post/Redirect/Get pattern

We are using server-side rendering \(rather than a rich browser client\), which means there is a risk of form handling inadvertently submitting data twice. To avoid this, we will use the well defined Post/Redirect/Get pattern.

Further reading:

* [https://en.wikipedia.org/wiki/Post/Redirect/Get](https://en.wikipedia.org/wiki/Post/Redirect/Get)
* [https://www.geeksforgeeks.org/post-redirect-get-prg-design-pattern/](https://www.geeksforgeeks.org/post-redirect-get-prg-design-pattern/)
* [https://www.theserverside.com/news/1365146/Redirect-After-Post](https://www.theserverside.com/news/1365146/Redirect-After-Post)

### Keep the UI lightweight

{% hint style="danger" %}
DRAFT!
{% endhint %}

Minimise use of Javascript, particularly for animation. It makes things potentially less accessible.

