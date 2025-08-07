---
title: "Vibe engineering"
layout: post
date: 2025-08-06 00:00
image: /assets/posts/2025-08-06-vibe-engineering/header.jpg
headerImage: false
tag:
- ai
- coding
- skill
- swe
- dev
star: false
category: blog
author: sandeeprajup
description: Thoughts on vibe coding after four months!
---

Back in March 2025, I started dabbling with ["vibe coding"](/blog/vibe-coding/). Over the last four months, this led me down a journey of re-learning how I code with AI and developing a workflow that I now affectionately call "Vibe Engineering™". It's been a thoroughly enjoyable process, and I've picked up a few invaluable lessons along the way - lessons I thought were worth sharing, not just for you, but as a personal best practice guide for myself. Think of it as my evolving playbook for working smarter, not harder, with AI.

As I started jotting these down, it hit me: so many of the timeless principles from traditional software engineering are just as crucial, if not more so, when you're "vibe coding". It's not just about whipping up some quick code; it's about engineering it. We're aiming for quality and productivity, not just speed. So, let's talk about how to make AI-assisted coding feel less like a free-for-all and more like proper "vibe engineering".

<br/>
![Trust me, I'm an engineer][1]{: class="center-image" }
<br/>

Here's the scoop on what I've learned:

First off, AI can be a game-changer when used correctly. Suddenly, those features you always dreamed of but kept pushing aside due to capacity issues? They're within reach. It's thrilling! You start envisioning grander things, features you never thought possible. But here's the catch: it's incredibly easy to get swept up in the flow, letting the AI conjure up new features or bespoke serialization formats or design patterns. Without guardrails, a simple Minimum Viable Product (MVP) can balloon into a full-blown application, loaded with bells and whistles nobody actually needs. If you don't ruthlessly focus on what you need, very soon you'll be spending days squashing bugs in a feature that exists purely because the AI thought it'd be "cool" to implement (and trust me, I'm speaking from experience). Remember, every new line of code is a liability. Keep AI on a tight leash, and tell it to ruthlessly reuse, refactor, and focus on just what you asked for.

And speaking of AI's tendencies, remember this: AI is a "yes man". It'll feed your ego and let you run wild if you're not careful. Every idea you toss its way will be hailed as genius. So, be mindful of what you ask it to do. Actively encourage it to challenge your assumptions. Don't let your AI assistant amplify your blind spots. What looks like a small detour can quickly become a full-blown rabbit hole. This is where AI truly shines for senior engineers, making them even more productive, but can utterly bewilder and give false confidence to junior folks.

<br/>
![Yes sir][2]{: class="center-image" }
<br/>

Next, when crafting your prompts, don't go overboard with the details. Give the AI some breathing room for creativity. Let it figure out the code layout, class names, function names, and other nitty-gritty bits. You should definitely catch any glaring red flags, but don't obsess over every little detail unless it's absolutely necessary. Some exceptions: You're building a UI that needs to be pixel-perfect to the spec. In those cases, specialized tools are your best bet - think Figma-to-code converters, for example. Often, a simple screenshot of what you need can work wonders.

Always, always, always start with tests if you can, and build strong test guardrails. AI can go off the rails quite often, and a failing test case is a fantastic way to show it exactly where it went wrong. Be vigilant, and commit your changes frequently. Think of AI like a mad lumberjack with a chainsaw. You can get a lot done, but you never know when that lumberjack is going to go, well, mad. I’ve seen it hallucinate entire libraries, delete files, even remove tests to make the existing code look correct. It can re-implement a whole library from scratch because of a slight misunderstanding in a prompt! Seriously, always have a backup of your code and be very vigilant with what it generates.

Next up, task sizing. This is where a bit of planning really pays off. How are you going to break down your entire project into phases, and then each phase into manageable tasks? And how can you ensure these tasks are just the right size for the AI to tackle as a cohesive unit? It's super tempting to just dive in and start coding, but resist! Work with the AI to generate a plan. It's surprisingly good at it. It might seem like a lot of work upfront but makes it easier to build something iteratively and course-correct early on if needed.

<br/>
![Have a plan][3]{: class="center-image" }
<br/>

A solid dev workflow is a big part of implementing these small chunks of tasks effectively. For instance, I've adopted "rules" that the AI must follow before marking a task as complete: Before implementing anything, the rule asks the AI to clarify the requirements, think about edge cases or ambiguities, and then show me its understanding before I give the green light. Once the code's done, I want the AI to make sure there are tests, that they pass, that documentation is updated, existing tests are adjusted if needed, and that everything is linted. This creates a structured, self-evaluating loop. You can also define project best practices as "rules": Writing modular functions, focusing on reusability, a maximum line count for functions, creating methods for any code repeated more than twice, and so on. Many Agentic IDEs (such as [Cursor](https://cursor.com/en) or [Cline](https://cline.bot/)) have the concept of [rules](https://docs.cursor.com/en/context/rules) baked in. They really help you get more predictable code and iterate faster over time. Your repertoire of rules can be reused across projects and will eventually become your "dev style" when coding with AI.

Let's talk about context memory: It is a precious commodity (both from an accuracy and 💵💵 standpoint), so make it a habit to compact your context every now and then. Concepts like [Cline's memory bank](https://docs.cline.bot/prompting/cline-memory-bank) are fantastic for this. They ensure that after each task, you dump the important bits into a "memory bank" so that when you clear your context, you can load up that "compacted context". This way, you won't hit your context limit and can keep making progress. On top of that, explicitly attaching only the necessary files will help the AI be much more accurate and targeted in its changes.

Finally, AI generates a ton of code. If you ever dreaded reading other people's code, well, now you'll have to deal with AI's code too. Reading every single line it generates will slow you down, but blindly trusting it (YOLO mode) is definitely not advised. The sweet spot is to have some checkpoints—before you commit a feature or task (basically, some logical boundary) where you dedicate time to just reading the code and suggesting improvements. As the AI applies these improvements, turn them into concrete rules that AI must follow from then on. Over time, you'll slowly start seeing a more predictable, higher quality of code.

<br/>
![Cat code review][4]{: class="center-image" }
<br/>

So, there you have it. From the initial thrill of "vibe coding" to the disciplined approach of "vibe engineering," these lessons have been instrumental in my journey with AI-assisted coding. It's all about harnessing the power of AI while keeping those time-tested engineering principles front and center. It's a continuous learning process, but with a bit of mindfulness and a good workflow, you can truly leverage AI to build incredible things.

Happy vibe engineering! ✌️

<br/>
<br/>

What do you think? Shoot me an <a href="mailto:me@sandeepraju.in">email</a> with your thoughts!


[1]: /assets/posts/2025-08-06-vibe-engineering/engineer.gif
[2]: /assets/posts/2025-08-06-vibe-engineering/yes.gif
[3]: /assets/posts/2025-08-06-vibe-engineering/plan.gif
[4]: /assets/posts/2025-08-06-vibe-engineering/cat.gif
