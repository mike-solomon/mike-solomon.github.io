---
layout: post
title: "Analyzing the WaniKani API Docs"
date: 2022-07-25 12:48:32
tags: [Technical Writing, WaniKani]
categories: [Technical Writing, WaniKani]
---

As part of my technical writing certification course, we were tasked with analyzing some online
document. We were provided with a series of key questions to answer in order to evaluate how
effective the document was. I chose to analyze the WaniKani API docs, and you can read my analysis
of them below.

> You can find the API docs for yourself here: [https://docs.api.wanikani.com/20170710/](https://docs.api.wanikani.com/20170710/)

# Audience

## Who will be reading the API docs?

The API docs are written for developers interested in utilizing the WaniKani APIs. This means they
are not written for people who are unfamiliar with WaniKani, nor are they written for people who
don’t have experience with software development.

## What do they know about the subject area?

The people utilizing these docs more than likely:

- Know how to work with APIs
- Are familiar with HTTP requests
- Understand what HTTP status codes mean
- Use WaniKani themselves

That being said, these people more than likely _don’t_ know:

- How to authenticate against the WaniKani endpoints
- How to make WaniKani-specific API calls
- What the responses to said API calls look like
- What errors are expected

# Purpose

## What do the API docs need to accomplish?

The main purpose of this kind of documentation is to educate developers so that they can make
specific API calls. The goal behind these API calls varies from developer to developer, but the
core idea is that they want to interact with WaniKani in some way. This could be requesting
information that they will then use or it could be providing WaniKani with information to change
the experience for specific users.

## Is persuasion needed to change the reader's attitude?

No. API docs are not designed to persuade people in any way. Rather, they are strictly there for
educational / lookup purposes.

## Do the readers need to be instructed on how to perform a specific task?

Yes. There are a plethora of tasks a developer might need instructions on. To list a few of the
most important ones:

- How to authenticate requests
- How to parse the responses
- How to deal with large numbers of responses (pagination)
- How to filter endpoints to get specific pieces of information
- How rate limits are dealt with

# Context

## Where and how will the audience be reading the docs? What is their environment?

People reading this document will more than likely be indoors in front of a large monitor or
laptop screen. It is _possible_ that they could read the docs on their phone or tablet, though.
Furthermore, they will be connected to the internet which implies that the reader will have the
ability to click on links to gain further assistance if needed.

# Visual Language

## What are the font types and sizes that are used?

There are many different fonts used throughout the doc. For instance, headers and text have a
different font than code. It’s a bit tricky to narrow down which font belongs to which piece due to
the way the CSS is written, but I’ve seen these fonts used throughout the doc:

- Segoe UI
- Roboto
- Helvetica
- Arial
- Consola
- Menlo
- Monaco
- Lucida

Font size also varies wildly depending on the pieces. Headers appear to be 28px in size whereas
code can be as tiny as 12px.

## How is the document structured?

The document is broken up into logical chunks; starting with an introduction and basic API
information and moving towards specific API resources. Each chunk has very specific examples and
information and is designed to be read through linearly.

## Are icons, graphics, charts, tables, or graphs used to communicate data?

For the most part, the document is strictly text-based. That being said, many sections use simple
tables to present specifics for each request. The code section on the side of the doc doesn’t use
any of these things, but it is presented in a way that visually looks like code. It is also
structured in a way that allows people to easily copy / paste the code into another window.

## What is the size of the document?

The document is significant in size. As it’s a web page, it’s difficult to determine a page length,
but copying and pasting it into Word suggests it’s around 65 pages in length.

# Document Effectiveness

## Arrangement

These API docs are beautifully spread out across three areas:

1. A navigation side-bar that is concise while providing easily searchable chunks.
2. A main content area that provides the core text and explanations for how to use their APIs.
3. A code area that is equal in size to the main content area but which provides easily copyable code (in either shell or JavaScript) for developers to work with.

In both the navigation side-bar and the main content area, a hierarchy is created with different
levels of headers to break the document up into clean sections.

## Emphasis

API docs consist of an incredible amount of information that the reader is looking for. While these
docs are typically written such that there’s no extraneous text, there are three key pieces that
benefit from having further emphasis:

1. Headers so that the reader can easily find which sections they’re looking for.
2. Request / Response parameters so experienced readers can look directly at those pieces and ignore the explanations needed for others.
3. Different pieces of code so that readers can easily parse what the code is saying. Having code that is all the same color is significantly harder to comprehend than code that highlights key words or pieces.

## Clarity

As discussed in the arrangement section, the document is broken up into clear and easily readable
sections. Furthermore, as mentioned in the emphasis section, headers, pieces of code, and key
attributes are all distinct while being easily understood and not difficult to look at. There is
no area in this document that is difficult to read.

## Conciseness

Despite being a substantially sized document, each section is concise and to the point. There are
no fluff words or sentences interjected that brag about things like speed or design. Rather, it
strictly shows the reader how to make specific API calls, and it links out to other pages if the
reader deems they need more information. No paragraph is longer than a few sentences.

## Tone

The tone of this document is welcoming and friendly. It speaks to the reader directly via words
like “you,” while not going as far as using slang or making jokes. There are no areas with
unreasonably bolded text or capitalization that screams at the reader. Colors are only used to
denote links or differentiate code as a developer would expect.

## Ethos

The layout of the WaniKani docs is better than most API docs I’ve seen. By providing all of the
information needed in one page, it makes it significantly easier for readers to find what they’re
looking for. Furthermore, all of the attributes and values for each resource are listed and
explained. In contrast, many other API docs I’ve seen either just list the attributes without
any explanation or leave out significant chunks of them. The fact that there’s simple and easily
copyable code further inspires confidence and trust.

# Conclusions

Overall, I found the WaniKani API docs to be extremely effective in their goals. More companies
should strive to create API docs that rival theirs – especially in regards to clarity and ethos.
