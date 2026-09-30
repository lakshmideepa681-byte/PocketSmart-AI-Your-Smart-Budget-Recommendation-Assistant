# PocketSmart AI 💰🤖

> **Your Smart Budget & Recommendation Assistant**

PocketSmart AI is a GenAI-powered budget and recommendation assistant designed to help users plan everyday lifestyle needs within a defined budget. It provides personalized recommendations across **home interiors, party planning, and jewelry selection** by combining user preferences, budget information, contextual requirements, and optional images.

The system uses **FastAPI** as the backend service and integrates **Google Gemini 1.5 Flash Pro** for AI-powered budget interpretation, recommendation generation, and multimodal analysis.

---

## 📌 Table of Contents

- [Overview](#-overview)
- [Key Features](#-key-features)
- [Use Cases](#-use-cases)
- [How It Works](#-how-it-works)
- [Technology Stack](#-technology-stack)
- [System Architecture](#-system-architecture)
- [Project Structure](#-project-structure)
- [Prerequisites](#-prerequisites)
- [Gemini API Setup](#-gemini-api-setup)
- [Environment Configuration](#-environment-configuration)
- [Installation](#-installation)
- [Running the Application](#-running-the-application)
- [Application Modules](#-application-modules)
- [API Routes](#-api-routes)
- [Authentication & Sessions](#-authentication--sessions)
- [Recommendation Workflow](#-recommendation-workflow)
- [Testing & Optimization](#-testing--optimization)
- [Supported Platforms](#-supported-platforms)
- [Security Notes](#-security-notes)
- [Future Enhancements](#-future-enhancements)
- [Conclusion](#-conclusion)

---

## 🌟 Overview

Managing a budget across different lifestyle needs can be difficult because users must compare many products, services, platforms, prices, styles, and requirements.

PocketSmart AI addresses this challenge by providing a centralized AI-powered recommendation experience.

Users can enter their:

- Budget
- Preferences
- Requirements
- Occasion or event details
- Guest count
- Room details
- Optional outfit images

The AI then processes the information and generates personalized recommendations appropriate to the selected planner.

The project covers three primary planning domains:

1. 🏠 **Home Interior Budget Planner**
2. 🎉 **Party Budget Planner**
3. 💎 **Jewelry Budget Planner**

---

## ✨ Key Features

### 🏠 Home Interior Planner

Plan home interiors while staying within a specified budget.

Users can provide:

- Total budget
- Room types
- Required quantities
- Furniture requirements
- Lighting requirements
- Decor requirements
- Other interior preferences

The system generates recommendations for items such as:

- Furniture
- Lighting
- Ceiling fans
- Dining tables
- Decorative items
- Other home-interior products

Recommendations can be sourced or linked to platforms such as Amazon and IKEA.

---

### 🎉 Party Budget Planner

Plan an event according to the available budget and guest requirements.

Users can provide:

- Total budget
- Number of guests
- Event type
- Venue details
- Catering requirements
- Decoration requirements
- Entertainment requirements

The system can organize recommendations across categories such as:

- Food and catering
- Venue
- Decorations
- Entertainment
- Accommodation

The project documentation describes integrations or simulated sourcing from platforms such as Swiggy, Zomato, and OYO.

---

### 💎 Jewelry Budget Planner

Find jewelry recommendations based on:

- Budget
- Occasion
- Style preference
- Outfit
- Optional outfit image

The multimodal Gemini integration can process text and image inputs to help generate style-matched jewelry suggestions.

Potential recommendation sources described in the project include Amazon and Flipkart.

---

## 🔄 How It Works

```text
User
  │
  ▼
Frontend UI
  │
  ├── Budget
  ├── Preferences
  ├── Category
  └── Optional Image
  │
  ▼
FastAPI Backend
  │
  ▼
Planner Route
  │
  ├── Home Planner
  ├── Party Planner
  └── Jewelry Planner
  │
  ▼
Gemini AI Layer
  │
  ├── Budget Interpretation
  ├── Context Understanding
  ├── Recommendation Generation
  └── Image Analysis
  │
  ▼
Recommendation Processing
  │
  ▼
Frontend Results
```

---

## 🛠 Technology Stack

| Technology | Purpose |
|---|---|
| **Python** | Core programming language |
| **FastAPI** | Backend API framework |
| **Google Gemini 1.5 Flash Pro** | AI recommendation and multimodal processing |
| **HTML** | Frontend structure |
| **CSS** | Frontend styling |
| **JavaScript** | Dynamic frontend interactions |
| **Jinja2** | HTML templating |
| **JWT** | Authentication token handling |
| **CORS** | Cross-origin request handling |
| **Uvicorn** | Application server |
| **`.env`** | Environment configuration |
| **Third-party APIs / simulated integrations** | Product and service data sourcing |

---

## 🏗 System Architecture

PocketSmart AI follows a modular architecture consisting of:

### Frontend Layer

The frontend provides interactive forms for:

- Home planning
- Party planning
- Jewelry planning
- User registration
- Login
- Dashboard
- Recommendation history

AI-generated results are displayed using structured, card-style layouts.

### Backend Layer

FastAPI handles:

- Routing
- Request processing
- Authentication
- Sessions
- Planner-specific APIs
- Communication with Gemini
- Recommendation processing

### Gemini AI Layer

Gemini 1.5 Flash Pro is used for:

- Understanding budget context
- Processing user preferences
- Generating recommendations
- Analyzing optional images
- Producing domain-specific suggestions

### Recommendation Layer

The system organizes recommendations according to the selected domain and can connect or simulate sourcing from platforms such as Amazon, Flipkart, IKEA, Swiggy, Zomato, and OYO.

---

## 📁 Project Structure

The project documentation describes a modular backend organization similar to:

```text
PocketSmart-AI/
│
├── main.py
├── gemini_utils.py
├── .env
├── requirements.txt
│
├── routes/
│   └── ...
│
├── services/
│   └── ...
│
├── models/
│   └── ...
│
├── templates/
│   ├── home.html
│   ├── login.html
│   ├── register.html
│   ├── dashboard.html
│   ├── home_planner.html
│   ├── party_planner.html
│   ├── jewelry_planner.html
│   └── ...
│
├── static/
│   ├── css/
│   ├── js/
│   └── images/
│
└── README.md
```

> The exact filenames and directories should match the implementation in the project repository.

---

## ✅ Prerequisites

Before running PocketSmart AI, install or configure:

- Python
- Google Cloud / Gemini API access
- FastAPI
- Uvicorn
- Required Python dependencies
- A valid Gemini API key
- Any required third-party API credentials used by your implementation

The project documentation also identifies Python basics and API configuration as prerequisites.

---

## 🔑 Gemini API Setup

PocketSmart AI requires authenticated access to Gemini.

### Step 1 — Obtain Gemini API Access

Set up the required Google Cloud / Gemini API access and obtain an API key.

### Step 2 — Create an API Key

Create an API key through the appropriate Google AI / Google Cloud interface.

**Important:** Never commit your API key directly into GitHub.

### Step 3 — Store the Key in `.env`

Create a `.env` file in the project root:

```env
GEMINI_API_KEY=your_gemini_api_key_here
```

If your implementation uses a different environment-variable name, use the name expected by your code.

### Step 4 — Load the Environment

The backend should load environment variables during application initialization.

### Step 5 — Validate Connectivity

Run a sample Gemini request to confirm that:

- Authentication works
- Text prompts work
- Image + text requests work where required
- The configured model is accessible

The Jewelry Planner specifically requires multimodal support because it can accept an optional outfit image.

---

## ⚙️ Environment Configuration

A typical `.env` configuration can contain:

```env
GEMINI_API_KEY=your_gemini_api_key_here

# Add other project-specific configuration here
# DATABASE_URL=...
# JWT_SECRET_KEY=...
# THIRD_PARTY_API_KEY=...
```

### `.gitignore`

Make sure sensitive files are excluded:

```gitignore
.env
__pycache__/
*.pyc
.venv/
venv/
.idea/
.vscode/
```

---

## 📦 Installation

### 1. Clone the Repository

```bash
git clone <your-repository-url>
cd PocketSmart-AI
```

### 2. Create a Virtual Environment

Windows:

```bash
python -m venv venv
venv\Scripts\activate
```

macOS / Linux:

```bash
python3 -m venv venv
source venv/bin/activate
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

If a `requirements.txt` file has not yet been created, install the dependencies required by the current implementation and then generate one:

```bash
pip freeze > requirements.txt
```

### 4. Configure Environment Variables

Create `.env` and add the required Gemini API key and other project configuration.

---

## ▶️ Running the Application

The project documentation describes **Uvicorn** as the server used to start the FastAPI application.

A typical development command is:

```bash
uvicorn main:app --reload
```

After starting the server, open the local application URL shown by Uvicorn.

If your project uses a different application entry point, update the command accordingly.

---

# 🧩 Application Modules

## 1. Home Interior Planner

### Endpoint

```text
/generate-home
```

### Purpose

Accepts home-related preferences and budget information and generates tailored home-interior recommendations.

### Example Inputs

```text
Budget: ₹50,000
Room: Living Room
Items:
- Sofa
- Ceiling Fan
- Lights
- Dining Table
Style: Modern
```

### Expected Output

The AI generates structured recommendations based on:

- Budget
- Category
- Quantity
- Style
- Functional requirements

---

## 2. Party Planner

### Endpoint

```text
/generate-party
```

### Purpose

Processes party information and generates recommendations for event planning.

### Example Inputs

```text
Budget: ₹30,000
Guests: 50
Event Type: Birthday
Venue: Chennai
Requirements:
- Food
- Decoration
- Entertainment
```

### Expected Output

The system organizes suggestions for:

- Food
- Venue
- Decoration
- Entertainment
- Related services

---

## 3. Jewelry Planner

### Endpoint

```text
/generate-jewelry
```

### Purpose

Generates jewelry recommendations based on budget, occasion, style, and optional outfit image.

### Example Inputs

```text
Budget: ₹10,000
Occasion: Wedding
Style: Traditional
Outfit Image: Optional
```

### Expected Output

The AI provides recommendations based on:

- Occasion
- Style
- Budget
- Outfit context
- Image analysis when an image is supplied

---

# 🔐 Authentication & Sessions

PocketSmart AI includes user authentication and session-related routes.

### Registration

```text
/register
```

Creates a new user account and securely stores user credentials according to the application implementation.

### Login

```text
/login
```

Authenticates an existing user and starts an authenticated session.

### Logout

```text
/logout
```

Terminates the current user session.

### Token

```text
/token
```

Issues a JWT token after successful authentication for authorized API access.

### Session Information

```text
/session-info
```

Returns information about the current session.

### Session Data

```text
/session-data
```

Returns session-specific data used for personalization and recommendation tracking.

---

# 📡 API Routes

The documented application includes the following major routes:

| Route | Purpose |
|---|---|
| `/generate-home` | Home interior recommendations |
| `/generate-party` | Party planning recommendations |
| `/generate-jewelry` | Jewelry recommendations |
| `/register` | User registration |
| `/login` | User authentication |
| `/logout` | End user session |
| `/token` | JWT token generation |
| `/session-info` | Current session metadata |
| `/session-data` | Session-specific data |
| `/recommendations-details` | Detailed AI recommendations |
| `/history` | Previous recommendation queries/results |
| `/startup` | Application initialization |

---

# 🧠 Recommendation Workflow

The general recommendation process is:

```text
1. User selects a planner
        ↓
2. User enters budget and preferences
        ↓
3. Optional image is uploaded
        ↓
4. FastAPI receives the request
        ↓
5. Planner-specific logic prepares the input
        ↓
6. Gemini processes the request
        ↓
7. AI generates contextual recommendations
        ↓
8. Recommendation data is formatted
        ↓
9. Results are returned to the frontend
        ↓
10. User reviews recommendations
```

The system is designed to keep recommendations aligned with the user's specified budget and context.

---

# 🧪 Testing & Optimization

PocketSmart AI should be tested across realistic scenarios.

## Home Planner Testing

Test different:

- Budgets
- Room types
- Product quantities
- Styles
- Product categories

## Party Planner Testing

Test different:

- Event types
- Guest counts
- Budgets
- Food requirements
- Venue requirements
- Decoration requirements

## Jewelry Planner Testing

Test:

- Different budgets
- Occasions
- Styles
- Outfit images
- Text-only requests

## Optimization

The project documentation identifies the following optimization areas:

- Gemini response quality
- Budget adherence
- Platform accuracy
- Prompt refinement
- Input validation
- Session handling
- UI/UX
- Fallback recommendations when AI results are insufficient

---

# 🛒 Supported Platforms

The project documentation describes recommendation sourcing or integration with platforms including:

- Amazon
- Flipkart
- IKEA
- Swiggy
- Zomato
- OYO

Some integrations may be implemented as mock APIs or simulated data sources depending on the current project implementation.

> Product availability, prices, links, and third-party platform data should be treated as dynamic and should be verified against the respective platform before making a purchase or booking.

---

# 🔒 Security Notes

Never commit sensitive credentials to GitHub.

### Do not commit:

```text
.env
API keys
JWT secrets
Database passwords
Private credentials
```

Use environment variables or an appropriate secret-management solution.

For production deployment, additionally review:

- Authentication security
- Password handling
- JWT configuration
- CORS configuration
- File-upload validation
- API rate limits
- Input validation
- Error handling
- Third-party API credentials
- HTTPS configuration

---

# 📊 User Dashboard & History

The project includes a personalized user dashboard.

The dashboard can display:

- Recent recommendations
- Saved queries
- Personalized information
- Previous recommendation results

The `/history` route is intended to retrieve previous recommendation queries and results for review or reuse.

---

# 🎨 Frontend

The frontend is designed using:

- HTML
- CSS
- JavaScript
- Jinja2 templates

The documented UI includes:

- Home Page
- Register Page
- Login Page
- User Dashboard
- Home Interior Budget Planner
- Home Interior Recommendations
- Party Budget Planner
- Party Budget Recommendations
- Jewelry Budget Planner
- Jewelry Budget Recommendations
- Recommendation History
- Testimonials
- Footer

---

# 🚀 Project Milestones

## Milestone 1 — Gemini AI Initialization

- Configure Gemini API access
- Configure API keys
- Validate authentication
- Test text prompts
- Test multimodal prompts
- Refine recommendation prompts

## Milestone 2 — Core Functionality

- Implement planner modules
- Create backend routing
- Integrate Gemini
- Build recommendation logic
- Add product/service sourcing
- Add authentication

## Milestone 3 — FastAPI Integration

- Define FastAPI routes
- Implement modular architecture
- Configure CORS
- Implement sessions
- Implement structured inputs and outputs
- Connect frontend and AI services

## Milestone 4 — UI Development

- Build responsive frontend
- Create planner forms
- Display AI recommendations
- Implement authentication screens
- Implement dashboard and history

## Milestone 5 — Testing & Optimization

- Test real-world budget scenarios
- Evaluate recommendation quality
- Validate budget adherence
- Improve prompts
- Improve session handling
- Add input validation
- Add fallback recommendations
- Optimize UI/UX

---

# 📌 Important Implementation Note

The project documentation contains references to both **Flask** and **FastAPI** in different sections. The later implementation milestones and route descriptions are centered on **FastAPI**, including `main.py`, Uvicorn, FastAPI routes, and Jinja2 templates.

Therefore, this README describes the primary documented implementation as **FastAPI-based**. The exact framework and file structure should be kept consistent with the code currently present in the repository.

---

# 🔮 Future Enhancements

Possible future improvements based on the project's existing architecture include:

- More recommendation categories
- More real-time product/service integrations
- Improved recommendation ranking
- More detailed budget allocation
- Better product comparison
- Enhanced image-based recommendations
- More personalization
- Improved recommendation history
- Advanced analytics
- Production-grade database integration
- Improved authentication and authorization
- Mobile-responsive enhancements
- Deployment and scalability improvements

---

# 📄 License

Add the project's chosen license here.

Example:

```text
MIT License
```

If a license has not yet been selected, do not publish a license declaration until the project owner chooses one.

---

# 👩‍💻 Project

**Project Name:** PocketSmart AI  
**Description:** Your Smart Budget & Recommendation Assistant  
**Primary AI:** Gemini 1.5 Flash Pro  
**Backend:** FastAPI  
**Frontend:** HTML / CSS / JavaScript / Jinja2  

---

## ⭐ Summary

PocketSmart AI combines generative AI, budget planning, personalization, and web technologies to help users make informed choices across home interiors, party planning, and jewelry selection.

The platform accepts budgets, preferences, contextual information, and optional images, processes them through Gemini, and presents personalized recommendations through a responsive web interface.

It is designed as a practical example of how generative AI can be integrated into everyday budget planning and recommendation workflows.
