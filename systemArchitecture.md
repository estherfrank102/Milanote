1. Architecture Overview

Milanote uses a client–server setup with real-time collaboration.
The system includes:
	-Frontend (web and mobile)
	-Backend API
	-Real-time sync service
	-Cloud database and storage
	-User login and permissions
	-CDN for fast loading of images and files

2. Frontend

Tech Stack:
	-React (web)
	-React Native (mobile)
	-HTML/CSS/TypeScript

Responsibilities:
	-Show boards and content visually
	-Handle drag-and-drop for notes, tasks, and images
	-Save drafts when offline
	-Communicate with backend through REST or WebSocket
	-Display all content clearly

3. Backend

Tech Stack:
	-Node.js + Express
	-WebSocket server for live updates
	-REST API for creating, reading, updating, deleting data

Responsibilities:
	-Manage users and login
	-Handle boards, notes, tasks, and images
	-Keep real-time collaboration working smoothly
	-Track edits and versions
	-Control who can see or edit what

4. Database Layer

Database: MongoDB (document-based)

Collections:
	-Users
	-Boards
	-Items (notes, images, tasks, files)
	-Activity logs
	-Collaboration sessions

Why we use MongoDB:
	-Handles board data easily
	-Scales as the app grows
	-Loads boards and items quickly

5. File Storage

Cloud Storage: AWS S3 or Firebase Storage
Used for:
	-Images
	-Uploaded files
	-Board assets

6. Real-Time Collaboration

Handled through WebSockets

Features:
	-Multiple users can edit at the same time
	-See live cursor and updates
	-Notes, images, and tasks update instantly
	-Prevents conflicts between simultaneous edits

7. Communication Flow
	1.	User does something on the board (add note, move image, etc.).
	2.	Frontend sends it to the backend via REST (for saving) or WebSocket (for live updates).
	3.	Backend updates the database.
	4.	Real-time service pushes updates to all active users.
	5.	UI updates instantly for everyone.


8. Technical Feasibility
	•	React + real-time backend supports smooth drag-and-drop
	•	Document-based database allows flexible boards
	•	WebSockets keep collaboration fast and live
	•	Cloud storage handles media files reliably
	•	Architecture is scalable and ready for more users