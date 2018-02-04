---
layout: post
category: [drafts, programming]
title: Object model
---

My story with OOP begins in childhood when I was struggling with my despair in
school. Long story short, I got my hands dirty with dotnet and I liked it at the
moment. By the end of school years I'd tried lots of things: from network
programming with sockets and games with XNA to UI with WPF to webdev with aspnet mvc.
I was messing around mostly and it was all rather childish.
But the thing is I got quite familiar with the environment and concepts and I
loved it. MSDN was my dogmata. Most importantly, I considered myself an adept of OOP.
**Now I reproach all of that** and here's why.

I will try and not rant on
 [Microsoft](https://www.gnu.org/proprietary/malware-microsoft.html)
 and [proprietary software](https://www.gnu.org/proprietary/proprietary.html).
Instead I'll focus on OOP.

I can see two basic approaches to the Object Model or rather two different
Object Models:
-   Structure on sets.
-   Interacting entities.

## Structure

The first approach is the Light Side of the Force. It is built around the idea
of endowing *Sets* with *Structure*, i.e. relations and functions. If a
mathematician would reffer to a *set* together with a *structure* on it as to a
*Space*, an OOP adept would call it a *Class* or a type of *Object*. Object here
is simply an element of a space. The process of grouping sets and structure
is known as *incapsulation*.

## Interacting entities

The second way is a way of the Dark Side. It's a model of *interacting
entities*. Here objects are mysterious *entities* that *act* with their
functions on their *states*. They can share behaviour with the use of
*inheritance*. I'm not mentioning the principles like polymorphism here as they
aren't really specific to this model.

I don't imply that local interactions is a bad idea: actually it's a great idea,
but you must take care of... convergence of some sort.
I say it's a dark path because it's easily followed uncounsciously. And when
it's followed so it leads to misinterpretations, to the cargo cult, and, above
all, to errors.

## Inheritance is useless

Inheritance is a means to implement polymorphic behaviour, no more.
In this context
[almost always](https://en.wikipedia.org/wiki/Almost_surely)
the Inheritance is overused and only makes a system more complex: it either
can be replaced with
[composition](https://en.wikipedia.org/wiki/Composition_over_inheritance)
or even stripped away.
The main problem though is that it's tempting to *use inheritance to describe
hierarchies*, although there's no practical use in it.
A classic example is that of a square and a rectangle: the first is a particular
case of the latter but the `setWidth()` of a Square should either violate what
we expect from a Rectangle or return a non-square.

Another use of inheritance is for Mixins. While it's an acceptable use it's
still an overuse. My belief is that one can replace it all with plain
datastructures.

## OOP as an instance of cargo cult
Or a way to avoid solving the problem.

The main grudge of mine against the OOP is that it introduces a lot of
unmotivated concepts which have been taken for granted by the mainstream and are
being applied to every single problem.
People started modeling *data* with interacting objects!
How do you start building a web service in some java or, say, django?
You describe *models* (which aren't actually models) using *classes* which
inherit from ORM-framework's base types (from `django.db.models` or
`javax.persistence`).
These quasi-models then need to be mapped into the relational ones.
This mapping causes some additional conceptual difficulties and also poorly
affect the performance. Some time later you'll have to fix the performance. How
are you going to achieve that? You'll write custom queries which will take into
account the relational nature of data. Moreover, sooner or later you'll find out
that a typical RDBMS's model is rather stripped and incomplete because of some
dogmata and myths associated with the relational model (I'll write on that later).
One can find much more points to this topic by googling "object-relational
impedance mismatch" or something.

Shall we dig a bit deeper we'll realize that not only there's a mismatch between
applications' data model and persistence-layer's model, but also a mismatch
betwixt application and the presentation layer. For what it is that frontend
expects from the application? A REST api for WEB or plain datastructures for a
standalone application that relies on data-bindings.
Not a "bunch of interacting entities" at all
