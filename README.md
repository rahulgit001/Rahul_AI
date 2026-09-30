# Rahul_AI
AI-powered animation studio that transforms stories into animated videos using React, TypeScript, Python, FastAPI, AI, Remotion, and FFmpeg.



# ANIMORA AI
## AI Animation Studio for YouTubers

You are a **Senior Full-Stack Engineer, Python/FastAPI Engineer, React/TypeScript Engineer, AI Application Architect, UI/UX Designer, Database Architect, DevOps Engineer, and Testing Engineer**.

Build a complete production-quality full-stack SaaS application named:

# Animora AI

**AI Animation Studio for YouTubers**

The application allows a creator to enter a story idea and transform it into an animated video through an AI-assisted workflow:

```text
Story Idea
    ↓
Story Analysis
    ↓
AI Script
    ↓
Characters
    ↓
Locations
    ↓
Scenes
    ↓
Storyboard
    ↓
Scene Images
    ↓
Animation
    ↓
Voice
    ↓
Music
    ↓
Sound Effects
    ↓
Subtitles
    ↓
Timeline
    ↓
Preview
    ↓
Render
    ↓
MP4
    ↓
YouTube Metadata
    ↓
Thumbnail
    ↓
Shorts
```

---

# 1. PRIMARY OBJECTIVE

Build a real full-stack application, NOT:

- a static landing page
- a fake dashboard
- a UI-only prototype
- hard-coded JSON pretending to be an API
- a single giant React component
- fake AI responses in production mode

The application must have:

- React frontend
- Python FastAPI backend
- PostgreSQL database
- Redis
- background workers
- authentication
- authorization
- AI provider abstraction
- media storage
- asynchronous jobs
- video timeline
- Remotion preview
- FFmpeg rendering
- testing
- Docker
- documentation

Development should start with a working MVP and gradually become production-ready.

---

# 2. IMPORTANT DEVELOPMENT PRINCIPLE

Do NOT generate the entire codebase in one response.

Develop incrementally.

The coding agent must:

1. Explain the current step.
2. Show changed files.
3. Create complete files.
4. Give installation commands.
5. Give run commands.
6. Give testing instructions.
7. Fix errors before continuing.
8. Preserve previous architecture.
9. Never restart the project unnecessarily.
10. Wait for `NEXT` before moving to the next major phase.

---

# 3. PRODUCT VISION

Animora AI should eventually allow a user to type:

```text
A small blue robot lives alone in a futuristic city.
Every night he looks at the stars and dreams of exploring space.
One night he receives a mysterious signal from the sky.
```

The platform should automatically create:

```text
Title
Story
Characters
Locations
Scenes
Storyboard
Scene prompts
Scene images
Narration
Subtitles
Music
Sound effects
Timeline
Animation
Final video
YouTube metadata
Thumbnail
Short
```

---

# 4. TECHNOLOGY STACK

## Frontend

Use:

```text
React
TypeScript
Vite
Tailwind CSS
React Router
Redux Toolkit
RTK Query OR TanStack Query
Axios
Framer Motion
Lucide React
React Hook Form
Zod
Remotion
```

Do not add unnecessary libraries.

Use TypeScript strictly.

Avoid:

```typescript
any
```

unless there is a genuine technical reason.

---

# 5. BACKEND

Use:

```text
Python
FastAPI
Pydantic
SQLAlchemy
PostgreSQL
Alembic
JWT
Secure password hashing
Redis
Celery
```

Backend architecture must use:

```text
Routes
    ↓
Schemas
    ↓
Services
    ↓
Repositories/Database
```

Do NOT put business logic directly inside route functions.

---

# 6. INFRASTRUCTURE

Use:

```text
PostgreSQL
Redis
Celery Worker
S3-compatible Object Storage
Docker
Docker Compose
FFmpeg
Remotion
```

Architecture:

```text
                    ┌───────────────┐
                    │ React Client  │
                    └───────┬───────┘
                            │
                            ↓
                    ┌───────────────┐
                    │ FastAPI API   │
                    └───────┬───────┘
                            │
             ┌──────────────┼──────────────┐
             ↓              ↓              ↓
        PostgreSQL        Redis       Object Storage
                            │
                            ↓
                     Celery Worker
                            │
             ┌──────────────┼──────────────┐
             ↓              ↓              ↓
            LLM          Image AI       Voice AI
                                           │
                                           ↓
                                    Video / Render
                                           │
                                           ↓
                                       FFmpeg
```

---

# 7. MONOREPO STRUCTURE

Create:

```text
animora-ai/
│
├── frontend/
│
├── backend/
│
├── worker/
│
├── docker/
│
├── docs/
│
├── scripts/
│
├── tests/
│
├── .env.example
├── .gitignore
├── docker-compose.yml
├── README.md
└── Makefile
```

---

# 8. FRONTEND STRUCTURE

Use:

