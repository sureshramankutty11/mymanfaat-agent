# MyManfaat Agent

**MyManfaat Agent** is an AI-powered benefit navigator that helps Malaysians discover aid, grants, training programmes, and support schemes they may be eligible for.

## Tagline

Making public support easier to find, understand, and apply for.

## Problem

Many Malaysians miss useful aid, grants, training, and support programmes because the information is scattered, formal, and difficult to understand.

## Solution

MyManfaat Agent asks users simple eligibility questions, matches their profile against a benefit programme database, recommends suitable programmes, explains why each programme fits, and generates a document checklist plus application action plan.

## Features

- Eligibility questionnaire
- Benefit recommendation engine
- Programme match scoring
- Plain-language recommendation explanations
- Document checklist
- Step-by-step action plan
- Responsive web interface

## Current Prototype

This hackathon prototype uses:

- React
- Vite
- CSS
- Sample benefit programme database
- Rule-based recommendation scoring

## Planned Full Version

The full version can integrate:

- Google Gemini API for natural-language explanation and reasoning
- Google Cloud Agent Builder for agent workflow orchestration
- MongoDB for benefit programme records and eligibility rules
- Vercel, Firebase Hosting, or Google Cloud Run for deployment

## Partner Track Fit

Recommended partner track: **MongoDB**

MongoDB can store:

- Benefit programme records
- Eligibility requirements
- User profile inputs
- Recommendation history
- Checklist templates

## Demo User Journey

Example profile:

- Age: 50
- State: Selangor
- Employment status: Employee
- Income: M40
- Main need: Training / Reskilling
- User profile: Employee

The agent recommends:

1. Reskilling for Mid-Career Workers
2. Digital Skills Training Grant
3. Other relevant support programmes based on profile

It then generates:

- Programme match score
- Reason for recommendation
- Required document checklist
- Application action plan

## Run Locally

```bash
npm install
npm run dev
```

Then open the local URL shown in your terminal.

## Build

```bash
npm run build
```

## Prototype Disclaimer

This demo uses sample benefit data for hackathon demonstration only. A production version should connect to verified and official programme sources.

## License

MIT


## Design Theme

The prototype uses a striking blue visual direction to feel modern, trusted, and suitable for a public-service AI assistant.
