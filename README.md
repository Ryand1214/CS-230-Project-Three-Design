CS 230 Operating Platforms: The Gaming Room Software Design Document

This repository contains the software design document I completed for The Gaming Room in CS 230 at Southern New Hampshire University. The document covers the full design of a web-based version of their game, Draw It or Lose It, including the executive summary, requirements, design constraints, domain model, platform evaluation, and final recommendations.

File: CS 230 Project Three Software Design Document Ryan Doswell.docx

Reflection
Briefly summarize The Gaming Room client and their software requirements. Who was the client? What type of software did they want you to design?

The Gaming Room is a client that already had a game called Draw It or Lose It, but it only ran on Android. The game is similar to the old TV show Win, Lose or Draw, where teams try to guess what a drawing is as it gets rendered on screen before time runs out. The Gaming Room wanted to expand the game into a web-based application that could run across multiple platforms. Their requirements were that a game could have one or more teams, each team could have multiple players, every game and team name had to be unique so players could check whether a name was already taken, and only one instance of the game service could exist in memory at any given time, with unique identifiers for every game, team, and player.

What did you do particularly well in developing this documentation?

I think I did a good job connecting the client's requirements directly to specific design decisions instead of just restating them. When the client said only one instance of the game could exist, I tied that to the singleton pattern in the GameService class, and when they said names had to be unique, I tied that to the iterator pattern that checks existing games and teams before adding a new one. I also think the Evaluation section was strong because I compared Mac, Linux, Windows, and mobile devices on the server side, client side, and development tools with real details like licensing costs and browser restrictions, which made the final recommendations feel earned instead of picked out of thin air.

What about the process of working through a design document did you find helpful when developing the code?

Building the domain model and UML class diagram before writing the code made the coding part a lot smoother. Once I had the Entity base class mapped out with the shared id and name fields, it was obvious that Game, Team, and Player should all extend it, which cut down on repeated code. Having the relationships laid out ahead of time also meant I already knew where methods like addTeam and addPlayer belonged and what they needed to check, so I wasn't guessing at structure while I was coding.

If you could choose one part of your work on these documents to revise, what would you pick? How would you improve it?

I would revise the Evaluation section, specifically the cost discussion. I covered licensing and the general cost differences between platforms, but I would add a rough estimate of what hosting would actually cost The Gaming Room at different player counts, like a small launch versus a large user base. That would give the client a clearer picture of how the costs scale and make it easier for them to plan a budget, rather than just knowing which option is cheaper in general.

How did you interpret the user's needs and implement them into your software design? Why is it so important to consider the user's needs when designing?

I treated each of the client's requirements as something that had to show up somewhere concrete in the design. Unique names became the iterator check, the single instance requirement became the singleton, and the need to reach players on any device became a web-based client backed by a Linux server, with a database for permanent records, a fast cache for live game state, and a content delivery network for the image library. Considering the user's needs matters because a design can be technically solid and still fail if it doesn't solve the problem the client actually has. If I had designed around what was easiest for me instead of what The Gaming Room needed, the result would have been expensive to fix later.

How did you approach designing software? What techniques or strategies would you use in the future to analyze and design a similar software application?

I approached it in layers. I started with the requirements and constraints, then built the domain model, then evaluated the platforms, and only after all of that made recommendations, so each step was built on the one before it. In the future I would keep that same order, but I would add user stories and use case diagrams early on to make sure I fully understand how players will interact with the system, and sequence diagrams to map out how the client and server talk to each other during a game. I would also want to check in with the client more often with small prototypes so problems get caught early instead of after the design is finished.
