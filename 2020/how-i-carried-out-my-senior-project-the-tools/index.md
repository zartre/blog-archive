---
title: "How I Carried Out My Senior Project: the Tools"
date: 2020-02-29
categories:
  - "Life"
tags:
  - "productivity"
coverImage: "./images/1_uYCmwdzSO6ktWl3S1Ayy1g.webp"
public: true
---

As of writing this blog post, I was half way into finishing my senior project in Information Technology, so I wished to share the tools I had been using to carry out my senior project should some of you might want to seek for interesting finds 😉

# My project in brief

I am studying Information Technology so my senior project is in the form of software development. The project is an event check-in platform that uses Bluetooth beacons to accelerate the check-in process. In an overview, the project consists of three major parts: an API server where main business logic happens, a management website, and a mobile application for event attendees.

Apart from the software deliverable, there are also some paperwork and artifacts to work on.

# Backups

First things first, let’s talk about backups. Senior project is, for me, considered very crucial to my life as it plays an important role in my graduation. Everything must be safely stored and backup plans had to be sought. In case something went wrong I would still have all my stuff ready ’til the apocalypse.

I have been using these cloud storage services to keep backups of my work:

![](./images/1_9mxE2AXzeNmwB4Xc6Y_kZw.webp)

- SharePoint (OneDrive): the main hub to store and share documents, artefacts, research papers, designs and everything else.
- Google Drive: a mirrored backup of those in SharePoint (automatically synced by GoodSync).
- Backblaze: a whole PC backup.
- GitLab: not a backup but I store my source code and LaTeX files here.

# Research and paperwork

As I have told you that I consider my senior project to be very crucial, my thesis should be stored in an open standard, not proprietary ones such as Word (or Pages…) that could go corrupted somehow.

I chose LaTeX as the way to go because it is simply a plain text file. With this, I could be more assured that those proprietary software would not mess up with my work and make it unreadable, and that I would be able to see or recover my texts just by opening it with any software.

For less important documents like purchase forms, project update forms, I simply used Word because you don’t need to do it the hard way all the time.

Citations are very important to any thesis. I used Zotero to keep track of my information sources and used BetterBibTeX plugin to export them into BibTeX bibliography file to use with LaTeX.

# Designs and diagrams

I used Figma to design user interfaces for the website and the mobile application. Figma has a number of productive features, such as easy re-arrangement of group items, layout constraints, flexible components, prototype animations, and more. I could quickly create a prototype to present to my advisor.

Figma works in web browsers so it works on both Mac and Windows (Linux things too). You can also download their desktop app for convenience.

Figma is free but as a student you can grab the Pro plan for free which allows you to add an unlimited number of editors and supports unlimited version history.

UI designs were not the only graphics I had to do. Lucidchart was where I designed figures like Use Case Diagrams and Activity Diagrams.

Lucidchart is free and also offers students free Team plan which grants you unlimited documents, revision history and GSuite integration.

# Planning and task management

All the great tools would not matter anything if the project is not well planned. I used ClickUp to lay out tasks my colleague and I had to do in the project.

<figure>

![](./images/1_G5X54R0JMvfj5BDE2zhicA.webp)
<figcaption>
ClickUp
</figcaption>
</figure>

In ClickUp, you can organise your team into spaces and project into folders. You can also section your tasks as lists, and any task can have its subtasks too. With priority flags, I could focus on the tasks that are more important at a time. And with custom fields, I could set my own parameters for whatever I want to note to my tasks, like confidence levels.

ClickUp has loads of features that I found very useful (and I was surprised they greeted me with new features every week!). For example, multiple assignees, task tags, task relationship, estimated time, app integrations and more. You will definitely want to check it out.

For personal daily tasks, I used TickTick to help plan my day. The UI is very easy to use and plan. My tasks sync across my desktop, laptop, phone and tablet so I can view them anywhere. It also has a pomodoro timer to help you focus on a task.

A good old notebook-and-pen was a trusty companion when I had to write down my thoughts, diagrams, and order my algorithms. It is a simple canvas that is always ready to draw.

# Documentation and knowledge base

To have a unified understanding of the project, we shared the project’s outline in Notion. It included: what we were making; why we were making it; and how we would make it.

Notion is very flexible about the content in a note. You can add files, code, media embed, etc. to the note. With this flexibility, database schemas and API specifications were also shared in Notion. I could filter data in a table by fields, or add a relationship between data. It is so powerful I could not utilise it all.

# The code

This part might be a little technical but I will try to write it as simple as I can.

I chose GitLab to store my source code because it is easy to gather related ‘projects’ (repo) into a single group, and all projects in the group can share the same namespace (`[https://gitlab.com/group-name/repo-name](https://gitlab.com/group-name/repo-name)`) which makes it look organised.

<figure>

![](./images/1_vgcwApaExdZnSAUT5saSqw.webp)
<figcaption>
GitLab group
</figcaption>
</figure>

GitLab also has a container registry built right in, so the project’s container image can be hosted here publicly or privately depending on the repository’s setting.

The production deployment is hosted on Microsoft Azure mainly because I had a $100 student credit. I had found it to be confusing at first but later started to get things in their places in no time.

# Final notes

Tools help you get your workflow easier and organised, but good planning will help you stay on track. When working as a team, communication is key to a successful collaboration; keep your teammates updated on success and obstacles. The most important thing for me is to believe that _you can do it_, and that _you have all the power to do it_.

With a good plan, a positive mindset and the right tools, your project will be finished before you even realise.
