# SpillR – Project Case Study

This repository documents my work on **SpillR**, a full-stack web application developed as a collaborative group project.

SpillR is a React Native social platform built as a synchronised commentary layer for live, reality and episodic TV. Users join live chat threads tied to specific episodes, with every comment, reaction, and poll anchored to an exact timestamp in the show's runtime.
The core experience works in two modes: on premiere night, viewers watch live and drop reactions as moments unfold - plot twists, fan theories, shock cuts. After broadcast, any user can hit play on their streaming platform of choice and start timeline replay on SpillR, which displays comments, replies and reactions in real time exactly as they were posted during the original airing.

SpillR is designed for the gap between watching alone and watching together, where the second-screen experience becomes part of the show.

## Original Project Repositories

Frontend: https://github.com/Ines1299/SpillR-app  
Backend: https://github.com/yewen-jin/spillr-BE

The original repositories contain the full source code and commit history for the project.

Architectural diagrams can be found under screenshots/

![SpillR Homepage Screenshot](screenshots/homepage.png)

![SpillR Live Chat Screenshot](screenshots/live-chat.png)

## Tech Stack

## Backend:

- Express server hosting a REST API and a Socket.io WebSocket server for real-time writes and broadcasting new comments

- Express server hosted on Render

- Data stored in a single PostgreSQL database hosted on Supabase

- GitHub Action script to ping the Render server (free tier) every 10 minutes to prevent the server from going to sleep during demo day

## Frontend:

- React Native with Expo, using a single codebase deployable to both iOS and Android

Key features include:

- A polling system for fetching data from the backend

- An internal timer using `setInterval()` to track and synchronise comments with the episode timeline

## My Role in the Project

In this project I contributed to the development of several core features across both the frontend and backend, including:

- Developing core frontend UI components, including the **timeline scrubbing interface** and **user opinion polls**

- Implementing backend API endpoints to support **offset-based pagination for an infinite scroll comment feed**

- Developing logic to **prioritise and surface comments from a user’s friends** within the feed

- Researching and selecting appropriate external APIs and reviewing documentation for integrating TV show and episode data

- Creating utility helper functions to support **asynchronous data fetching from the backend**

- Assisting with the implementation and integration of **WebSocket functionality** across the frontend and backend to support real-time comments and reactions

## To be implemented

- A cron job running every 24 hours to fetch updates from the TV API, keeping show, season, and episode data current while automatically opening episode threads ahead of broadcast

- A Redis-based anti-spam system to limit the rate of comments that can be sent within a short period of time
