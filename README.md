# PeerSync(Tentative)

PeerSync is an academic collaboration hub designed to help students discover peers, collaborate on academic work, hackathons, and projects, all while keeping interactions dynamic. It serves as a centralized platform for both short-term opportunities and long-term professional connections.

## ✨ Core Concept

PeerSync is a hybrid platform combining features from professional networks like LinkedIn, social platforms like Facebook, and collaboration tools like Slack or Teams. Its unique characteristic is the use of event-driven posts that expire after a set period, which keeps the feed relevant and reduces database clutter.

The platform is designed to support:
* **Dynamic, Short-Term Collaboration:** Facilitated through event posts for immediate needs, such as finding teammates for a hackathon.
* **Long-Term Connections:** Built through a friendship network and persistent groups for ongoing teamwork.

---
## 🔑 Key Features

* **User Profiles:** Students create comprehensive profiles with academic and personal details, including their name, specialization, bio, projects, and academic year. This profile acts as the central node connecting a user to all platform activities.
* **Friend Network:** Users can send friend requests to connect with peers. The `Friendship` entity manages these connections with statuses such as `Pending`, `Accepted`, and `Rejected`.
* **Event-Based Posts:** A user can create temporary posts for a specific need (e.g., "Looking for 2 coders for Hackathon X"). These posts include a title, description, required skills, and an `expirationTime` to ensure they are automatically removed after they are no longer relevant.
* **Application System:** Other students can submit applications to event posts. The post creator can then review applicants and update their application status to `Accepted` or `Rejected`.
* **Group Management:** For long-term collaboration, users can form persistent `Groups`. The `GroupMember` entity tracks who belongs to each group, creating a dedicated space for ongoing teams.

---
## 🗄️ Database Schema Overview

The system's functionality is built upon five core entities:

1.  **User:** The central entity for a student's profile.
2.  **Friendship:** A self-referencing relationship on the User entity that manages the status of peer connections.
3.  **Event Post:** Represents a temporary, short-term collaboration opportunity created by a user.
4.  **Application:** Links a `User` to an `Event Post` to which they have applied, tracking the submission status.
5.  **Group & GroupMember:** The `Group` entity defines a team for ongoing projects, while `GroupMember` links users to the groups they belong to.

---
## 💡 Real-Life Workflow Example

Here is a step-by-step example of how the platform is used:

1.  **Profile Creation:** Vedant, a 2nd-year Computer Engineering student, creates his profile, listing his projects like "AI Chatbot".
2.  **Networking:** He finds Ananya (specialization: Data Science) and sends her a friend request. The request is stored with a "Pending" status. After Ananya accepts, the status changes to "Accepted".
3.  **Posting an Opportunity:** Vedant creates an `Event Post` to find a web developer for a hackathon, specifying required skills like React and Node.js, and sets it to expire in 7 days.
4.  **Applying:** Rohit, a 3rd-year student, sees the post and submits an `Application`, which is initially marked as "Pending".
5.  **Team Formation:** Vedant reviews Rohit’s profile and accepts his application by updating the status to "Accepted". Rohit is now on the team.
6.  **Long-Term Collaboration:** For continued work, Vedant creates a `Group` named "Hackathon Warriors" and adds Ananya and Rohit as members. This gives them a permanent space for communication.
