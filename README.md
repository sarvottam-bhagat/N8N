# Expense Tracker - n8n Workflow

An automated expense tracking system built with n8n that allows users to track their expenses through Telegram messages.

## Demo Video


[![Demo Video](https://img.youtube.com/vi/R_rpVs98ohc/maxresdefault.jpg)](https://youtu.be/R_rpVs98ohc?si=K4jiL96eNHjbOoMw)

## Overview

This n8n workflow creates a personal expense tracker that:
- Receives expense information via Telegram messages
- Uses AI to understand and process expense details
- Automatically updates a Google Sheet with the expense data
- Maintains conversation memory for better user interaction

## Components

### 1. Telegram Trigger
- Listens for incoming messages from users on Telegram
- Initiates the workflow when a message is received

### 2. AI Agent
- Powered by Groq's LLama3-70B model
- Understands natural language descriptions of expenses
- Extracts key information: date, category (personal/business), description, amount, and type

### 3. Simple Memory
- Maintains conversation context
- Allows for follow-up questions and clarifications

### 4. Google Sheets Integration
- Automatically appends expense data to a Google Sheet
- Organizes expenses in a structured format

### 5. Telegram Response
- Sends confirmation and details back to the user
- Provides feedback on the recorded expense

## How It Works

1. User sends an expense message to the Telegram bot (e.g., "I spent $25 on lunch today")
2. The AI agent processes the message to extract expense details
3. If information is missing, the bot asks for clarification
4. Once complete, the expense is recorded in the Google Sheet
5. A confirmation message is sent back to the user with the recorded details

## Setup Requirements

To use this workflow, you'll need:
- An n8n instance
- Telegram bot credentials
- Groq API access
- Google Sheets API credentials
- A configured Google Sheet with the appropriate columns

## Sheet Structure

The Google Sheet is structured with the following columns:
- Date
- Personal/Business
- Description
- Amount (USD)
- Type

## Example Usage

User: "I paid $15.99 for Netflix subscription yesterday"

Bot Response:
```
Date: 01/05/2023
Personal/Business: personal
Description: Netflix subscription
Amount (USD): 15.99
Type: monthly
```