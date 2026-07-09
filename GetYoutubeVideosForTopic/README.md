**Overview**
**GetYoutubeVideosForTopic** is a no-code automation built using Make.com, Google Sheets, and the YouTube Data API v3.
The purpose of this workflow is to automate YouTube competitor research by collecting structured information about the most relevant videos for any topic.

Instead of manually searching YouTube, opening videos, copying statistics, and maintaining spreadsheets, this automation performs the complete process automatically. It searches YouTube for a given topic, retrieves the top matching videos, fetches detailed metadata for each video, converts YouTube category IDs into human-readable category names, and stores all the information in a structured Google Sheet for further analysis.

This project is designed as the first step towards building a complete AI-powered Content Research Agent that will later include transcript analysis, comment analysis, SEO keyword generation, hashtag suggestions, script generation, and AI-based competitor analysis.

**Project Objectives:**
Automate YouTube competitor research
Eliminate repetitive manual data collection
Build structured datasets for AI analysis
Prepare content research for YouTube creators
Create reusable automation for SEO and content strategy

**Features:**
• Reads a topic from Google Sheets
• Searches YouTube using the YouTube Data API
• Retrieves the top relevant videos based on the topic
• Fetches detailed information for each video
• Converts YouTube Category IDs into readable Category Names
• Stores all processed data in an output Google Sheet
• Produces structured data that can later be consumed by AI models for content research

**Technologies Used:**
Make.com
Google Sheets
YouTube Data API v3
HTTP Module
JSON Parser
Iterator
Variable Management
Google Sheets Search Module
Google Sheets Add Row Module
Workflow

**The workflow follows the below sequence:**
Input Topic (Google Sheets)
↓
Search Top Matching YouTube Videos
↓
Parse API Response
↓
Loop Through Each Video
↓
Retrieve Complete Video Details
↓
Convert Category ID into Category Name
↓
Save Results into Output Sheet

**Workflow Modules**

**Module 1 – Get Topic from Input Sheet**
The automation begins by reading a topic entered in the input Google Sheet.

Example:
Morning Motivation

The topic acts as the search keyword for the YouTube API.

**Module 2 – Search YouTube Videos**
The workflow calls the YouTube Search API to retrieve the most relevant videos for the entered topic.

API Endpoint:
GET /youtube/v3/search

Information returned:
Video ID
Title
Description
Channel Name
Published Date
Thumbnail URL

**Module 3 – Parse JSON**
The JSON response received from the API is parsed into a structured array that can be processed inside Make.com.

This converts raw API data into individual records.

**Module 4 – Loop Through Videos**
The Iterator processes every video one by one.

This allows additional API calls to be made for every individual video.

**Module 5 – Retrieve Video Details**
Using the Video ID from each record, another API call is made to retrieve detailed information.

API Endpoint:
GET /youtube/v3/videos

The following information is collected:
View Count
Like Count
Comment Count
Duration
Category ID
Tags
Statistics
Video URL

**Module 6 – Convert Category ID**
The YouTube API returns only the numeric Category ID.

Example:
22

Instead of storing the numeric value, the workflow searches another Google Sheet containing the category mapping.

Example:
22 → People & Blogs

This makes the final report much easier to understand.

**Module 7 – Store Results**
The processed data is written into an Output Google Sheet.

Each row contains:
Search Topic
Video Title
Video URL
Channel Name
Published Date
View Count
Like Count
Comment Count
Video Duration
Category Name
Description
Input

The automation requires only one input.
Google Sheet

Topic
Morning Motivation
Time Management
Public Speaking
Output

The automation generates a structured Google Sheet containing the following information.

| Topic | Video Title | Channel | Views | Likes | Comments | Duration | Category | Published Date | Video URL |

**This output can directly be used for:**
Competitor Research
AI Prompt Engineering
Keyword Analysis
SEO Research
Content Planning
Script Generation
Business Value

**Manual YouTube research usually involves:**
Searching YouTube
Opening multiple videos
Copying titles
Recording statistics
Organizing spreadsheets

This repetitive work can easily take 30 to 60 minutes for a single topic.

The AI YouTube Research Agent completes the same task automatically in under a minute while producing a clean, structured dataset that is ready for analysis.

**Skills Demonstrated:**
This project demonstrates practical experience with:
API Integration
Workflow Automation
No-Code Development
JSON Parsing
HTTP Requests
Data Mapping
Process Automation
Google Workspace Automation
AI Workflow Design
Data Collection
Data Transformation
Repository Structure

This project demonstrates how no-code automation platforms can be combined with REST APIs to build scalable business workflows.

The automation showcases the complete lifecycle of an API-driven workflow—from collecting user input and integrating with external services to processing JSON responses, transforming data, enriching it with lookup information, and storing structured output for further AI-driven analysis.

It also serves as a strong foundation for developing more advanced AI agents capable of performing autonomous research, generating insights, and assisting with content creation.

I specialize in AI Automation, Agile Delivery, Process Optimization, Workflow Engineering, Prompt Engineering, and Data-Driven Transformation, with the goal of creating real-world solutions that enhance productivity and business outcomes.
