# The Amazin’ Quizzer App (in working progress)

## Table of Contents
- [Introduction](#introduction)
- [Project Overview](#project-overview)
- [Spike: Design & Planning](#spike-design--planning)
  - [Database Schema](#database-schema)
  - [API Endpoints](#api-endpoints)
- [User Stories](#user-stories)
- [Acceptance Criteria](#acceptance-criteria)
- [Stretch Goals](#stretch-goals)
- [Getting Started](#getting-started)
- [API Documentation](#api-documentation)
  - [Quiz Management](#quiz-management)
  - [Question Management](#question-management)
- [License](#license)

## Introduction

The **Amazin’ Quizzer App** is a dynamic web application designed to generate and manage quizzes. The application provides interfaces for both quiz creation and quiz taking. You can use AI tools to generate questions or utilize provided ones, stored in a JSON object acting as a mock database.

## Project Overview

This project involves developing a RESTful API to serve as the backend for the Amazin’ Quizzer App. The API will handle quiz generation, question management, and provide detailed quiz results.

## Spike: Design & Planning

Before diving into feature development, it’s crucial to design the data schema and RESTful API structure. This will ensure clarity and consistency as you build out the application.

### The Wireframe Design
Click [here](https://app.moqups.com/6HB95STuO4RGOCGiEgHGGW50BH0r95Zf/view/page/ad64222d5) to view the wireframe.


### Database Schema

The application uses a JSON object as a mock database. Below is the proposed schema for the data:

```json
{
  "categoryName": {
    "categoryID": "<some id>",
    "questions": [
        {
        "id": "1",
        "category": "Math",
        "difficulty": "easy",
        "question": "What is 2 + 2?",
        "choices": ["2", "3", "4", "5"],
        "answer": "4",
        "favourite_count": 0
        },
        {
        "id": "2",
        "category": "Science",
        "difficulty": "medium",
        "question": "What planet is known as the Red Planet?",
        "choices": ["Earth", "Mars", "Jupiter", "Saturn"],
        "answer": "Mars",
        "favourite_count": 5
        }
    ] 
    }
}


# API Endpoints

Here are the planned API endpoints for the Amazin’ Quizzer App:

- **GET `/api/quizzes`**:
  - **Purpose**: Generate a quiz based on selected parameters.
  - **Usage Example**: Retrieve a quiz with specified category and difficulty.
  
- **GET `/api/questions`**:
  - **Purpose**: Retrieve a list of questions.
  - **Optional Filters**: Category and difficulty.
  - **Usage Example**: Get questions in the 'Science' category with 'medium' difficulty.
  
- **POST `/api/questions`**:
  - **Purpose**: Add a new question to the database.
  - **Usage Example**: Submit a new question with multiple-choice answers.

- **PUT `/api/questions/{id}`**:
  - **Purpose**: Edit an existing question.
  - **Parameters**: `id` of the question to be edited.
  - **Usage Example**: Update the text or answers of a specific question.
  
- **DELETE `/api/questions/{id}`**:
  - **Purpose**: Delete a question by its ID.
  - **Parameters**: `id` of the question to be deleted.
  - **Usage Example**: Remove a question that is no longer needed.

- **PATCH `/api/questions/{id}/favourite`**:
  - **Purpose**: Increment the favourite count of a question.
  - **Parameters**: `id` of the question.
  - **Usage Example**: Mark a question as a favourite.

# User Stories

As a quizzer, I want to:

- Select a subject area for my quiz.
- Begin a quiz session with randomly generated questions.
- View a summary of my quiz results, including areas of strength and weakness.
- Add, edit, and delete quiz questions and answers.

# Acceptance Criteria

The API should:

- Dynamically generate quizzes with adaptive difficulty.
- Filter quiz questions by category.
- Return any number of questions based on the specified criteria.
- Allow for adding or deleting questions from the database.
- Provide clear and thorough documentation on how to use the API.





