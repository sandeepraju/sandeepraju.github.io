---
title: "Reviewers' guide to effective code reviews"
layout: post
date: 2025-08-07 00:00
image: /assets/posts/2025-08-07-the-art-of-code-reviews/header.jpg
headerImage: false
tag:
- code
- swe
- dev
star: false
category: blog
author: sandeeprajup
description: My thoughts on approaching code reviews as a reviewer!
---

Over the years, I've been fortunate enough to review thousands of code changes across different teams and projects. While I'm far from having all the answers, this experience has taught me a few things about what makes code reviews effective and what makes them painful. I've seen reviews that left developers feeling inspired and ready to improve, and others that left them questioning their career choices. The difference often comes down to how we approach the review process.

So, here's what I've learned along the way: practical advice that I wish someone had shared with me when I first started reviewing code. Think of this as a collection of hard-earned wisdom, offered in the hope that it might help you avoid some of the mistakes I've made and create better review experiences for your team.

## The Foundation: General Guidelines

When you're reviewing someone's code, remember that you're not just looking for bugs or mistakes. You're also building a positive team culture. So, let's keep these general principles in mind:

* **Be a role model:** This one's pretty straightforward. If you expect a certain level of quality and professionalism in code reviews, you've got to lead by example. Practice what you preach, and others will follow.  
* **Be kind and courteous:** Imagine putting hours into a piece of code, only for someone to tear it down without a second thought. People get emotional about their creations, and that's totally understandable. A little kindness goes a long way in making the review process less daunting.  
* **Give the benefit of the doubt:** It's easy to jump to conclusions, but most of the time, folks have good intentions. If something in the code seems off, assume they had a good reason for it until you've had a chance to ask.  
* **Build relationships:** Code reviews are actually a fantastic way to connect with your teammates. You get to see how they think, and they get to see how you approach problems. It's a prime opportunity for some friendly collaboration.  
* **Know the power dynamic:** As a reviewer, you hold a certain amount of influence. Be aware of that and use it responsibly. Your words carry weight, especially for newer engineers.  
* **Focus on education:** Think of yourself as a mentor. Your main goal here isn't just to get the code merged, but to help the author learn and grow as an engineer. Every review is a teaching moment.  
* **Think from the reader's perspective:** When you're looking at code, try to put yourself in the shoes of someone who's seeing it for the first time. How easy is it to understand? Is it clear what's happening? This helps catch readability issues.  
* **Critique the code, not the author:** This is a big one. Always focus your feedback on the code itself, not the person who wrote it. Personal attacks or blaming are never okay and just create a toxic environment.  
* **Ask for clarification, don't assume:** If a piece of code or a design choice isn't clear to you, don't just guess or assume. Just ask! It's better to clear things up than to make a review based on a misunderstanding.  
* **Be mindful of diverse backgrounds:** We all come from different places and have different communication styles. Choose your words carefully to ensure your feedback is understood and well-received by everyone.  
* **Praise good work:** It's not all about finding things to fix. When you see something well-executed, a clever solution, or a lot of effort put in, call it out! Positive reinforcement is super motivating.

## Before You Dive In: Setting Yourself Up for Success

Before you even start leaving comments, here are a couple of things to consider:

* **Read things in passes:** Don't feel like you have to catch everything in one go. Sometimes, it's helpful to do a first pass just to get the overall gist of the changes. Maybe even read the test cases first to understand the intended usage and functionality. Then go back for a more detailed look.  
* **Automate what can be automated:** If a machine can check it, let it! Things like code formatting, linting, and basic style checks should ideally be handled by automated tools. This frees up human eyes for more complex, logical issues that only a human can spot.

## The Art of Feedback: Crafting Helpful Comments

Now that we've covered the general vibe, let's talk about how to actually write your feedback so it's helpful and constructive.

