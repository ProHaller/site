+++
title = "Why Rust?"
date = "2025-09-19"
in_search_index = true
description="Why I chose Rust as my first programming language and why it is a better choice than you might think."

[taxonomies]
tags = ["me", "rust", "learning"]
[extra]
og_image="/img/why-rust/crab-sword.jpg"
+++

![](/img/why-rust/crab-sword.jpg "A crab war-chief holding a giant sword above itself")

**TLDR:** Choosing rust was the result of an intentional choice that I do not regret. It is a harsh but excellent tutor that has provided me with much better foundations than I would have otherwise.

<!-- more -->

# What is the best programming language to start?

This has to be one of the most asked questions by aspiring software engineers.
There are both good and not-so-good reasons for that.
This is a choice that by definition beginners are not equipped to make.
There are a lot of different reasons for choosing a language over another.
Am I looking for the easiest to learn, the most in demand, the most pertinent for a specific domain of interest, etc.

## Do you want depth or simplicity?

It sure didn't take me a lot of time to find these pieces of advice online.
To make a long story short, the general consensus goes into one of two ways:

On the one hand, C is as low-level a programming language as you can reasonably go in this millennium.
With C you will learn all about how a computer works and build solid foundations.
C is used everywhere on everything. It has been so for more than 50 years.
Starting with C (and arguably C++) is the path favored by formal computer science curriculums and universities throughout the world.
C and C++ are the OG and there are a lot of [excellent resources](https://github.com/iczelia/C-Learning-Resources "Resources to learn C") to learn programming with them.

On the other hand, you have the high-level team.
Python's syntax _reads like English_, and JavaScript is the _de facto web standard_.
Either would teach you the building blocks of programming that you'll use everywhere afterwards.
Whether you want it or not you will not be able to avoid them.
Most self-taught software engineers start with one or the other.
There also is an abundance of resources to learn both [Python](https://wiki.python.org/moin/BeginnersGuide/Programmers "Resources to learn Python") and [JavaScript](https://www.learn-js.org/ "Resources to learn JavaScript") as well, books, courses, games, apps, bootcamp, the list is endless.

![](/img/why-rust/pills.png "Hands presenting a Red and a Blue pill, with C, C++, and Python and JavaScript logos respectively")

## But it's not so simple though is it?

I know some will be mad at me for lumping them together, but C and C++ barriers to entry are really high.
They both come with very messy ecosystems, compilers, standards, variations and flavors making starting with them a daunting task.
C++ also suffers from its history of incremental, sometimes contradicting _improvements_ and the richness of its ecosystem, inducing choice paralysis.

Python is simple, but maybe too much so, hiding complexity under intuitive syntax.
Until the amazing [uv](https://docs.astral.sh/uv/ "uv documentation") Python's package and environment management was unreliable and full of friction.
And Python is slow.
Its wide adoption and ubiquity in machine learning and artificial intelligence did tempt me a little, to be honest, but ultimately, it wasn't what I was looking for.

As for JavaScript, there is a lot to say, some good, most not so much.
I have a lot of respect for the work that has been done to expand its scope beyond what it was originally intended for.
But, it appeared to me as an incoherent, overused language that is something that we will all **have** to learn at some point, but not one I would really want to spend my limited free time on learning.

To be honest, that last argument is probably the one that had the most impact on my choice of a first language.
Learning programming is something I **wanted** to do. And none of the above felt exciting enough to provide me with the motivation needed.

![](/img/ferris/ferris.gif "Animated Ferris gif Original by Refracted Color")

## So, Why Rust?

It is the most admired language in the stack-overflow developer survey, and has been for nearly a decade, for good reasons.
Rust has been [designed from the ground up](https://youtu.be/k_-6KI3m31M?si=_aI_yIPFNzM1y5k_&t=1215 "How Rust Won by Raph Levien") to take advantage, combine and build on 50+ years of computer Science research.
Rust has stellar performance, state-of-the-art unified tooling and package management.
It is progressively taking over the world of _low-level programming_ from embedded systems to systems programming, to tools in a wide variety of fields.
As of the time of writing this, it is not yet the first choice for front-end development, and it might never be for various reasons, but it sure _can_ do it.
Rust is all around such a well designed piece of software that it is genuinely difficult to find negative things to say about its engineering.

Rust checks all the features I was looking for my first language:

- It is **fast**
- It is both capable of low-level and high-level programming
- It is built on the lessons of the past
- It has **excellent ecosystem and tooling**
- It has a wide and **growing adoption**
- It will teach you **no bad habits**
- It is [exciting](https://youtube.com/playlist?list=PLZaoyhMXgBzoM9bfb5pyUOT3zjnaDdSEP&si=zo3MONviW91e9HX5 "No Boilerplate Playlist on Rust") to me and others ([Not a cult](/img/why-rust/rust-cult.webp))

So the only caveat to choosing Rust is its reputation for being difficult to learn.
That however has not been such an issue for me, and maybe it won't for you either.
I think that difficulty rarely is the issue, more often it is that this difficulty expresses itself through lack of clarity, and needless complexity.
Learning to talk, walk, count, interact socially, is hard.
Soccer, gymnastics, dance, drawing, is hard.
Writing, reading, using a computer is hard.
We can do hard things.

> Doing hard things is not easy, but it's worth it.
>
> ~ Mia Love

So the question changes from **"Is it hard?"** to a much more interesting one: "Why choose **this specific hard?**".

Software engineering is complex. No two ways about it.

I do mean complex, not complicated.

![](/img/why-rust/complex-complicated.png "A drawing of a maze labeled complex and a tangle labeled complicated")

As a beginner facing this new world of complexity, it can be very daunting.
There are a myriad of things one has to know and understand to write code, let alone good code.
This complexity, however, is inherent to how computer works and how we interact with them.
It can be, and already is for the most part, hidden away under levels after levels of abstractions.
For a beginner looking to understand and master as much as I can of our technological system, being aware of the underlying abstraction is important.
Rust does an excellent job of finding that balance.

It does not hide completely that inherent software complexity.
But unlike C that drops you in this new jungle with a pointy stick for sole tool, \
Rust wraps this reality in a vast collection of excellent tools, documentation, compiler messages and libraries.
Rust also provides safety rules, that it also enforces mercilessly, forcing you to comply or at the very least acknowledge you are not.
At times it is difficult, infuriating even, like a strict master in your favorite anime, forcing the protagonist to _try again_.
Unlike C and C++, Rust borrow checker will not let you do what you want, if what you want shouldn't be done.
Nor will it hold your hand, and pretend everything is easy like Python and JavaScript would like you to believe.
No, Rust will have you learn, Rust will have you understand, Rust will have you verify, and remind you when your not up to snuff.

> The truth will set you free, but first it will make you miserable.
>
> ~ James A. Garfield

## So, was Rust a good choice?

![](/img/why-rust/crab-riding.jpg "An armored knight riding a giant crab to battle")

### Yes

More than a year after starting my programming journey with Rust, I do not regret it at all.

- I have learned a lot through Rust and I do not see even the beginning of a limit to the language from my skill-point.
- I have built [Sharad](https://github.com/ProHaller/sharad_ratatui "Sharad game repository"), an awesome little Terminal Game with the excellent [Ratatui library](https://ratatui.rs/ "Ratatui.rs website").
- My passion for programming has only increased with time and expertise, extending to development in general, and recently algorithms.
- I have found that I compare rather well to most of my peers both in breadth and depth of knowledge.
- I have found a very supportive and inspiring community of mentors [online](https://orhun.dev "Orhun Parmaksız") and [in real life](https://umami.orhun.dev "Tokyo Rust Meetup").

### But

It hasn't been only sunshine and rainbows:

- Learning programming on my own has been lonely at times, especially before I found the courage to connect with the Rust online community.
  The vast majority of the Rust community is composed of seasoned engineers, often with very high expertise both in Rust and a variety of other languages.
  This is not to say that they are gate-keeping in any way.
  On the contrary most of them were very nice and welcoming.
  But it can be intimidating to be still learning to walk among marathoners.
- There are a comparatively very small number of Rust resources targeted to real beginners.
  To be fair, the Rust team and community values deeply learning resources, and has taken many steps to ensure documentation is abundant, easily accessible and homogeneous.
  Unfortunately, so far, complete beginners are probably too small a minority of users to warrant prioritizing.
  I do admire the thought and efforts put into [Will Crichton](https://www.youtube.com/watch?v=R0dP-QR5wQo "Rust for Everyone on Jane Street") work with Rust for everyone and the efforts of [CharcoalFrostMetallic](https://github.com/charcoalfrostmetallic/ "Rust Starter Book author") to write a primer to the excellent [Rust Book](https://rust-book.cs.brown.edu/ "The Rust Book").
  A project to which I try to contribute directly, with the author..

- Rust jobs are still somewhat few and far between, most of which looking for young genius senior engineers with 30 years of experience.

- Although I became quickly proficient in the terminal and for coding logic in general, my Rust experience has offered little opportunity for front-end work.
  Beyond design, I think the community distribution is a little skewed towards back-end and system design.
  I'll need to swallow the blue pill at some point in the near future to complement my [zola](https://www.getzola.org/ "Zola Website") and [Dioxus](https://dioxuslabs.com/ "Dioxus Website") experience.
- Finally, starting my programming journey with Rust may have ruined most others for me.
  I will branch out eventually but you know what they say about first loves, they are often empty infatuation born out of lust and a lack of experience... Wait, what‽ 🫢

##### I hope it was as interesting to read as it was to write