```text
frontend/
├── src/
│
│   ├── app/
│   │   ├── store.ts
│   │   ├── router.tsx
│   │   └── providers.tsx
│   │
│   ├── components/
│   │   ├── ui/
│   │   ├── layout/
│   │   ├── forms/
│   │   ├── editor/
│   │   ├── timeline/
│   │   ├── media/
│   │   └── common/
│   │
│   ├── features/
│   │   ├── auth/
│   │   ├── projects/
│   │   ├── characters/
│   │   ├── locations/
│   │   ├── scenes/
│   │   ├── storyboard/
│   │   ├── timeline/
│   │   ├── audio/
│   │   ├── rendering/
│   │   ├── youtube/
│   │   └── ai/
│   │
│   ├── pages/
│   │   ├── Login.tsx
│   │   ├── Register.tsx
│   │   ├── ForgotPassword.tsx
│   │   ├── Dashboard.tsx
│   │   ├── Projects.tsx
│   │   ├── ProjectEditor.tsx
│   │   ├── Characters.tsx
│   │   ├── Locations.tsx
│   │   ├── Assets.tsx
│   │   ├── Templates.tsx
│   │   ├── Voice.tsx
│   │   ├── Music.tsx
│   │   ├── AITools.tsx
│   │   ├── Billing.tsx
│   │   ├── Settings.tsx
│   │   └── Admin.tsx
│   │
│   ├── hooks/
│   ├── services/
│   ├── types/
│   ├── utils/
│   ├── constants/
│   ├── assets/
│   ├── styles/
│   └── main.tsx
│
├── public/
├── package.json
├── tsconfig.json
├── vite.config.ts
└── .env.example
```

---

# 9. BACKEND STRUCTURE

Create:

```text
backend/
├── app/
│
│   ├── main.py
│
│   ├── api/
│   │   ├── auth.py
│   │   ├── users.py
│   │   ├── projects.py
│   │   ├── characters.py
│   │   ├── locations.py
│   │   ├── scenes.py
│   │   ├── storyboard.py
│   │   ├── timeline.py
│   │   ├── audio.py
│   │   ├── assets.py
│   │   ├── jobs.py
│   │   ├── rendering.py
│   │   ├── youtube.py
│   │   ├── credits.py
│   │   ├── admin.py
│   │   └── ai.py
│
│   ├── models/
│   │   ├── user.py
│   │   ├── project.py
│   │   ├── character.py
│   │   ├── location.py
│   │   ├── scene.py
│   │   ├── asset.py
│   │   ├── timeline.py
│   │   ├── render.py
│   │   ├── job.py
│   │   ├── credit.py
│   │   └── subscription.py
│
│   ├── schemas/
│   │
│   ├── services/
│   │   ├── auth/
│   │   ├── projects/
│   │   ├── scenes/
│   │   ├── timeline/
│   │   ├── ai/
│   │   ├── image/
│   │   ├── voice/
│   │   ├── video/
│   │   ├── storage/
│   │   └── youtube/
│
│   ├── repositories/
│   │
│   ├── workers/
│   │   ├── celery_app.py
│   │   ├── ai_tasks.py
│   │   ├── render_tasks.py
│   │   └── media_tasks.py
│
│   ├── core/
│   │   ├── config.py
│   │   ├── security.py
│   │   ├── logging.py
│   │   └── exceptions.py
│
│   ├── database/
│   │   ├── session.py
│   │   ├── base.py
│   │   └── init_db.py
│
│   └── utils/
│
├── alembic/
├── tests/
├── requirements.txt
└── .env.example
```

---

# 10. AUTHENTICATION

Implement:

```text
POST /api/auth/register
POST /api/auth/login
POST /api/auth/refresh
POST /api/auth/logout
GET  /api/auth/me
POST /api/auth/forgot-password
POST /api/auth/reset-password
```

Features:

- password hashing
- JWT access token
- refresh token
- token expiration
- protected routes
- role authorization
- logout
- user ownership validation

Roles:

```text
USER
ADMIN
```

---

# 11. USER DATABASE

Create:

```text
users
```

Fields:

```text
id
name
email
password_hash
avatar_url
role
credits
is_active
created_at
updated_at
```

Email must be unique.

Passwords must never be stored as plain text.

---

# 12. PROJECT DATABASE

Create:

```text
projects
```

Fields:

```text
id
user_id
title
description
genre
visual_style
language
aspect_ratio
resolution
duration
status
thumbnail_url
created_at
updated_at
```

Aspect ratios:

```text
16:9
9:16
1:1
4:5
```

Resolution:

```text
720p
1080p
4K
```

---

# 13. CHARACTERS

Create:

```text
characters
```

Fields:

```text
id
project_id
name
age
gender
personality
appearance
clothing
colors
visual_style
reference_image_url
created_at
updated_at
```

Features:

```text
Create
Edit
Delete
Generate
Upload reference
Regenerate
Save
```

---

# 14. LOCATIONS

Create:

```text
locations
```

Fields:

```text
id
project_id
name
description
visual_style
lighting
weather
reference_image_url
created_at
updated_at
```

---

# 15. SCENES

Create:

```text
scenes
```

Fields:

```text
id
project_id
scene_number
title
description
narration
dialogue
duration
camera
motion
transition
emotion
visual_prompt
image_url
video_url
created_at
updated_at
```

Scene relationships:

```text
Scene
 ├── Characters
 └── Location
```

---

# 16. ASSET SYSTEM

Create:

```text
assets
```

Types:

```text
IMAGE
VIDEO
AUDIO
MUSIC
SFX
FONT
THUMBNAIL
```

Store:

