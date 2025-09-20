# PeerSync (Tentative)🚀

[cite_start]PeerSync is an academic collaboration hub designed to help students discover peers, collaborate on academic work, hackathons, and projects, all while keeping interactions dynamic[cite: 3]. [cite_start]It serves as a centralized platform for both short-term opportunities and long-term professional connections[cite: 53].

## ✨ Core Concept

[cite_start]PeerSync is a hybrid platform combining features from professional networks like LinkedIn, social platforms like Facebook, and collaboration tools like Slack or Teams[cite: 2]. [cite_start]Its unique characteristic is the use of event-driven posts that expire after a set period, which keeps the feed relevant and reduces database clutter[cite: 2, 52].

The platform is designed to support:
* [cite_start]**Dynamic, Short-Term Collaboration:** Facilitated through event posts for immediate needs, such as finding teammates for a hackathon[cite: 50, 26].
* [cite_start]**Long-Term Connections:** Built through a friendship network and persistent groups for ongoing teamwork[cite: 49].

---

## 🔑 Key Features

* [cite_start]**User Profiles:** Students create comprehensive profiles with academic and personal details, including their name, specialization, bio, projects, and academic year[cite: 7, 8]. [cite_start]This profile acts as the central node connecting a user to all platform activities[cite: 9].
* [cite_start]**Friend Network:** Users can send friend requests to connect with peers[cite: 38]. [cite_start]The `Friendship` entity manages these connections with statuses such as `Pending`, `Accepted`, and `Rejected`[cite: 15].
* [cite_start]**Event-Based Posts:** A user can create temporary posts for a specific need (e.g., "Looking for 2 coders for Hackathon X")[cite: 25, 26]. [cite_start]These posts include a title, description, required skills, and an `expirationTime` to ensure they are automatically removed after they are no longer relevant[cite: 23, 27].
* [cite_start]**Application System:** Other students can submit applications to event posts[cite: 31]. [cite_start]The post creator can then review applicants and update their application status to `Accepted` or `Rejected`[cite: 33].
* [cite_start]**Group Management:** For long-term collaboration, users can form persistent `Groups`[cite: 46]. [cite_start]The `GroupMember` entity tracks who belongs to each group, creating a dedicated space for ongoing teams[cite: 18, 47].

---

## 🗄️ Database Schema Overview

The system's functionality is built upon five core entities:

1.  [cite_start]**User:** The central entity for a student's profile[cite: 9].
2.  [cite_start]**Friendship:** A self-referencing relationship on the User entity that manages the status of peer connections[cite: 14, 15].
3.  [cite_start]**Event Post:** Represents a temporary, short-term collaboration opportunity created by a user[cite: 25, 26].
4.  [cite_start]**Application:** Links a `User` to an `Event Post` to which they have applied, tracking the submission status[cite: 29, 31].
5.  [cite_start]**Group & GroupMember:** The `Group` entity defines a team for ongoing projects, while `GroupMember` links users to the groups they belong to[cite: 17, 18, 21].

---

## 💡 Real-Life Workflow Example

[cite_start]Here is a step-by-step example of how the platform is used[cite: 57]:

1.  [cite_start]**Profile Creation:** Vedant, a 2nd-year Computer Engineering student, creates his profile, listing his projects like "AI Chatbot"[cite: 59, 60, 61, 62, 63].
2.  [cite_start]**Networking:** He finds Ananya (specialization: Data Science) and sends her a friend request[cite: 66]. [cite_start]The request is stored with a "Pending" status[cite: 67]. [cite_start]After Ananya accepts, the status changes to "Accepted"[cite: 68].
3.  [cite_start]**Posting an Opportunity:** Vedant creates an `Event Post` to find a web developer for a hackathon, specifying required skills like React and Node.js, and sets it to expire in 7 days[cite: 71, 72, 74, 75, 76].
4.  [cite_start]**Applying:** Rohit, a 3rd-year student, sees the post and submits an `Application`, which is initially marked as "Pending"[cite: 79, 80].
5.  [cite_start]**Team Formation:** Vedant reviews Rohit’s profile and accepts his application by updating the status to "Accepted"[cite: 83, 85]. [cite_start]Rohit is now on the team[cite: 86].
6.  [cite_start]**Long-Term Collaboration:** For continued work, Vedant creates a `Group` named "Hackathon Warriors" and adds Ananya and Rohit as members[cite: 88, 89, 91]. [cite_start]This gives them a permanent space for communication[cite: 93].
