# 🤖 AI Lead Follow-up Automation

[![n8n](https://img.shields.io/badge/n8n-automation-ff6d5a?style=for-the-badge)](https://n8n.io)
[![Google Gemini](https://img.shields.io/badge/Google_Gemini-AI-4285F4?style=for-the-badge&logo=google)](https://ai.google.dev)
[![Gmail](https://img.shields.io/badge/Gmail-API-EA4335?style=for-the-badge&logo=gmail)](https://gmail.com)

> **Automatically nurture leads with personalized AI-generated follow-up emails using Google Gemini AI**

## 📋 Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Technologies Used](#technologies-used)
- [How It Works](#how-it-works)
- [Workflow Diagram](#workflow-diagram)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Configuration](#configuration)
- [Usage](#usage)
- [Screenshots](#screenshots)
- [File Structure](#file-structure)
- [Demo](#demo)
- [Future Enhancements](#future-enhancements)
- [License](#license)

---

## 🎯 Overview

This automation workflow eliminates manual follow-up tasks by automatically sending personalized emails to leads using AI. When a lead's status is marked as "Needs Follow-up" in Google Sheets, the system:

1. **Triggers** automatically every minute
2. **Generates** a personalized email using Google Gemini AI
3. **Sends** the email via Gmail
4. **Updates** the spreadsheet with follow-up status

Perfect for sales teams, agencies, and businesses that need to nurture leads efficiently.

---

## ✨ Features

- ✅ **Automated Triggering** - Monitors Google Sheets every minute
- ✅ **AI-Powered Personalization** - Uses Google Gemini 2.5 Flash Lite
- ✅ **Smart Email Generation** - 100-150 word professional emails
- ✅ **Automatic Sending** - Gmail integration for instant delivery
- ✅ **Status Tracking** - Auto-updates sheets with follow-up status
- ✅ **Professional Tone** - Friendly, helpful, and non-pushy
- ✅ **Consultation CTA** - Includes 15-minute call offer
- ✅ **Error Handling** - Graceful failure management

---

## 🛠 Technologies Used

| Technology | Purpose |
|------------|---------|
| **n8n** | Workflow automation platform |
| **Google Gemini AI** | Email content generation |
| **Google Sheets** | Lead data storage & trigger |
| **Gmail API** | Email sending |

---

## 🔄 How It Works

### **Workflow Steps:**

1. **Trigger Node** (Google Sheets)
   - Monitors "Lead Capture Form" every minute
   - Activates when Status = "Needs Follow-up"
   - Captures lead data (name, email, company, requirements)

2. **AI Generation Node** (Google Gemini)
   - Model: `gemini-2.5-flash-lite`
   - Analyzes lead information
   - Generates personalized follow-up email
   - Professional tone, 100-150 words
   - Includes consultation call offer

3. **Email Sending Node** (Gmail)
   - Sends AI-generated email to lead
   - From: Raf Digital Media
   - Includes project-specific details
   - Auto-personalized for each lead

4. **Update Node** (Google Sheets)
   - Updates Status → "Sent"
   - Adds Last Contact Date → Today
   - Tracks follow-up completion

---

## 📊 Workflow Diagram
┌─────────────────────┐
│ Google Sheets │
│ (Trigger) │
└──────────┬──────────┘
│
↓
┌─────────────────────┐
│ Google Gemini AI │
│ (Email Generation) │
└──────────┬──────────┘
│
↓
┌─────────────────────┐
│ Gmail │
│ (Send Email) │
└──────────┬──────────
│
↓
┌─────────────────────┐
│ Google Sheets │
│ (Update Status) │
└─────────────────────┘

---

##  Prerequisites

Before you begin, ensure you have:

- ✅ **n8n account** (Self-hosted or Cloud)
- ✅ **Google account** with:
  - Google Sheets access
  - Gmail API enabled
- ✅ **Google Gemini API key** (Free from [Google AI Studio](https://aistudio.google.com))
- ✅ **Google Sheets** with columns:
  - Full Name
  - Email Address
  - Phone Number
  - Company Name
  - Message/Requirements
  - Status
  - Last Contact Date
  - Follow-up Status

---

## 🚀 Installation

### **Step 1: Clone or Download**

```bash
# Clone this repository
git clone https://github.com/rafdigitalmedia/n8n-ai-lead-followup-automation.git
cd n8n-ai-lead-followup-automation