```text
id
project_id
type
file_name
file_url
mime_type
file_size
metadata
created_at
```

Large media files must NOT be stored in PostgreSQL.

---

# 17. AI PROVIDER ARCHITECTURE

Create interfaces/classes:

```python
class LLMProvider:
    async def generate_script(...):
        ...


class ImageProvider:
    async def generate_image(...):
        ...


class VoiceProvider:
    async def generate_voice(...):
        ...


class VideoProvider:
    async def generate_video(...):
        ...
```

Provider implementations should be replaceable.

Example:

```text
AIProvider
│
├── LLMProvider
│   ├── OpenAIProvider
│   └── LocalLLMProvider
│
├── ImageProvider
│   ├── ExternalImageProvider
│   └── LocalImageProvider
│
├── VoiceProvider
│   ├── ExternalVoiceProvider
│   └── LocalVoiceProvider
│
└── VideoProvider
    ├── ExternalVideoProvider
    └── LocalVideoProvider
```

Never expose provider API keys to React.

---

# 18. AI MOCK MODE

Support:

```env
AI_MOCK_MODE=true
```

When true:

- no paid AI API calls
- sample script
- placeholder/sample images
- sample audio
- simulated jobs
- simulated render progress

When false:

```env
AI_MOCK_MODE=false
```

use configured AI providers.

The mock implementation must follow the same interfaces as the real implementation.

---

# 19. STORY GENERATION

Endpoint:

```text
POST /api/projects/{project_id}/generate-script
```

Input:

```json
{
  "idea": "A small robot wants to see the stars",
  "duration": 120,
  "genre": "emotional",
  "visual_style": "3D cartoon",
  "language": "English"
}
```

Output:

```json
{
  "title": "",
  "logline": "",
  "summary": "",
  "characters": [],
  "locations": [],
  "scenes": []
}
```

AI output must be:

```text
structured JSON
    ↓
Pydantic validation
    ↓
database
```

Never blindly trust AI output.

---

# 20. SCRIPT SCHEMA

Create structured models:

```text
Script
Character
Location
Scene
Dialogue
Narration
```

Example scene:

```json
{
  "scene_number": 1,
  "title": "The Lonely City",
  "description": "ROBI walks through a futuristic city at night.",
  "characters": ["ROBI"],
  "location": "Futuristic City",
  "duration": 8,
  "camera": "slow tracking shot",
  "motion": "walk forward",
  "emotion": "lonely",
  "narration": "ROBI lived alone in a futuristic city."
}
```

---

# 21. CHARACTER CONSISTENCY

Character consistency is a core feature.

Every scene image prompt should combine:

```text
Scene Description
+
Character Description
+
Character Reference
+
Location Description
+
Visual Style
+
Lighting
+
Camera
+
Emotion
```

Create:

```python
build_scene_prompt()
```

The prompt builder should preserve:

```text
face
body proportions
clothing
colors
age
character identity
visual style
```

---

# 22. IMAGE GENERATION

Endpoint:

```text
POST /api/scenes/{scene_id}/generate-image
```

Process:

```text
Scene
 ↓
Character data
 ↓
Location data
 ↓
Prompt Builder
 ↓
Image Provider
 ↓
Object Storage
 ↓
Asset Database
 ↓
Scene.image_url
```

Generation must be asynchronous.

---

# 23. JOB SYSTEM

Create jobs:

```text
jobs
```

Fields:

```text
id
project_id
user_id
type
status
progress
message
error
result
created_at
started_at
completed_at
```

Job states:

```text
QUEUED
PROCESSING
COMPLETED
FAILED
CANCELLED
```

Job types:

```text
SCRIPT
STORYBOARD
IMAGE
VOICE
MUSIC
SFX
SUBTITLE
THUMBNAIL
VIDEO
RENDER
SHORT
```

---

# 24. REDIS + CELERY

Use:

```text
FastAPI
 ↓
Celery
 ↓
Redis
 ↓
Worker
```

Long-running operations must NOT block FastAPI requests.

Use background jobs for:

```text
AI generation
image generation
voice generation
video generation
rendering
thumbnail generation
short generation
```

---

# 25. STORYBOARD

Create:

```text
/projects/:id/storyboard
```

Display scene cards.

Each card:

```text
Scene Number
Image
Title
Description
Duration
Camera
Motion
Narration
Dialogue
Characters
Location
```

Actions:

```text
Edit
Regenerate
Duplicate
Delete
Move Up
Move Down
```

Support drag-and-drop ordering.

---

# 26. TIMELINE

Create a professional editor.

Tracks:

```text
VIDEO
VOICE
MUSIC
SFX
SUBTITLES
```

Timeline item:

```text
id
track_id
asset_id
start_time
duration
trim_start
trim_end
volume
position
scale
rotation
effects
transition
```

Support:

```text
Drag
Resize
Trim
Split
Delete
Duplicate
Reorder
```

---

# 27. EDITOR UI

Use:

