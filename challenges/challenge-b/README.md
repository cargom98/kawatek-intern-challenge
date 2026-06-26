# Challenge B: AI Programming & UX

## Context

At Kawatek, we develop **ACTIVAI** — an AI-powered rehabilitation platform that helps patients train their neuromuscular control after receiving a bionic prosthetic. The platform displays real-time metrics, therapeutic exercises, and progress tracking.

## The Problem

You are tasked with building a **Rehabilitation Dashboard Prototype** — a web application that visualizes patient rehabilitation data and provides an intuitive interface for tracking progress.

## Requirements

Build a single-page web application that:

1. **Displays patient session data** from the provided JSON file
2. **Visualizes rehabilitation metrics** with interactive charts
3. **Implements an AI-powered recommendation** feature (can be simulated/rule-based)
4. **Provides a clean, accessible UX** suitable for clinical use

## Provided Files

```
challenge-b/
├── README.md              (this file)
├── data/
│   └── patient_sessions.json   (sample rehabilitation session data)
├── src/
│   └── placeholder.html        (start here)
├── design/
│   └── wireframe.png           (basic layout reference)
└── SOLUTION.md                 (write your explanation here)
```

## The Data

`patient_sessions.json` contains rehabilitation session records:

```json
{
  "patient_id": "RYO-2027-001",
  "sessions": [
    {
      "date": "2027-07-10",
      "duration_minutes": 30,
      "exercises": [
        {
          "name": "Power Grip Training",
          "repetitions": 15,
          "accuracy_percent": 72,
          "avg_response_time_ms": 340,
          "fatigue_index": 0.3
        }
      ],
      "emg_quality_score": 0.85,
      "overall_progress_percent": 45
    }
  ]
}
```

## Tasks

### Task 1: Data Display (Required)
- Load and display patient session history
- Show a summary card with: total sessions, average accuracy, current progress
- List individual sessions with expandable details

### Task 2: Data Visualization (Required)
- **Progress over time** — line chart showing accuracy improvement across sessions
- **Exercise breakdown** — bar chart comparing performance across exercise types
- **Fatigue analysis** — visualization of fatigue index trends within and across sessions

### Task 3: AI Recommendations (Required)
- Based on the patient data, generate at least 3 personalized recommendations
- Examples: "Increase power grip repetitions — accuracy above 80% for 3 consecutive sessions"
- Can be rule-based logic (no ML model required, but bonus if you use one)
- Display recommendations in a clear, actionable format

### Task 4: UX & Accessibility (Required)
- Responsive design (works on desktop and tablet)
- Accessible color scheme and font sizes suitable for clinical environments
- Clear data hierarchy — most important metrics visible at a glance

### Task 5: Bonus Features
- **Dark/light mode** toggle
- **Session comparison** — select 2 sessions to compare side by side
- **Export** — generate a PDF or printable summary report
- **Real-time simulation** — animate incoming session data as if live

## Tech Stack

Choose any of the following (or combine):
- **Frontend:** React, Vue, Svelte, or vanilla HTML/CSS/JS
- **Charting:** Chart.js, D3.js, Recharts, or any visualization library
- **Styling:** Tailwind CSS, Material UI, or custom CSS

## Evaluation Focus

- UI/UX design sensibility (clarity, hierarchy, accessibility)
- Data visualization effectiveness
- Code organization and component structure
- Creative problem-solving in the recommendation engine
- Responsiveness and attention to detail

## Hints

- Think about who uses this: therapists and patients. Keep it simple and clinical.
- The recommendation engine doesn't need to be fancy — clear logic with good UX presentation matters more
- Consider loading states, empty states, and error handling
- A working prototype beats a pretty mockup that doesn't function
