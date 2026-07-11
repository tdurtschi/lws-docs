# AI Agents on a Software Team: Client Engagement Report

## Introduction

My experience using agentic AI tools (specifically Claude Code and Amp) on a development team - 3 month update.

A bit about the team:

- Domain experts
- Pair programming by default
- Strict adherence to TDD
- Aggressive refactorers
- Complex Client/Server application

Our team has been learning how to best utilize these AI tools.

## Agent as a pair

- User as navigator / Agent as driver
    - 'Ground Control to Major Tom' - our space themed nickname
- Deep planning sessions
- Lots of reading/writing, spending more time in the CLI than IDE

I wanted to see what the tools were capable of, so at first I tried to use agents as the main interface to building features. This usually works with some gentle guidance and vigilance. 

## Using the agent less

Writing code is fun! Refactoring is fun! Reading plans & reviewing PRs is not as fun.

I invoke the agent to do various tasks: 

- answer questions 
- repeat a pattern 
- do research

I use the IDE to:

- get basic context on the code
- refactor

## Agent context

- Agent gets its own repo. 
    - Allows team members to opt-in to hooks, skills, etc without committing to code repos.
    - Works across many repositories

- Shared skills
    - DevOps and debugging
    - Test Driven Development workflow

- Readmes - human readable docs are also helpful for models. 
    - Thought: Why shouldn't CLAUDE.md files just be a hyperlink to README.md?

## TDD

- More powerful models follow TDD workflow better
- Putting TDD principles in the prompt somewhere helps
    - Always write a red test before implementing a new behavior
    - Only add enough code to pass the test
        - AI loves to write overly defensive code
    - Verify the test fails on specific assertions 
        - LLMs love to write a test that doesn't compile and claim 'that's it! red step complete'
        - Claude dubbed these compilation failures "Infrastructure red"
    - Updating a test may be more appropriate than writing a new one

## Lessons Learned

- Talk about AI. Share your prompts & techniques.
- Agents are similar to human coworkers. You need to give them context on what they're doing. Every session is the first time the agent has ever seen your code. Sharing context is as important as ever.
- Agent can help you be lazier or more actively involved. It's up to you.

## Conclusion

AI has changed how our team works. Most of us use AI every day. We still value pairing with each other. We have a lot of fun!