```text
┌──────────────────────────────────────────────────────┐
│ Animora AI     Project Name       Preview   Export   │
├────────────┬──────────────────────────┬──────────────┤
│            │                          │              │
│ Scenes     │                          │ Properties   │
│ Characters │       VIDEO PLAYER       │              │
│ Locations  │                          │ Duration     │
│ Assets     │                          │ Camera       │
│ Audio      │                          │ Motion       │
│            │                          │ Voice        │
├────────────┴──────────────────────────┴──────────────┤
│                      TIMELINE                         │
│                                                      │
│ VIDEO       █████████████████████████                 │
│ VOICE       █████████████████████████                 │
│ MUSIC       █████████████████████████                 │
│ SFX         ███████       ███████                     │
│ SUBTITLES   █████████████████████████                 │
└──────────────────────────────────────────────────────┘
```

---

# 28. AUDIO

Voice:

```text
POST /api/projects/{id}/generate-voice
```

Support:

```text
Narrator
Character voices
Voice selection
Speed
Pitch
Volume
```

Music:

```text
POST /api/projects/{id}/generate-music
```

Support:

```text
Upload
Generated music
Volume
Fade in
Fade out
```

SFX:

```text
door
footsteps
rain
wind
city
magic
robot
whoosh
explosion
```

---

# 29. SUBTITLES

Generate subtitle entries:

```json
{
  "start": 0,
  "end": 3.5,
  "text": "ROBI lived alone in a futuristic city."
}
```

Support:

```text
English
Hindi
Hinglish
Spanish
French
German
```

Customization:

```text
Font
Size
Position
Animation
Background
Color
```

---

# 30. REMOTION

Use Remotion for video composition and preview.

Create reusable animation effects:

```text
Zoom In
Zoom Out
Pan Left
Pan Right
Pan Up
Pan Down
Fade
Slide
Parallax
Ken Burns
Camera Shake
```

Scene configuration:

```json
{
  "duration": 8,
  "camera": "zoom_in",
  "transition": "fade",
  "motion": "slow"
}
```

Create reusable Remotion components rather than one huge composition.

---

# 31. VIDEO PREVIEW

Use Remotion Player.

Support:

```text
Play
Pause
Seek
Volume
Fullscreen
```

Preview must reflect timeline changes.

---

# 32. RENDER PIPELINE

Endpoint:

```text
POST /api/projects/{project_id}/render
```

Pipeline:

```text
Project
 ↓
Timeline
 ↓
Scenes
 ↓
Images
 ↓
Voice
 ↓
Music
 ↓
SFX
 ↓
Subtitles
 ↓
Remotion
 ↓
FFmpeg
 ↓
MP4
 ↓
Object Storage
```

Show progress:

```text
Preparing assets ✓
Generating scene ✓
Generating audio ✓
Rendering video ●
Encoding ○
Uploading ○
Complete ○
```

Final response:

```text
Render completed

[Preview]

[Download MP4]
```

---

# 33. YOUTUBE OPTIMIZATION

Endpoint:

```text
POST /api/projects/{id}/generate-youtube-metadata
```

Generate:

```text
title
description
tags
hashtags
short_description
thumbnail_prompt
```

Example:

```text
Title:
The Little Robot Who Wanted to Touch the Stars

Tags:
robot story
AI animation
emotional animation
animated story
```

---

# 34. THUMBNAIL GENERATOR

Endpoint:

```text
POST /api/projects/{id}/generate-thumbnail
```

Use:

```text
main character
important scene
emotion
strong composition
clear focal point
```

Features:

```text
Generate
Regenerate
Upload
Save
Download
```

---

# 35. SHORTS GENERATOR

Endpoint:

```text
POST /api/projects/{id}/generate-short
```

Workflow:

```text
Full Video
 ↓
Analyze Scenes
 ↓
Find interesting segment
 ↓
Create 9:16 composition
 ↓
Add captions
 ↓
Generate short metadata
 ↓
Render
```

Output:

```text
short_video_url
title
description
hashtags
```

---

# 36. DASHBOARD

Create modern SaaS dashboard.

Header:

```text
Welcome back, Rahul 👋
```

Primary CTA:

```text
+ Create New Video
```

Statistics:

```text
Videos Created
Projects
AI Credits
Rendering Jobs
```

Recent projects:

```text
Project thumbnail
Project title
Status
Duration
Updated date
```

Sidebar:

```text
Dashboard
Projects
Characters
Locations
Assets
Templates
Voice
Music
AI Tools
Billing
Settings
```

Admin users additionally see:

```text
Admin
```

---

# 37. CREATE PROJECT SCREEN

Fields:

```text
Project Name
Story / Idea
Genre
Duration
Visual Style
Aspect Ratio
Resolution
Language
Voice
```

Genres:

```text
Animation
Kids
Education
Comedy
Horror
Fantasy
Sci-Fi
Motivational
Storytelling
Documentary
Explainer
```

Visual style options should be generic descriptions and must not intentionally reproduce copyrighted characters or protected living-artist styles.

---

# 38. UI DESIGN

Design language:

```text
Modern
Professional
Minimal
AI SaaS
Creative
```

Support:

```text
Dark Mode
Light Mode
Responsive layout
Smooth animations
Skeleton loading
Toast notifications
Dialogs
Tooltips
Empty states
Error states
Progress states
```

Avoid:

```text
excessive gradients
excessive glassmorphism
generic AI template appearance
```

Use consistent:

```text
spacing
typography
border radius
shadows
icons
button styles
form styles
```

---

# 39. RESPONSIVE DESIGN

