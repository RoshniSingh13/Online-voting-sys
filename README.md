# Online Voting System

A lightweight, single-page web application that enables users to cast votes for their preferred candidate and view real-time voting results. Built with vanilla HTML, CSS, and JavaScript for simplicity and accessibility.

---

## Table of Contents

- [Features](#features)
- [Project Structure](#project-structure)
- [Installation](#installation)
- [Usage](#usage)
- [File Descriptions](#file-descriptions)
- [Technical Stack](#technical-stack)
- [How It Works](#how-it-works)
---

## Features

- **Simple Voting Interface** – Clean, intuitive radio button selection for multiple candidates
- **Vote Submission** – Submit votes with real-time confirmation messages
- **Results Display** – View voting results instantly with a single click
- **Responsive Design** – Centered, mobile-friendly layout with consistent styling
- **Client-Side Storage** – Votes persisted in browser memory during session
- **No Dependencies** – Pure HTML, CSS, and JavaScript implementation

---

## Project Structure

```
online-voting-system/
│
├── index.html          # Main HTML markup and structure
├── style.css           # Styling and layout definitions
├── script.js           # JavaScript logic and interactivity
└── README.md           # Project documentation (this file)
```

---

## Installation

### Prerequisites

- Any modern web browser (Chrome, Firefox, Safari, Edge)
- No server or package manager required

### Setup Steps

1. **Clone or Download** the project files:
   ```bash
   git clone <repository-url>
   cd online-voting-system
   ```

2. **Open in Browser**:
   - Double-click `index.html` or
   - Right-click → "Open with" → Select your browser

3. **Start Voting** – No additional configuration needed

---

## Usage

### Casting a Vote

1. Select a candidate by clicking the radio button next to their name
2. Click the **"Submit Vote"** button
3. A success message will appear confirming your vote has been recorded

### Viewing Results

1. Navigate to the **"Results"** section
2. Click the **"View Results"** button
3. Voting statistics for all candidates will display below the button

### Resetting Votes

Refresh the page or clear browser cache to reset voting data (as votes are stored client-side).

---

## File Descriptions

### `index.html`

Core HTML structure containing:
- Semantic container with voting form
- Radio button group for candidate selection
- Submit button for vote registration
- Results section with dynamic display area
- Script references for functionality

**Key Elements:**
- Vote form with unique identifier (`voteForm`)
- Message display area for user feedback (`message`)
- Results list container (`results`)

### `style.css`

Styling definitions including:
- Clean typography with Arial sans-serif font
- Centered container layout (400px width)
- White content boxes with padding and border-radius
- Light gray background (#f2f2f2) for contrast
- Green confirmation message styling
- Responsive button styling with hover states

**Key Classes:**
- `.container` – Main layout wrapper
- `.box` – Content card styling for form and results sections

### `script.js`

JavaScript functionality managing:
- Vote form submission and validation
- Vote counting and aggregation
- Local storage of voting data
- Results retrieval and formatting
- User feedback messaging

**Core Functions:**
- `handleVoteSubmission()` – Processes form submission
- `showResults()` – Displays current voting statistics
- `updateVoteCount()` – Maintains vote tally

---

## Technical Stack

| Layer | Technology |
|-------|-----------|
| **Frontend** | HTML5 |
| **Styling** | CSS3 |
| **Logic** | Vanilla JavaScript (ES6+) |
| **Storage** | Browser localStorage / Memory |
| **Architecture** | Single-Page Application (SPA) |

---

## How It Works

### Vote Flow

```
User Interaction
    ↓
Select Candidate (Radio Button)
    ↓
Submit Vote (Form Submission)
    ↓
Validate Input
    ↓
Record Vote (Client-Side Storage)
    ↓
Display Confirmation Message
    ↓
Update Vote Count
```

### Data Management

- Votes are stored client-side (no backend required)
- Each vote is associated with the selected candidate
- Vote count increments per selection
- Results persist during the current session
- Page refresh resets all data

---

## Code Example

### Basic Form Submission (JavaScript Pattern)

```javascript
document.getElementById('voteForm').addEventListener('submit', function(e) {
    e.preventDefault();
    
    const selectedVote = document.querySelector('input[name="vote"]:checked');
    
    if (selectedVote) {
        recordVote(selectedVote.value);
        document.getElementById('message').textContent = 
            'Your vote has been submitted successfully!';
    }
});
```

---