* **Make it actionable and concrete:** Avoid vague statements or theoretical discussions. Instead of saying "This code is bad," try to explain *why* it's bad and *how* it could be improved. Give specific, concrete suggestions with context. Providing a small code snippet of your suggested change makes it much easier for the author to implement.
* **Watch your tone:** Even the most well-intentioned feedback can sound harsh if the tone is off. Remember, written communication lacks body language and vocal inflections, so be extra careful with your wording. Try reading your comment aloud to see how it sounds.  
* **Categorize your comments:** It's helpful to give the author a heads-up about the nature of your comment. You can use categories like:  
  * **Appreciation:** "Hey, I really like how you tackled this edge case! Great job."  
  * **Question:** "I'm curious, what was the thought process behind using a `for` loop here instead of `forEach`?"  
  * **Should change (blocking):** "This needs to be fixed before merging, as it introduces a security vulnerability."  
  * **Suggestion (non-blocking, optional):** "You *could* consider using a helper function here for better readability, but it's not strictly necessary."  
  * **Nitpick (know when you're doing this!):** "Just a nit, but `userId` should probably be camelCase." (And make sure the author knows it's a nitpick, so they don't stress about it.)  
  * **Brainstorming:** "What if we tried an entirely different approach, like using a reactive stream here? Just thinking out loud."  
  * **Complaint to change process:** "This PR is huge, and it's hard to review. Can we talk about breaking down PRs in the future?"  
* **Over-explain, over-communicate:** When in doubt, provide more detail rather than less. Clarity is king in code reviews, and it helps prevent misunderstandings.  
* **Wrap criticism as an intelligent question:** This is a fantastic technique. Instead of dictating a solution, frame your feedback as a question that encourages the author to think critically about their code and come up with the answer themselves.  
  * **Instead of** _"You are writing cryptic code."_,  **try** _"It's hard for me to grasp what's going on in this code. Could you clarify the intention behind this section?"_  
  * **Instead of** _"This variable should have the name 'userId'."_, **try** _"What do you think about the name 'userId' for this variable? I found myself wondering what it represented."_
* **Use "we" verbiage:** Instead of saying "Can *you* do this?", try "Can *we* do this?" This fosters a sense of teamwork and shows that you're both on the same side, working towards the best solution.

## The Pitfalls: What to Avoid During Code Reviews

Just as important as knowing what to do is knowing what *not* to do.

* **Reviewing design during code review:** Ideally, major design decisions should be agreed upon *before* the code is even written. If you find yourself in a code review trying to fundamentally change the design, it might indicate that your team's design review process needs a tune-up. Code reviews are for implementation details and minor refinements, not complete overhauls.  
* **Approving code you're not okay with:** Never, ever approve code that you genuinely believe is flawed or introduces problems, just because the author is under a time crunch. Your approval signifies that you stand behind the code, and compromising on quality can lead to bigger headaches down the line.  
* **Bikeshedding:** This is a classic pitfall. Avoid getting bogged down in minor stylistic debates that can easily be handled by linters or agreed-upon coding standards. Arguing over whether a curly brace should be on the same line or the next is a waste of everyone's time.

## Team Dynamics: Different Roles in a Code Review

Sometimes, a code review isn't just one person doing everything. For larger projects or teams, different parts of the code might benefit from different expertise:

* **Style Checker:** This person (or tool!) focuses on ensuring the code adheres to the team's coding style guidelines.
* **Subject Matter Expert (SME):** If the code touches a specific area of the codebase, an SME can provide deep insights into its impact and best practices for that domain.  
* **Security Reviewer:** For sensitive systems, a security reviewer will specifically look for potential vulnerabilities and ensure security best practices are followed.  
* **Test Reviewer:** This person focuses on the tests. Are they comprehensive? Do they cover edge cases? Are they well-written and maintainable?

## Wrapping Up: The Ripple Effect of Great Reviews

Here's the beautiful thing about effective code reviews: they create a ripple effect that extends far beyond the immediate changes. When you approach reviews with empathy, clarity, and a genuine desire to help others grow, you're not just improving code. You're building a culture of continuous learning and mutual respect.

Every review is an opportunity to make someone's day a little better, to share knowledge that might help them in their next project, and to strengthen the bonds within your team. The skills you develop as a thoughtful reviewer will serve you well throughout your career, whether you're mentoring junior developers, collaborating with peers, or even writing code that others will review.

Remember, the goal isn't perfection. It's progress. Every developer, no matter how experienced, has room to grow. By creating an environment where feedback is welcomed rather than feared, you're helping build the kind of team where everyone feels empowered to take risks, learn from mistakes, and push the boundaries of what's possible.

So the next time you're about to review someone's code, take a moment to think about the impact you want to have. Will your feedback leave them feeling inspired and ready to tackle the next challenge? Will it help them see their code through fresh eyes? Will it contribute to a culture where everyone feels valued and supported?

That's the magic of great code reviews. They don't just make better code, they make better developers, better teams, and ultimately, better software. And that's something worth striving for.

Happy reviewing! ✨

<br/>


## Bonus: Bad vs. Good Code Review Comments

Here are some real-world examples I've encountered (both as an author and reviewer) of how to transform unhelpful code review comments into constructive feedback. I've seen firsthand how much of a difference the right phrasing can make:

1. **Bad:** "This code is a mess."  
   **Good:** "I'm having trouble following the logic flow here. Could we break this down into smaller functions with descriptive names to make it more maintainable?"

2. **Bad:** "Why would you do it this way?"  
   **Good:** "I'm curious about the approach here. Could you help me understand the reasoning behind using a recursive solution instead of an iterative one?"

3. **Bad:** "Use better variable names."  
   **Good:** "The variable name 'data' is a bit generic. Since this represents user preferences, what do you think about naming it 'userPreferences' to make the code more self-documenting?"

4. **Bad:** "This is inefficient."  
   **Good:** "I notice we're iterating through the array multiple times. We could potentially improve performance by using a Map to store the values, reducing the time complexity from O(n²) to O(n). Would you like to explore that approach?"

5. **Bad:** "Did you even test this?"  
   **Good:** "I noticed this might not handle the edge case where the input is null. Could we add a test case to verify the behavior in that scenario?"

6. **Bad:** "This doesn't follow our standards."  
   **Good:** "According to our team's coding guidelines (link), we typically use async/await instead of Promise chains. Would you mind updating this to maintain consistency with the rest of the codebase?"

7. **Bad:** "Copy-pasted code. Fix it."  
   **Good:** "I noticed similar logic in the UserService class. We could reduce duplication by extracting this into a shared utility function. What are your thoughts on that?"

8. **Bad:** "Wrong."  
   **Good:** "The current implementation might lead to a race condition when multiple users update the same record. Consider using a transaction or optimistic locking to handle concurrent updates safely."

9. **Bad:** "This needs comments."  
   **Good:** "This algorithm is quite complex. Adding a brief comment explaining the business logic would help future developers (including ourselves!) understand why we need this specific implementation."

10. **Bad:** "Just use pandas."  
    **Good:** "Instead of implementing this data grouping manually, we could use pandas' groupby() method here. Since we're already using pandas in the project, it would make the code more readable and efficient. For example, `df.groupby('category').mean()` instead of the current nested loops. What do you think?"


<br/>
<br/>

What do you think? Shoot me an <a href="mailto:me@sandeepraju.in">email</a> with your thoughts!