Support:

```text
Desktop
Laptop
Tablet
Mobile
```

The timeline/editor can prioritize desktop.

Dashboard, authentication, project pages and settings must be fully responsive.

---

# 40. API LIST

Implement:

```text
POST   /api/auth/register
POST   /api/auth/login
POST   /api/auth/refresh
POST   /api/auth/logout
GET    /api/auth/me

GET    /api/projects
POST   /api/projects
GET    /api/projects/{id}
PUT    /api/projects/{id}
DELETE /api/projects/{id}

POST   /api/projects/{id}/generate-script
POST   /api/projects/{id}/generate-storyboard

GET    /api/projects/{id}/characters
POST   /api/projects/{id}/characters

PUT    /api/characters/{id}
DELETE /api/characters/{id}
POST   /api/characters/{id}/generate-image

GET    /api/projects/{id}/locations
POST   /api/projects/{id}/locations

PUT    /api/locations/{id}
DELETE /api/locations/{id}

GET    /api/projects/{id}/scenes
POST   /api/projects/{id}/scenes

PUT    /api/scenes/{id}
DELETE /api/scenes/{id}

POST   /api/scenes/{id}/generate-image
POST   /api/scenes/{id}/animate

GET    /api/projects/{id}/timeline
PUT    /api/projects/{id}/timeline

POST   /api/projects/{id}/generate-voice
POST   /api/projects/{id}/generate-music
POST   /api/projects/{id}/generate-subtitles

GET    /api/projects/{id}/assets
POST   /api/projects/{id}/assets

POST   /api/projects/{id}/generate-thumbnail
POST   /api/projects/{id}/generate-youtube-metadata
POST   /api/projects/{id}/generate-short

POST   /api/projects/{id}/render
GET    /api/renders/{id}

GET    /api/jobs/{id}

GET    /api/projects/{id}/download
```

---

# 41. API RESPONSE FORMAT

Use consistent responses.

Success:

```json
{
  "success": true,
  "data": {},
  "message": "Project created successfully"
}
```

Error:

```json
{
  "success": false,
  "message": "Unable to generate scene",
  "code": "AI_GENERATION_FAILED"
}
```

Never expose:

```text
stack traces
API keys
database credentials
internal provider errors
```

---

# 42. SECURITY

Implement:

```text
JWT
Password hashing
CORS
Validation
Rate limiting
Upload validation
Upload size limits
Authorization
Ownership checks
Environment variables
SQL injection protection
XSS-safe rendering
```

Every project endpoint must verify:

```text
current_user owns project
```

Admin endpoints must verify:

```text
current_user.role == ADMIN
```

---

# 43. CREDIT SYSTEM

Create configurable credit costs.

Example:

```text
Script = 2
Image = 5
Voice = 5
Animation = 10
Render = 20
Thumbnail = 3
Short = 10
```

Plans:

```text
Free
Creator
Pro
```

Example credits:

```text
Free = 100
Creator = 1000
Pro = 5000
```

IMPORTANT:

Credit costs must be backend configuration.

Do not hard-code business rules in React.

---

# 44. CREDIT TRANSACTION MODEL

Create:

```text
credit_transactions
```

Fields:

```text
id
user_id
amount
operation
reference_id
balance_after
created_at
```

Support:

```text
CREDIT
DEBIT
REFUND
```

When an AI job fails permanently, support credit refund where appropriate.

---

# 45. ADMIN DASHBOARD

Create:

```text
/admin
```

Admin statistics:

```text
Total Users
Active Users
Projects
Videos
AI Jobs
Failed Jobs
Storage
Credits Used
```

Pages:

```text
Users
Projects
Jobs
Usage
Credits
Renders
System
```

Add failed-job retry.

---

# 46. FILE UPLOADS

Validate:

```text
MIME type
extension
file size
ownership
```

Allowed examples:

```text
PNG
JPG
WEBP
MP3
WAV
MP4
MOV
```

Generate safe storage names.

Never trust user-provided file names.

---

# 47. DATABASE RELATIONSHIPS

Use proper relationships:

```text
User
 └── Projects
      ├── Characters
      ├── Locations
      ├── Scenes
      │    ├── SceneCharacters
      │    └── Location
      ├── Assets
      ├── TimelineTracks
      │    └── TimelineItems
      ├── Jobs
      └── Renders
```

Use foreign keys.

Use indexes for frequently queried fields.

---

# 48. PAGINATION

Implement pagination for:

```text
Projects
Assets
Jobs
Users
Renders
```

Example:

```text
GET /api/projects?page=1&page_size=20
```

Response:

```json
{
  "items": [],
  "page": 1,
  "page_size": 20,
  "total": 100,
  "total_pages": 5
}
```

---

# 49. FRONTEND STATE MANAGEMENT

Use Redux Toolkit for:

```text
authentication
theme
editor state
timeline state
user
credits
```

Use RTK Query or TanStack Query for server state.

Do not put every API response manually into Redux if the server-state library handles it better.

---

# 50. API CLIENT

Create:

```text
services/api/
```

Implement:

```text
axios instance
request interceptors
response interceptors
authentication handling
error normalization
```

Base URL:

```env
VITE_API_URL=
```

Never put AI provider secrets in frontend environment variables.

