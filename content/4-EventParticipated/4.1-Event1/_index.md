---
title: "Event 1"
date: 2026-06-07
weight: 1
chapter: false
pre: " <b> 4.1. </b> "
---

# FCAJ Meetup 06-06-2026

**Date:** June 06, 2026.  
**Format:** In-person.  
**Location:** Floor 26, Bitexco Financial Tower, 02 Hai Trieu, Ben Nghe Ward, Ho Chi Minh City.  
**Organizer:** First Cloud & AI Journey (FCAJ) Community.

---

### Purpose of the Meetup

*   From my perspective, this event created a very open space for community members to comfortably share technical knowledge and practical combat experiences with each other.
*   This is a wonderful opportunity for everyone to introduce real-world projects that are applying Cloud and AI technologies.
*   The meetup also greatly inspired me through stories of career advancement in the tech industry.
*   Finally, the event helped me connect with many members from diverse fields and backgrounds.

---

### List of Speakers & Topics

| No. | Speaker | Topic |
|-----|----------|--------|
| 1 | **Mr. Nguyen Quoc Bao** | Rock Paper Scissors with AWS WebSocket – Real-time Multiplayer Game |
| 2 | **Mr. Huynh Nguyen Quoc Bao** | Docker Basics – Virtualization & Containerization |
| 3 | **Mr. Dinh Viet Phat** | GraphRAG – Information retrieval based on knowledge graphs |
| 4 | **Mr. Le Hoang Gia Dai** | AWS WAF & NIDS using Machine Learning |
| 5 | **Mr. Vinh Tran** | From IT Helpdesk to Senior Sysadmin – A career journey |

---

### Outstanding Content

#### Talk 1 – Rock Paper Scissors with AWS WebSocket (Real-time Multiplayer)

Mr. **Nguyen Quoc Bao** shared how to use **Godot 4** as a game client, combined with a completely serverless architecture on AWS:

*   **API Gateway WebSocket** routes connections through `$connect`, `$disconnect`, `$default`, while reading the `action` field in the JSON body to accurately determine the game's processing flow.
*   **AWS Lambda** plays a backend role to handle player matchmaking and calculate win/loss results.
*   **Amazon DynamoDB** is used to store the connection state of each player, including `connectionId`, status (`waiting`/`matched`), `opponentId`, and `choice` (rock/paper/scissors).
*   He also pointed out tough real-world problems such as:
    *   The **GoneException** error occurs when a player has disconnected but DynamoDB still stores the data, causing Lambda to fail when trying to send a message.
    *   The **DynamoDB Scan cost** problem: Using ScanCommand to traverse the entire table is very expensive and slow when the number of players surges.
    *   The **Stateless Lambda** nature: Because Lambda is stateless, every time it is called, it must fetch the game state from DynamoDB again.
*   **Next solution**: For games that need dedicated servers, have high update frequencies, or require real-time physics simulation, switching to **AWS GameLift** would be a more optimal option.

#### Talk 2 – Docker Basics (Virtualization & Containerization)

Mr. **Huynh Nguyen Quoc Bao** – Junior Cloud Native Developer at Endava Vietnam, Founder of ITea Lab.

