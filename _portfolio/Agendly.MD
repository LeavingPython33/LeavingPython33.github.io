---
title: "Agendly"
excerpt: "Using AI to streamline adding events from syllabi, agendas, and schedules to your calendar."
layout: single
header:
  overlay_image: /assets/img/VandyHackXI.png
  overlay_filter: 0.5
  teaser: https://d112y698adiu2z.cloudfront.net/photos/production/software_photos/003/053/202/datas/medium.jpg
  actions:
    - label: "Devpost"
      url: "https://devpost.com/software/agendly"

categories:
  - Technology
  - Coding
  - Website
tags:
  - Nextjs
  - Openai
  - Typescript
meta: "January 12, 2025"

gallery:
  - url: /assets/img/Cyber-Scooter-1.jpg
    image_path: assets/img/Cyber-Scooter-1.jpg
    alt: "placeholder image 1"
  - url: /assets/img/Cyber-Scooter-2.jpg
    image_path: assets/img/Cyber-Scooter-2.jpg
    alt: "placeholder image 2"
  - url: /assets/img/Cyber-Scooter-3.jpg
    image_path: assets/img/Cyber-Scooter-3.jpg
    alt: "placeholder image 3"

toc: true
toc_label: "Table of Contents"
toc_sticky: true
toc_icon: bars
---

## Demonstration
{% include video id="NWCOUHfcfTk" provider="youtube" %}

## Inspiration
As students, most of us are accustomed to using different Learning Management System (LMS)s. One LMS that many of us used prior to coming to Vanderbilt is Canvas. Canvas has a really great tool that allows you to export your test and assignment dates to calendar softwares, which helps students stay on top of things. One pain point in Vanderbilt's main LMS, Brightspace, is that there's currently no such functionality. We wanted to make the process easier than manually adding every date from every syllabus to your calendar of choice. We then realized that this kind of technology can be used to turn any text agenda into convenient Google Calendar action items!

## What it does
Users log in with their Google Account and are prompted to upload an agenda as a .pdf or .docx file. The program then calls on an LLM to process that text and generate a set of event objects. These are then displayed to the user to allow for edits and any correction needed. The user is then provided with the option to automatically sync these with their Google Calendar or download an .ics file that can be uploaded to Google, Apple, and Notion calendars.

## How we built it
We used Auth.JS to let users log in with Google. For the web app, we used Next.JS 14 with TypeScript and TailWindCSS to create an interactive user interface that lets them upload and download .pdf or .docx files. The Mammoth library was used to convert these text files into plain text. Then, we used the Vercel AI SDK with OpenAI as our model provider (we used GPT-4o for this project) to process this text and generate structured JSON objects that our app displayed and allowed users to edit. We then used a JavaScript function to convert the JSON objects into an .ics file that users could download directly to their computer or sync to their Google Calendar using the Google Calendar API.

## Challenges we ran into
When it came to the underlying LLM task, building on the Vercel AI SDK usually means responding to text with more plain text. However, our project required us to get an LLM to take in text data, break it down into a series of calendar objects, and return it in a specific .ics format. To do this, we had to experiment with different forms of output supported by the Vercel AI SDK, specifically generating a structured object that follows a certain schema, and then formatting it to fit ICS format. During the construction of the actual app, having to display these event objects and allowing the user to edit them was one of our biggest roadblocks. For integration with Google/Google Calendar, we initially wanted to use Auth0 but the authentication with the Google Calendar API wasn't available. Therefore, we had to switch to using Auth.JS and learn how to handle JWT tokens and login state management.

## Accomplishments that we're proud of
We used a REAL Vandy Systems Physiology syllabus and our program was able to successfully parse it and generate test and homework deadlines! We were then able to successfully sync them to Google Calendar with one-click and download the events as an ICS file and upload them to our Apple and Notion calendars!

## What we learned
Aside from learning about full-stack web development, we learned how to work with the Vercel AI SDK and use Zod schema to structure JSON outputs.

## What's next for Agendly
We're looking at three main avenues of improvement: First, one initiative we began but didn't have time to finish was integration with various LMS so that students can directly connect their classes to their calendars. We were planning on webscraping using Python and Selenium to log into an LMS and scrape the syllabus off of every course page. This can help save even more time for our students, as they don't have to upload their separate syllabi. Secondly, we'd like to add a tab on the user's page that saves all the uploaded agendas so they can be redownloaded for convenience. We would ideally use MongoDB to store the IDs and .ICS files associated with each user's text files. Secondly, because we're using a general GPT-4o model to turn event information into calendar files, Agendly can be used for all kinds of agendas! We would like to test it on other kinds of agendas besides syllabi (for clubs, companies, or really anyone who has meetings, because who doesn't ...)

## Built With
* nextjs
* openai
* typescript

## Source Code
<a href="https://github.com/dgzct11/vandy_hacks_2024" class="btn repository"><i class="fab fa-fw fa-github" aria-hidden="true"></i><span> Github Repository</span></a>


{% include gallery caption="This is a sample gallery to go along with this case study." %}