---

# 51. FORM VALIDATION

Use:

```text
React Hook Form
Zod
```

Validate:

```text
register
login
project creation
character creation
location creation
scene editing
settings
```

Show field-level errors.

---

# 52. ERROR HANDLING

Frontend must support:

```text
loading
success
empty
error
retry
```

Example:

```text
Unable to generate image.

The AI service is temporarily unavailable.

[Retry]
```

Do not show technical stack traces.

---

# 53. AI RETRY SYSTEM

Temporary AI failures should support retry.

Example:

```text
Attempt 1
 ↓
Failure
 ↓
Wait
 ↓
Attempt 2
 ↓
Failure
 ↓
Attempt 3
 ↓
FAILED
```

Use exponential backoff where appropriate.

Avoid infinite retries.

---

# 54. OBSERVABILITY

Add structured logging.

Log:

```text
request_id
user_id
job_id
project_id
operation
duration
status
error_code
```

Never log:

```text
password
JWT secrets
API keys
private credentials
```

---

# 55. TESTING

Frontend:

```text
Vitest
React Testing Library
```

Backend:

```text
Pytest
```

Test:

```text
Registration
Login
JWT
Authorization
Project CRUD
Character CRUD
Location CRUD
Scene CRUD
AI schema validation
Job creation
Job status
Timeline
Credits
Render permissions
Admin permissions
```

Add integration tests for important API workflows.

---

# 56. SAMPLE DEMO DATA

Create demo project:

# ROBI AND THE STARS

Story:

```text
A small blue-and-white robot lives alone in a futuristic city.
Every night he looks at the stars and dreams of exploring space.
One night he discovers a mysterious signal coming from the sky.
```

Character:

```text
ROBI

Small blue-and-white robot.

Personality:
Curious
Friendly
Emotional

Appearance:
Small body
Round head
Glowing eyes
Blue-white body
```

Locations:

```text
Futuristic City
Rooftop
Robot Workshop
Night Sky
```

Scenes:

```text
1. ROBI walks through the futuristic city.

2. ROBI climbs to a rooftop.

3. ROBI looks at the stars.

4. A mysterious light appears.

5. ROBI discovers a signal.

6. ROBI builds a communication device.

7. The signal responds.

8. ROBI smiles.

9. A spaceship appears in the sky.

10. ROBI begins his journey.
```

---

# 57. SEED SYSTEM

Create:

```text
scripts/seed.py
```

The seed should create:

```text
demo user
demo project
characters
locations
scenes
sample timeline
```

Do not seed production passwords or secrets.

For development, clearly document demo credentials through environment variables or a safe local-only mechanism.

---

# 58. DOCKER

Create:

```text
Dockerfile.frontend
Dockerfile.backend
Dockerfile.worker
docker-compose.yml
```

Docker Compose services:

```text
frontend
backend
worker
postgres
redis
```

Example architecture:

```text
frontend:5173
backend:8000
postgres:5432
redis:6379
```

Do not expose unnecessary internal services publicly in production.

---

# 59. ENVIRONMENT VARIABLES

Create:

```env
DATABASE_URL=
REDIS_URL=

JWT_SECRET=
JWT_REFRESH_SECRET=

AI_MOCK_MODE=true

LLM_API_KEY=
IMAGE_API_KEY=
VOICE_API_KEY=
VIDEO_API_KEY=

S3_ENDPOINT=
S3_ACCESS_KEY=
S3_SECRET_KEY=
S3_BUCKET=

FRONTEND_URL=
BACKEND_URL=
```

Use:

```text
.env
```

locally.

Commit only:

```text
.env.example
```

Never commit:

```text
.env
```

---

# 60. DOCUMENTATION

Create:

```text
README.md
ARCHITECTURE.md
API.md
DATABASE.md
AI_PIPELINE.md
TIMELINE.md
RENDERING.md
DEPLOYMENT.md
SECURITY.md
CONTRIBUTING.md
```

Documentation should explain:

```text
Architecture
Installation
Environment variables
Database setup
Redis
Workers
AI providers
Mock mode
API
Rendering
Docker
Testing
Deployment
Troubleshooting
```

---

# 61. README

README should contain:

```text
Project Overview
Features
Screenshots
Architecture
Tech Stack
Project Structure
Installation
Environment Variables
Database Setup
Redis Setup
Running Frontend
Running Backend
Running Worker
Docker
Testing
AI Provider Setup
Rendering
Deployment
Troubleshooting
Future Improvements
```

---

# 62. DEVELOPMENT PHASES

Build the project in this exact order.

## PHASE 1

Project architecture.

Create:

```text
frontend
backend
worker
docker
docs
```

---

## PHASE 2

Frontend foundation.

Implement:

```text
React
TypeScript
Vite
Tailwind
Router
Redux
Axios
Lucide
Framer Motion
```

Build:

```text
Login
Register
Dashboard
Projects
Sidebar
Header
Theme
Create Project
Editor shell
```

Use mock data.

---

## PHASE 3

Python foundation.

Before complex backend code, establish:

```text
Python
functions
classes
async/await
JSON
exceptions
modules
environment variables
```

---

## PHASE 4

FastAPI foundation.

Implement:

```text
FastAPI app
routers
schemas
services
dependencies
middleware
health check
error handling
logging
```