*   He explained very intuitively the difference between a **Virtual Machine** (each VM must carry its own OS, so it consumes a lot of resources) and a **Container** (super lightweight thanks to the ability to share the host OS's kernel).
*   The core Docker concepts I grasped:
    *   **Dockerfile** is used to define build steps; each command generates an immutable **image layer** — Docker is very smart in knowing how to reuse unchanged layers from the cache to maximize build speed.
    *   **Docker Images** act as a blueprint, while **Containers** are the actual running instances of that image.
    *   Containers operate completely independently of the host machine and are manipulated via the Docker CLI.
*   **Practical application**: Docker is extremely useful for CI/CD pipelines, microservices architectures, dev/test environment setups, building cloud-native apps, or even modernizing legacy apps.
*   The biggest benefit brought is the *"Build once, run anywhere"* philosophy — ensuring applications run consistently from the dev machine to the staging environment and straight to production.

#### Talk 3 – GraphRAG (Graph Retrieval Augmented Generation)

Mr. **Dinh Viet Phat** – AI major student at Swinburne University of Technology.

*   Phat pointed out that **traditional RAG** (retrieving text snippets from a vector database and putting them into an LLM prompt) often struggles with questions requiring **multi-step reasoning** (for example: "Where is the headquarters of the company acquired by the company founded by Jeff Bezos?").
*   **GraphRAG** was born to solve this weakness by storing **relationships between entities in the form of graph edges**, thereby allowing the AI to traverse through a series of interconnected entities and documents.
*   There are two directions for us to deploy on AWS:
    *   **Fully Managed Route**: Combining **Amazon Bedrock Knowledge Bases** (handling chunking, entity extraction, creating embeddings) with **Amazon Neptune Analytics** (to store graphs and discover relationships).
    *   **Custom Route**: Build it yourself with **LlamaIndex** for a custom pipeline and use **Amazon Neptune** to store the Knowledge Graph, from which multi-hop traversals and Cypher Queries are performed.
*   The biggest advantage of GraphRAG is its ability to smoothly handle complex questions intertwining many relationships that pure vector search is powerless against.

#### Talk 4 – AWS WAF & ML-based NIDS

Mr. **Le Hoang Gia Dai** – Final year student at HUTECH University.

*   **AWS WAF** is a defensive checkpoint protecting CloudFront, ALB, API Gateway, and Cognito via Web ACLs and rules (like Allow/Block/Count/CAPTCHA). It is extremely effective against attacks already on the blacklist, but proves weak against zero-day, hybrid, and spoofing attacks.
*   Dai demonstrated building a **Machine Learning-based NIDS**, using the **CSE-CIC-IDS2018** dataset (from the University of New Brunswick), covering attack types such as: DDoS, DoS, Brute Force, SQL Injection, XSS, Bot traffic...
*   The chosen model was **LightGBM** — this model was trained after going through a thorough data preprocessing step (handling NaN/infinity values, balancing data classes, selecting features).
*   A massive AWS architecture picture was drawn: **VPC → EC2 → ALB → AWS WAF → Lambda → Kinesis Data Firehose → S3 → Security Hub + GuardDuty + Inspector → SNS alerts → CloudWatch monitoring**.
*   Core lesson: The quality of input data is decisive; handling class imbalance significantly improves the ability to detect minority attack flows. Furthermore, ML-based NIDS was born to **supplement** the power of AWS WAF, not to replace it.

#### Talk 5 – From IT Helpdesk to Senior Sysadmin

Mr. **Tran Trung Vinh** – System Administrator at Central Retail Group.

*   Mr. Vinh shared about his highly practical career path: From IT Helpdesk stepping up to Sysadmin, and then advancing to Cloud/DevOps Engineer.
*   His time working at the Helpdesk forged his skills in troubleshooting under high pressure, communicating softly with users, and practicing problem-solving mindsets.
*   The daily work of a Sysadmin revolves around server provisioning, network infrastructure management, security patching, and system capacity planning.
*   He emphasized a **Golden Rule**: *"Never test on production — you must always protect the availability, trust, and time of the whole team"*.
*   When transitioning to the Cloud/DevOps sector: He changed his mindset from manual on-premise configuration to using **AWS elastic scaling**, applying **Terraform** (IaC), building **CI/CD pipelines**, and utilizing **Docker**.
*   Hard-earned experience when interviewing at Central Retail Group: Employers heavily focus on real-world projects, acute troubleshooting skills, and architectural design thinking.
*   Career advice from him:
    *   *Dig really deep into 1–2 core areas before intending to expand to others*.
    *   *A portfolio containing real-world projects carries much more weight than pieces of paper with certificates*.
    *   *Where your starting point is doesn't matter — the important thing is to keep moving forward. Every small step is meaningful.*

---

### What I Accumulated

#### Technical Perspective

*   **AWS WebSocket + Lambda + DynamoDB**: I grasped the serverless combo specialized for real-time turn-based applications; meanwhile, AWS GameLift will be the ultimate boss for games requiring high update frequencies.
*   **Docker layers & caching**: Understanding how image layers work will help me write smoother Dockerfiles and maximize overclocking for CI/CD pipelines.
*   **GraphRAG vs. RAG**: It was very interesting to learn that GraphRAG uses Amazon Neptune to store entity relationships as graph edges, allowing AI to perform multi-step reasoning – an ability that pure vector search has to surrender to.
*   **ML applied in security**: The combination of LightGBM-based NIDS and AWS WAF creates a flexible defense wall — signature rules to block old threats, while ML sniffs out new ones.
*   **Infrastructure as Code**: Now I understand why Terraform is so divine in making cloud infrastructure reusable, easily version-controlled, and scalable.

#### Career & Mindset Perspective

*   **Career transition is entirely feasible** as long as we have a proper roadmap and a tireless learning spirit — Mr. Vinh Tran's story is a living testament.
*   Diving into **real-world projects** (like building a multiplayer WebSocket game from scratch) is the shortest path to mastering cloud concepts.
*   **Learning with the community** truly accelerates development — exchanging and absorbing knowledge in a peer-to-peer environment brings unimaginably high efficiency.

---

### Plan to Apply to Work

*   In the near future, I will start tinkering with **AWS API Gateway WebSocket + Lambda** to build real-time features (like push notifications or live dashboards).
*   I will practice writing **Dockerfiles in the most efficient way** — focusing deeply on understanding layer caching to reduce build times.
*   I will certainly dig deeper into **GraphRAG with Amazon Bedrock + Neptune** to apply it to AI features needing complex knowledge processing.
*   In the future, I will consider mixing **AWS WAF and ML-based NIDS** to create a production environment with smarter security.
*   Most importantly, I will build a clear **personal learning roadmap** — pick 1–2 core areas, grind on real-world projects, take notes on everything, and share them.

---

### Personal Experience at the Event

Attending **FCAJ Meetup #1** was truly an eye-opening experience for me. Quite different from the formal, dry vibe of typical workshops or training courses, this event was ablaze with the energy of a passionate community gathering to learn and share together.

#### Extremely Practical Sharing Sessions

Every presentation was distilled from the blood and tears of real combat — from personally building a multiplayer game on the AWS platform to the rocky journey of rising from a helpdesk worker to a senior engineer. This exact element made the knowledge conveyed extremely relatable and highly applicable.

#### Touching the AWS Ecosystem

This meetup helped me skim through a series of AWS services — **API Gateway, Lambda, DynamoDB, WAF, Bedrock, Neptune, GuardDuty, Kinesis** — sketching in my mind an overall architectural picture of how these puzzle pieces coordinate with each other in reality.

#### Enlightenment on AI

The talk on **GraphRAG** was the spotlight of that evening for me personally. It completely changed my mindset on how AI retrieves information — breaking through the limits of flat vector search to reach the level of knowledge extraction based on structural graphs. Hearing the analysis of the differences between the Fully Managed flow (Bedrock + Neptune Analytics) and the Custom flow (LlamaIndex + Neptune) mapped out an extremely clear starting line for me to begin practicing.

#### Drawing Inspiration from Career Stories

**Mr. Vinh Tran's journey** from an IT Helpdesk staff member to a Senior Sysadmin position at Central Retail Group was one of the most inspiring moments of the night. His mental structure when troubleshooting: *understand the system clearly, find ways to minimize damage, dig deep into root causes, and the survival rule is never test on production* — is precious baggage I will always carry. His sharing solidified my belief that: as long as there is technical depth, persistent perseverance, and a proper orientation, anyone can go very far in this technology industry.

#### Takeaways Brought Home

*   **Only real-world projects bring real-world lessons** — the WebSocket game demo clearly proved that theory only truly "lives" when you roll up your sleeves and build a product from start to finish.
*   **Docker's power far exceeds my thoughts** — understanding layer caching, deploying across multiple platforms, or testing containers brings a depth of knowledge much greater than the simple concept of "packaging an app".
*   **Machine Learning is the perfect puzzle piece for rule-based systems** — I realized that AWS WAF standing alone is not enough; pairing it with ML-based NIDS creates a genuinely adaptive security shield.
*   **The community is the catalyst** — breathing the same air with brothers who are day and night grinding, building, and developing systems generates a powerful energy flow that I could never find while studying online alone.

#### Images While Attending the Event

![FCAJ Meetup 1 - June 06, 2026](/images/4-EventParticipated/4.1-Event1/meetup-1.jpg)

> Overall, the FCAJ Meetup was a highly enthusiastic head start for my journey of learning from the community. The richness of the topics — ranging from game development, AI making, to career advancement — showed me just how vast and full of interesting things this Cloud & AI world is. I walked out of the event with a head full of new ideas, new friends, and an immense source of motivation to continue the path of conquering technology.
