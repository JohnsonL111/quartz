---
title: Projects
date: 2023/12/03
---

<head>
  <title>Two Photos Side by Side</title>
  <link rel="stylesheet" href="../style.css">
  <style>
    .projects-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 40px;
      margin-top: 20px;
    }

    .project-filters {
      display: flex;
      flex-wrap: wrap;
      gap: 10px;
      margin: 24px 0 8px;
    }

    .project-filter-input {
      position: absolute;
      width: 1px;
      height: 1px;
      opacity: 0;
      pointer-events: none;
    }

    .project-filter-label {
      padding: 7px 14px;
      border: 1px solid var(--lightgray);
      border-radius: 999px;
      cursor: pointer;
      font-size: 0.9rem;
      font-weight: 600;
      transition: background-color 0.2s ease, border-color 0.2s ease, color 0.2s ease;
    }

    .project-filter-label:hover {
      border-color: var(--secondary);
      color: var(--secondary);
    }

    .project-filter-input:focus-visible + .project-filter-label {
      outline: 2px solid var(--secondary);
      outline-offset: 2px;
    }

    .project-filter-input:checked + .project-filter-label {
      color: var(--light);
      background: var(--secondary);
      border-color: var(--secondary);
    }

    body:has(#filter-hackathon:checked) .project-item:not(.category-hackathon),
    body:has(#filter-course:checked) .project-item:not(.category-course),
    body:has(#filter-club:checked) .project-item:not(.category-club),
    body:has(#filter-personal:checked) .project-item:not(.category-personal) {
      display: none;
    }
    
    @media (max-width: 1200px) {
      .projects-grid {
        grid-template-columns: 1fr;
      }
    }
    
    .project-item {
      break-inside: avoid;
    }
    
    .project-item h2 {
      margin-top: 0;
    }

    .project-tag {
      display: inline-block;
      margin: 0 0 14px;
      padding: 4px 10px;
      border-radius: 999px;
      color: var(--darkgray);
      background: var(--highlight);
      font-size: 0.78rem;
      font-weight: 700;
      letter-spacing: 0.03em;
      text-transform: uppercase;
    }
  </style>
</head>

> Software projects that I've built/contributed to.

<div class="project-filters" role="radiogroup" aria-label="Filter projects by category">
  <input class="project-filter-input" type="radio" name="project-filter" id="filter-all" checked>
  <label class="project-filter-label" for="filter-all">All</label>
  <input class="project-filter-input" type="radio" name="project-filter" id="filter-hackathon">
  <label class="project-filter-label" for="filter-hackathon">Hackathons</label>
  <input class="project-filter-input" type="radio" name="project-filter" id="filter-course">
  <label class="project-filter-label" for="filter-course">Courses</label>
  <input class="project-filter-input" type="radio" name="project-filter" id="filter-club">
  <label class="project-filter-label" for="filter-club">Clubs &amp; Programs</label>
  <input class="project-filter-input" type="radio" name="project-filter" id="filter-personal">
  <label class="project-filter-label" for="filter-personal">Personal</label>
</div>

<div class="projects-grid">
<div class="project-item category-hackathon">

## Argus: Git for quant researchers, secured by blockchain

<span class="project-tag">Hackathon</span>

<img src="../posts/attachments/argus_block.png" alt="Argus blockchain view" />

<br />

<iframe
  width="100%"
  height="400"
  src="https://www.youtube.com/embed/p849nn0xS1k"
  title="Argus Demo"
  frameborder="0"
  allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
  allowfullscreen>
</iframe>

**Argus** is a Git-like versioning tool for quantitative researchers built on the Solana blockchain. It enables deterministic and immutable replayability of version-controlled models and datasets, making experimentation, iteration, and auditing of quantitative signals transparent and verifiable.

Argus brings familiar developer workflows to quantitative research while adding cryptographic guarantees around data integrity and provenance. By anchoring version metadata on-chain and maintaining a lightweight local index, the system ensures that model runs can be reliably reproduced and independently verified.

**Stack:** Python, Textual, Rust, Anchor, Solana, Vultr, SQLite

🏆*Won "Best use of Solana" at NWHacks 2026 (650+ hackers)* <br>
<a target="_blank" href="https://github.com/JohnsonL111/argus">GitHub</a>&emsp;
<a target="_blank" href="https://devpost.com/software/argus-fgtsu5">Devpost</a>&emsp;

</div>
<div class="project-item category-hackathon">

## 26 Studio: Interactive Vancouver 2026 Kit Viewer

<span class="project-tag">Hackathon</span>

![Vancouver 2026 interactive kit viewer](../posts/attachments/sea_to_sky.jpg)

We built a real-time 3D product experience for a Vancouver FIFA World Cup 2026 host city kit concept. Users can rotate and flip synchronized jersey and shorts models, select hotspots to zoom into design details, and explore procedural textures inspired by Vancouver's cherry blossoms, Coast Mountains, Pacific currents, and Sea to Sky Highway.

The experience uses procedurally generated geometry and HTML5 Canvas textures, physically based materials, animated camera transitions, and responsive mouse and touch controls.

**Stack:** React, Three.js, JavaScript, HTML5 Canvas API, Vite

🏆*Won "Best Use of AI" at Vancouver Made* <br>
<a target="_blank" href="https://johnsonl111.github.io/interactive-3d-devin-worldcup-model/">Deployment</a>&emsp;
<a target="_blank" href="https://github.com/JohnsonL111/interactive-3d-devin-worldcup-model">GitHub</a>&emsp;

</div>
<div class="project-item category-hackathon">

## Study Mog: Multiplayer Pomodoro Accountability

<span class="project-tag">Hackathon</span>

![Study Mog multiplayer lobby](../posts/attachments/devin_1.jpg)

 We built a real-time multiplayer Pomodoro app for the agents of chaos track that turns focus sessions into a social accountability game. Participants can send surprise 60-second "Mog Checks" that challenge friends to submit webcam proof that they are still studying, while an Aura leaderboard and end-of-session MVP recap track performance.

**Stack:** Next.js, React, TypeScript, Tailwind CSS, Socket.IO, Node.js, Express, MediaDevices API

🏆*Won 1st Runner-Up at the Devin AI Hackathon* <br>
<a target="_blank" href="https://github.com/JohnsonL111/yet-another-devin-hack">GitHub</a>&emsp;

</div>
<div class="project-item category-course">

## Hope Health Action: Community Based Rehabilitation Application

<span class="project-tag">Course</span>

![HHA](../posts/attachments/hha_main.png)

Developing the web and mobile application supporting community based rehabilitation services as part of SFU research projects for HHA, a non-profit. Primarily working on test automation and features to the mobile client.

**Stack:** React Native, Expo, Django, Python, Docker, Postgres

<a target="_blank" href="https://github.sfu.ca/bfraser/415-HHA-CBR">GitHub</a>&emsp;

</div>

<div class="project-item category-personal">

## BotBouncers: AI Edge Bot Access Control & Observability

<span class="project-tag">Personal</span>

![ai-edge-bot](../posts/attachments/ai-edge-bot.png)
![architecture](../posts/attachments/architectural_diagram.png)

I built an AI-focused bot access control layer that runs at the CDN edge, allowing users to generate and enforce `robots.txt` rules per-crawler using AWS CloudFront + Lambda@Edge. The system inspects CloudFront logs streamed through S3 and SQS into an analytics Lambda, which aggregates per-bot, per-path metrics into DynamoDB. A React-based dashboard lets site owners configure bot policies, view allowed vs. disallowed traffic over time, and safely test changes without redeploying the site.

Stack: AWS CloudFront, Lambda@Edge, S3, SQS, API Gateway, DynamoDB, React, Typescript, NodeJS

<a target="_blank" href="https://github.com/JohnsonL111/botbouncer">GitHub</a>&emsp;

</div>
<div class="project-item category-club">

## Reel Youth – Mobile-First Headless Website (Technical Project Lead)

<span class="project-tag">Club &amp; Program</span>

<table>
  <tr>
    <td><a href="web_architecture (1).png" target="_blank"><img src="web_architecture (1).png" width="300"/></a></td>
    <td><a href="ry_gallery.png" target="_blank"><img src="ry_gallery.png" width="300"/></a></td>
  </tr>
  <tr>
    <td><a href="ry_media.png" target="_blank"><img src="ry_media.png" width="300"/></a></td>
    <td><a href="ry_programs.png" target="_blank"><img src="ry_programs.png" width="300"/></a></td>
  </tr>
</table>

As Technical Project Lead at SFU Blueprint, I led a team of developers and designers to build Reel Youth’s new mobile-first website from 0→1 using a fully headless architecture improving accessibility, SEO, and mobile responsiveness. We created a custom WordPress CMS w/ 15+ custom post types based on the NPOs needs and integrated it with a Next.js/Typescript frontend w/ a graphql data api layer, enabling the NPO to easily manage programs, films, and marketing content. 

I met with the client along with the PM/Designers, oversaw technical direction/systems architecture, CI/CD pipelines, developer onboarding, and implemented core features including the page for managing historical films and programs, a manual publish trigger enabling staff to push CMS changes live with one click, and Cloudflare deployment/CDN for fast global performance along with integrating multi-stage deployments with a staging and production environment.

Stack: Next.js, Typescript, GraphQL/Apollo, Faust.js, Supabase (postgres + serverless typescript APIs), Storybook, Headless WordPress, Cloudflare

<a target="_blank" href="https://reelyouth-demo.xyz/">Deployment</a>&emsp;
<a target="_blank" href="https://github.com/SFU-Blueprint/Reel-Youth">GitHub</a>&emsp;

</div>
<div class="project-item category-club">

## MOSAIC - AI Conversational ChatBot (Developer)
<span class="project-tag">Club &amp; Program</span>

![ai-chatbot](../posts/attachments/mosaic_pic.png)

As a developer on this project through SFU blueprint my 2 primary contributions were to <br>
(1) provide a method to automate the process to update the neo4J graph database with new program data and to <br>
(2) Provide a POC for transferring the chatbot react application to wordpress with full feature parity along with writing/filming documentation for the npo to replicate steps.

Stack: React, Typescript, Tailwind, Python, Langchain, Neo4J

<a target="_blank" href="https://mosaicmate.vercel.app/">Deployment</a>&emsp;

</div>
<div class="project-item category-club">

## InvolveMINT

<span class="project-tag">Club &amp; Program</span>

![involveMINT](../posts/attachments/involvemint.png)

As part of the <a target="_blank" href="https://www.developforgood.org/">Develop For Good</a> Winter 2024 cohort I worked on a team of 7 devs to migrate InvolveMINT's backend API functionality into NestJS. This way the non-profit improves site security and long term scalability by moving away from the sunsetted open source framework <a target="_blank" href="https://github.com/jczacharia/orcha">OrchaJS</a> that dominates the backend.

Stack: NestJS, Typescript, NodeJS, Angular, Jest, TypeORM, Docker, Firebase (Auth/Firestore), PostgreSQL, Git

<a target="_blank" href="https://github.com/involveMINT/iMPublic">GitHub</a>&emsp;
<a target="_blank" href="https://app.involvemint.io/">Deployment</a>

</div>
<div class="project-item category-hackathon">

## WhereU@

<span class="project-tag">Hackathon</span>

![WhereU@](../posts/attachments/whereUAt.png)

<center> Mid-animation landing page </center> <br>

Worked in a team of 4 during NWHacks 2023 to develop a full-stack web-application to fight against FOMO where users can subscribe to one another or a location and be notified when that user moves locations or when any user moves to a subscribed location. Inspired by snapchat's location tracking feature, but without the data collection.

Stack: Java, Spring Boot, React.js, CockroachDB, HTML, CSS, JavaScript, Twilio API, Axios, Postman

<a target="_blank" href="https://github.com/JohnsonL111/where-u-at">GitHub</a>&emsp;
<a target="_blank" href="https://devpost.com/software/whereu">DevPost</a>

</div>
<div class="project-item category-hackathon">

## Sigma.IO

<span class="project-tag">Hackathon</span>

![SigmaIO](../posts/attachments/sigmaIO.png)

Worked in a team of 4 during Stormhacks 2022 to build a web application that takes in audio or video file input and outputs a summary of the uploaded content.

Stack: ReactJS, AssemblyAI API, HTML, CSS, Javascript, Git

<a target="_blank" href="https://github.com/JohnsonL111/Sigma.io">GitHub</a>&emsp;
<a target="_blank" href="https://sigmaio.netlify.app/">Deployment </a> &emsp;
<a target="_blank" href="https://www.youtube.com/watch?v=9fAU0wKU-hQ">Demo</a>

</div>
<div class="project-item category-personal">

## BookWise

<span class="project-tag">Personal</span>

![BookWise](../posts/attachments/books_list.png)
Full-stack web app to track your book collection. Uses mongoose ORM to abstract DB operations. Features toggleable Table/Card view and alerts. More features to come :).

Stack: Nodejs, Expressjs, MongoDB, Mongoose, ReactJs, Tailwind, Vite, Axios

<a target="_blank" href="https://github.com/JohnsonL111/book-wise">GitHub</a>&emsp;

</div>
<div class="project-item category-course">

## FindMyPig

<span class="project-tag">Course</span>

![FindMyPig](../posts/attachments/findMyPig.png)

For my Web Development I final project I developed an angular CRUD pig locator web application. Here you can report missing pigs and visualize their locations on a live map courtesy of Leaflet

Stack: Angular, Typescript, HTML, Bootstrap (CSS), Leaflet API, Postman

<a target="_blank" href="https://github.com/JohnsonL111/find-my-pig">GitHub</a>&emsp;
<a target="_blank" href="https://findmypig.netlify.app/">Deployment </a>

</div>
<div class="project-item category-course">

## 1-2-Tree: Parenting Made Easy

<span class="project-tag">Course</span>

<div class="image-container">
  <img src="../posts/attachments/parentingMadeEasyPic1.png" alt="Home Screen">
  <img src="../posts/attachments/parentingMadeEasyPic2.png" alt="Children Screen">
</div>

For my Intro to Software Engineering Class I worked in a team of 4 in an agile scrum format to build an android app to help parents cope with having children. The app allows for CRUD on children and on task assignment (start 'em early), a coin flip feature to arbitrate decisions, a timeout feature, and breathing exercises based off a state machine.

Stack: Java, Android Studio, SharedPreferences, Git

<a target="_blank" href="https://github.com/JohnsonL111?page=2&tab=repositories">GitHub</a>&emsp;

</div>
<div class="project-item category-course">

## Bitcoin Minefinder Game

<span class="project-tag">Course</span>

<div>
  <img src="../posts/attachments/mineFinderPic1.png" alt="Home Screen">
  <img src="../posts/attachments/mineFinderPic2.png" alt="Children Screen">
</div>

Worked in a team of 2 to develop a bitcoin themed mine finder android game based off minesweeper. Users can configure the number of bitcoins and blockchain size. The best score is saved.

Stack: Java, Android Studio, SharedPreferences, Git

<a target="_blank" href="https://github.com/JohnsonL111/Totally-Accurate-Bitcoin-Mining-Simulator?tab=readme-ov-filetab=repositories">GitHub</a>&emsp;

</div>
<div class="project-item category-course">

## NutriNote

<span class="project-tag">Course</span>

![NutriNote](../posts/attachments/consumableItem.png)

A desktop app to manage the expiry dates of your refridgerator items through CRUD operations. Developed with a Swing GUI frontend and Spring Boot RESTful backend. Utilizes Gson to serialize/deserialize POJO to Json Objects to seamlessly save/load item information respectively.

Stack: Java, Spring Boot, Swing GUI, REST API, Gson, HTTP Client

<a target="_blank" href="https://github.com/JohnsonL111/nutri-note">GitHub</a>&emsp;

</div>
<div class="project-item category-hackathon">

## Space Oddysey

<span class="project-tag">Hackathon</span>

![Space Oddysey](../posts/attachments/spaceOddysey.png)

My friends and I decided to build a space exploration site at our first hackathon: SOSY's Hackademia. This was back before we even knew how to code (heck, we used google docs as version control). It's a pretty simple site with fun facts, a space quiz, and a space visualizer.

Stack: HTML, CSS, Javascript, Jquery

<a target="_blank" href="https://github.com/JohnsonL111/Space-Odyssey">GitHub</a>&emsp;
<a target="_blank" href="https://spaceodysseyhackademia.netlify.app/">Deployment</a>&emsp;

</div>
<div class="project-item category-course">

## Memory Card Game

<span class="project-tag">Course</span>

![Space Oddysey](../posts/attachments/memoryCardGame.png)

Terminal implementation of the <a target="_blank" href="https://en.wikipedia.org/wiki/Concentration_(card_game)">Concentration</a> card game.

Stack: C

<a target="_blank" href="https://github.com/JohnsonL111/Concentration-Memory-Card-Game">GitHub</a>&emsp;

</div>
</div>