---

## PHASE 5

Database.

Implement:

```text
PostgreSQL
SQLAlchemy
Alembic
models
relationships
migrations
```

---

## PHASE 6

Authentication.

Implement:

```text
register
login
refresh
logout
me
password hashing
JWT
protected routes
RBAC
```

---

## PHASE 7

Project CRUD.

Implement:

```text
create
read
update
delete
pagination
search
ownership
```

Connect frontend to backend.

---

## PHASE 8

Character + Location system.

Implement:

```text
CRUD
reference images
generation-ready schema
```

---

## PHASE 9

AI Script Generator.

Implement:

```text
LLM abstraction
structured output
Pydantic validation
script generation
character extraction
location extraction
scene extraction
```

---

## PHASE 10

Storyboard.

Implement:

```text
scene cards
scene editing
scene ordering
drag/drop
regeneration
```

---

## PHASE 11

Image generation.

Implement:

```text
ImageProvider
prompt builder
character consistency
reference image
background job
storage
```

---

## PHASE 12

Redis + Celery.

Implement:

```text
job creation
worker
progress
retry
failure
completion
```

---

## PHASE 13

Voice.

Implement:

```text
VoiceProvider
narration
voice selection
audio storage
timeline integration
```

---

## PHASE 14

Music + SFX.

Implement:

```text
upload
library
generated music
sound effects
volume
fade
timing
```

---

## PHASE 15

Subtitles.

Implement:

```text
subtitle generation
timing
styling
timeline integration
```

---

## PHASE 16

Timeline editor.

Implement:

```text
tracks
items
drag
resize
trim
split
duplicate
delete
preview synchronization
```

---

## PHASE 17

Remotion.

Implement:

```text
scene composition
camera effects
transitions
text
subtitles
audio
```

---

## PHASE 18

FFmpeg rendering.

Implement:

```text
render job
Remotion rendering
FFmpeg processing
encoding
progress
storage
download
```

---

## PHASE 19

YouTube AI.

Implement:

```text
title
description
tags
hashtags
thumbnail
```

---

## PHASE 20

Shorts.

Implement:

```text
9:16
segment selection
captions
short metadata
render
```

---

## PHASE 21

Credits.

Implement:

```text
credit balance
transactions
AI operation costs
refunds
plans
```

---

## PHASE 22

Admin.

Implement:

```text
users
projects
jobs
renders
usage
credits
failed job retry
```

---

## PHASE 23

Testing.

Implement:

```text
unit tests
integration tests
frontend tests
backend tests
permission tests
AI schema tests
```

---

## PHASE 24

Security review.

Check:

```text
JWT
authorization
ownership
uploads
rate limits
CORS
secrets
SQL injection
XSS
logging
```

---

## PHASE 25

Docker + deployment.

Implement:

```text
Dockerfiles
docker-compose
production config
health checks
worker deployment
database migration
```

---

# 63. FINAL PROJECT STRUCTURE

Expected final structure:

```text
animora-ai/
│
├── frontend/
│   ├── src/
│   ├── public/
│   ├── package.json
│   └── ...
│
├── backend/
│   ├── app/
│   ├── alembic/
│   ├── tests/
│   ├── requirements.txt
│   └── ...
│
├── worker/
│
├── docker/
│
├── docs/
│
├── scripts/
│
├── tests/
│
├── .env.example
├── .gitignore
├── docker-compose.yml
├── Makefile
└── README.md
```

---

# 64. CODE QUALITY RULES

Always:

- use clean naming
- use TypeScript types
- use Pydantic models
- use SQLAlchemy models
- use migrations
- separate routes/services/repositories
- create reusable React components
- keep API calls centralized
- handle loading states
- handle errors
- handle empty states
- use environment variables
- write tests
- write documentation

Never:

- create giant files
- duplicate business logic
- expose secrets
- hard-code AI responses
- hard-code production credentials
- store videos in PostgreSQL
- put business logic in React components
- put business logic directly in FastAPI routes
- use `any` unnecessarily
- silently swallow exceptions
- create fake production APIs

---

# 65. PORTFOLIO REQUIREMENTS

This project should be strong enough to demonstrate:

```text
React.js
TypeScript
Redux Toolkit
REST APIs
Python
FastAPI
Pydantic
PostgreSQL
SQLAlchemy
Alembic
JWT
Redis
Celery
AI integration
Prompt engineering
Structured AI output
Object storage
Remotion
FFmpeg
Docker
Testing
System architecture
```

The project should be explainable in a technical interview.

---

# 66. INTERVIEW ARCHITECTURE QUESTIONS TO PREPARE

The implementation should make it possible to explain:

### Frontend

```text
Why React?
Why TypeScript?
Why Redux Toolkit?
Redux vs Context?
How does the timeline state work?
How do you prevent unnecessary re-renders?
How does Remotion preview work?
```

### Backend

```text
Why FastAPI?
Why Pydantic?
How does dependency injection work?
How does JWT authentication work?
How do you handle authorization?
Why background workers?
```

### Database

```text
Why PostgreSQL?
How are scenes related to projects?
How do you model timeline items?
How do you optimize queries?
```

### AI

