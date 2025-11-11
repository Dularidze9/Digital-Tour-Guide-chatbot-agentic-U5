# Digital-Tour-Guide-chatbot-agentic-U5

# Overview

In this small demo, we’ll walk through building an intelligent assistant that can provide local guidance and information to visitors. The workflow demonstrates how a retrieval-based system combined with decision-making components can improve response quality for location-specific questions.

## Project Goal

The purpose of this work is to enhance the travel experience for people visiting Istanbul by allowing them to receive helpful, contextually accurate information about the city — from cultural sites and food suggestions to live, real-time details such as transport costs or weather conditions.

## Tools Used

OpenAI models – used for both reasoning and embedding creation

LangGraph / LangChain – for defining the logic of the assistant

Chroma – for storing and recalling information

Tavily – for web-based live lookup

Gradio – for creating a simple chat interface

(Make sure your API environment variables are correctly configured.)

## Dataset

For demonstration purposes, three publicly available Istanbul travel documents were used as the knowledge source. These are stored in a vector-based database and used by the assistant for semantic retrieval.

Structure and Data Flow

The system combines two main sources of knowledge:

Stored guidebook data for background knowledge

Online results for up-to-date details

The flow uses several processing steps (translation, routing, retrieval grading, and answer generation) to produce contextually relevant responses.

Nodes handle functions such as:

Translating the user’s input if needed

Routing the question to the appropriate source

Checking the relevance of retrieved data

Generating the final response

Verifying factual consistency

Filtering out inappropriate content

These parts are connected with edges that define how information moves between components.

## Agent Logic

The agent begins by receiving a user question.
If needed, it translates it into a suitable language.
It then decides whether the answer should come from stored data or from live web lookup.
Once data is retrieved, the system checks for relevance, rewrites or adjusts the query if necessary, and finally creates the answer using a generative model.
A final moderation step ensures that the response remains safe and appropriate for all audiences.

## Visualization and Flow

LangGraph is used to define, visualize, and execute the agent’s workflow.
Each node is a small Python function, and the edges define the logical flow — making debugging and modification straightforward.

## Testing Examples

The assistant can respond to questions about historical places, local weather, or cultural sites.
It supports multilingual input, translating questions automatically before processing.
The model produces accurate, context-grounded answers — verified against its retrieved information.

## Outcome

This small project shows how retrieval-based workflows and adaptive decision systems can work together to produce dynamic, useful conversational tools.
The architecture can easily be extended for other cities or domains by replacing the document set and adjusting the routing logic.
