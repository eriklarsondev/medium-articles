---
title: "Congratulations, AI Just Made Your Mess Even Bigger"
createdAt: 2026-11-04
---

There's no denying that AI has changed the way we write software. What used to take hours can sometimes be accomplished in minutes. Entire features, API endpoints, components, tests, and even application scaffolding can be generated with a few well-written prompts.

I've been using AI-assisted coding for years, and I genuinely believe it's one of the most significant developments in software engineering in my career. I use it every day. I encourage its use. I lead a team of engineers where AI is now the primary means of generating code.

But working this way has made one thing increasingly apparent: we're getting very good at generating code, but we're not always thinking about what happens after it's generated.

There's a fundamental difference between writing code and building maintainable software. I think that distinction is getting lost in the excitement surrounding AI-assisted development.

One of the most obvious examples is the size of pull requests. It's not uncommon to see AI-generated PRs containing hundreds or even thousands of lines of changes. Sometimes that work could have been broken into several smaller, more focused pull requests. Instead, an entire implementation gets generated, submitted, and treated as one deliverable.

The problem isn't necessarily that the code is bad. It's that someone still has to review it.

AI can generate thousands of lines of code in minutes. A human engineer still has to understand what those changes do, whether they're correct, how they interact with existing functionality, and what potential consequences they introduce. That doesn't happen at the same speed. Implementation might be faster, but comprehension hasn't magically become instantaneous.

And if we're being honest, how thoroughly can someone review a 2,000-line pull request when they're also responsible for their own work, meetings, deadlines, and everything else that comes with being an engineer?

This is where the process starts to break down. Large changes become harder to reason about, reviews become less effective, and it's tempting to rely on the fact that the tests pass or another AI tool says the implementation looks good. Neither is a substitute for actually understanding what we're shipping.

The same problem shows up at the file level.

Personally, I try to keep most of my files somewhere around 150 lines. That's not a hard rule, and there are certainly legitimate reasons for files to exceed that. But I prefer smaller, focused modules with clear responsibilities over massive files that try to do everything.

AI doesn't seem to have the same preference.

It's remarkably easy for an AI-generated implementation to turn into a file containing 1,000, 2,000, or even 5,000 lines of code. Entire components, business logic, data handling, and utility functions end up living together in a single file. Technically, everything might work, but actually working with something like that is a nightmare.

Anyone who's had to sift through a 3,000-line file just to find where a particular piece of functionality lives knows exactly what I'm talking about. You're jumping between functions, tracing dependencies, and trying to understand how everything fits together. Instead of spending your time engineering a solution, you're spending it navigating a wall of code.

This isn't just about aesthetics or personal preferences. Code organization directly affects how easily a team can understand, debug, extend, and maintain an application. Separation of concerns and modularity exist for practical reasons. They reduce the amount of information an engineer has to keep in their head just to make a change.

When an AI agent generates a massive file, it doesn't necessarily care whether another developer will have a difficult time navigating it six months from now. It cares about satisfying the immediate implementation request.

There's an irony here. We're using AI to accelerate software development, but we're also creating codebases where we increasingly need AI just to understand, navigate, and maintain what we've built.

And this goes beyond file sizes and pull requests. The bigger concern is how easily AI can accelerate the accumulation of technical debt.

Technical debt isn't new. We've been creating it for decades. Rushed implementations, duplicated logic, unnecessary abstractions, inconsistent patterns, and architectural shortcuts have always been part of software development. AI hasn't invented any of these problems. What it has done is dramatically reduce the friction involved in creating them.

When generating code becomes almost effortless, it's tempting to keep adding more. Need another abstraction? Generate one. Need another utility? Generate one. Need to support a new workflow? Have the AI implement it. Before long, you can end up with multiple approaches to solving the same problem, business logic duplicated across the application, inconsistent data models, and dependencies that nobody can quite explain.

Individually, these decisions might seem harmless. Collectively, they make a codebase increasingly difficult to understand and maintain. And because the code was generated so quickly, it's easy to underestimate the amount of work required to support it later.

This is the part I think engineering teams need to take seriously: **code is not free just because AI can generate it for free.**

Every additional line of code is another potential maintenance obligation. It needs to be understood, tested, reviewed, documented where appropriate, and eventually changed or removed. Code that doesn't provide enough value to justify that ongoing responsibility is a liability, not an accomplishment.

Imagine inheriting an application after six months of unchecked AI-assisted development. You find multiple implementations of authentication, three different approaches to handling API errors, duplicated business logic, and abstractions that seem to exist for no particular reason. Nobody intentionally designed the application that way. It just happened, one successful AI-generated implementation at a time.

Eventually, somebody has to pay that bill. And that somebody is usually an engineer who has to untangle the mess, figure out what can safely be changed, and determine which parts of the application are actually trustworthy.

So what's the answer? It's certainly not to stop using AI. I think that would be a mistake. But we need to be more intentional about how we're using it.

Engineers need to stop treating generated code as disposable output and start treating it as production code from the moment it enters the codebase. That means giving AI smaller, well-defined tasks instead of asking it to implement entire features in one shot. It means breaking work into incremental changes, keeping pull requests focused, and reviewing generated code with the same scrutiny we'd apply to code written by another engineer.

It also means being deliberate about architecture. Don't let an AI agent decide that every problem needs another abstraction or another dependency. Establish patterns, define boundaries, and make sure generated implementations follow the conventions of the existing application. Ask it to explain its approach. Challenge unnecessary complexity. Refactor oversized files. Remove code that doesn't need to exist.

Most importantly, engineers need to remain involved in the decisions. AI can suggest an implementation, but someone needs to understand why that implementation belongs in the application and what its long-term consequences might be.

We need to remember what productivity actually means. Generating more code isn't necessarily being more productive. Shipping a feature faster doesn't mean we've saved time if we've introduced complexity that takes weeks to unwind. And a team that produces twice as much code isn't necessarily delivering twice as much value.

AI is an incredibly powerful tool. Used thoughtfully, it can make engineers more effective and give teams the ability to accomplish things that would have been much more difficult just a few years ago. But the goal should be to build better software, not simply to generate more of it.

Because the novelty of generating thousands of lines of code in minutes eventually wears off. The maintenance work doesn't.

Congratulations. AI just made your mess even bigger.