```text
How does script generation work?
How do you validate AI output?
How do you prevent malformed JSON?
How do you switch AI providers?
How do you maintain character consistency?
```

### Async

```text
Why Redis?
Why Celery?
Why can't image generation run directly in FastAPI?
How does job status work?
How do retries work?
```

### Video

```text
Why Remotion?
Why FFmpeg?
How is a timeline converted into a video?
How do you combine audio and video?
How do you track render progress?
```

### Security

```text
How are API keys protected?
How do users access only their own projects?
How are uploads validated?
How is rate limiting handled?
```

---

# 67. PERFORMANCE

Optimize:

```text
lazy loading
code splitting
image compression
pagination
database indexes
API caching
Redis caching where appropriate
background processing
large media handling
video rendering queues
```

Do not optimize prematurely.

Measure important operations.

---

# 68. PRODUCTION READINESS

Before declaring the project complete, verify:

```text
[ ] Authentication works
[ ] Authorization works
[ ] Project CRUD works
[ ] Character CRUD works
[ ] Location CRUD works
[ ] Scene CRUD works
[ ] AI script generation works
[ ] AI output validation works
[ ] Image generation works
[ ] Background jobs work
[ ] Voice generation works
[ ] Subtitles work
[ ] Timeline works
[ ] Remotion preview works
[ ] FFmpeg rendering works
[ ] MP4 export works
[ ] YouTube metadata works
[ ] Thumbnail generation works
[ ] Shorts work
[ ] Credits work
[ ] Admin works
[ ] Tests pass
[ ] Docker works
[ ] Documentation is complete
```

---

# 69. DEMO MODE

The complete project must remain usable without paid AI services.

When:

```env
AI_MOCK_MODE=true
```

the user must still be able to demonstrate:

```text
Create project
Generate script
Generate characters
Generate scenes
Generate storyboard
Generate images
Generate voice
Generate subtitles
Edit timeline
Preview
Render simulation
Download demo video
```

This is important for development and portfolio demonstrations.

---

# 70. FUTURE AI MODEL STRATEGY

Do NOT require training an LLM, image model, voice model, and video model from scratch.

Design the application so that later we can use:

```text
External AI APIs
        OR
Open-source models
        OR
Self-hosted models
        OR
Fine-tuned models
```

without rewriting the entire application.

The provider abstraction is mandatory.

---

# 71. FINAL SUCCESS CRITERIA

The final application should provide this complete experience:

```text
USER
 ↓
Create Account
 ↓
Dashboard
 ↓
Create Project
 ↓
Enter Story
 ↓
Generate Script
 ↓
Review Script
 ↓
Characters
 ↓
Locations
 ↓
Storyboard
 ↓
Generate Images
 ↓
Generate Voice
 ↓
Add Music
 ↓
Add SFX
 ↓
Generate Captions
 ↓
Timeline Editor
 ↓
Preview
 ↓
Render
 ↓
MP4
 ↓
YouTube Metadata
 ↓
Thumbnail
 ↓
Shorts
```

The application should feel like a real commercial AI creative SaaS rather than a college demo.

---

# 72. DEVELOPMENT RESPONSE FORMAT

For every step, respond using:

## 1. What we are building

Explain the current feature in simple language.

## 2. Architecture

Show how the feature connects:

```text
Frontend
 ↓
FastAPI
 ↓
Service
 ↓
Database/Worker/AI
```

## 3. Files

List:

```text
CREATE
UPDATE
DELETE
```

## 4. Complete code

For every required file, provide complete code.

Never use:

```text
// implementation here
// add code
// TODO
```

unless it is an actual documented future task and the current feature can work without it.

## 5. Installation

Give exact commands.

## 6. Run

Give exact commands for:

```text
Frontend
Backend
Worker
Redis
PostgreSQL
```

## 7. Testing

Explain exactly how to test the current feature.

## 8. Common errors

Give likely errors and fixes.

## 9. Completion checklist

Show:

```text
✓ Feature
✓ API
✓ Database
✓ UI
✓ Validation
✓ Error handling
✓ Testing
```

Then STOP.

Wait for:

```text
NEXT
```

---

# 73. FIRST COMMAND

START NOW.

Implement:

# STEP 1 — PROJECT ARCHITECTURE + FRONTEND FOUNDATION

Create:

```text
animora-ai/
├── frontend/
├── backend/
├── worker/
├── docker/
├── docs/
├── scripts/
├── .gitignore
├── .env.example
├── docker-compose.yml
├── Makefile
└── README.md
```

Then initialize:

```text
React
TypeScript
Vite
Tailwind CSS
React Router
Redux Toolkit
Axios
Lucide React
Framer Motion
```

Build the initial production-quality frontend:

```text
Login
Register
Dashboard
Projects
Create Project
Project Editor Shell
Sidebar
Header
Theme Switcher
Responsive Layout
```

Use mock data.

Do NOT connect AI yet.

Do NOT implement database yet.

Do NOT implement real authentication yet.

Create a clean foundation that future phases can extend without rewriting the architecture.

After STEP 1 is complete:

STOP.

Wait for:

```text
NEXT
```

When the user says `NEXT`, continue with STEP 2.

Do not restart the project.

Do not remove working features.

Do not change architecture without explaining the technical reason.

# END OF MASTER PROMPT
