# Assignment 3 — Weather Chatbot (Tools + Reasoning)

This project is a small command-line chatbot that answers weather questions using real weather data. It connects to a language model that can call tools such as a weather API and a calculator. The program includes three modes: basic mode, reasoning mode, and advanced mode with safer tool execution and parallel tool calls.

## How to run the program

**1.** Open the project folder and (optionally) create a virtual environment:

```bash
cd "Assignment 3"
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

**2.** Add your API keys:

You need the following variables:
- API_KEY
- BASE_URL
- LLM_MODEL
- WEATHER_API_KEY (you can get this from weatherapi.com using the free plan)

**3.** Run the program:

```bash
python conversational_agent.py
```

You will see a menu:
- 1 = Basic weather chatbot
- 2 = Weather + calculator with reasoning
- 3 = Advanced mode (multi-step reasoning, parallel tool calls, optional JSON output)

You can also run a specific mode directly:

```bash
python conversational_agent.py 1
python conversational_agent.py --mode 2
```

Do not upload the .env file or any real API keys to GitHub.

## Bonus mode (optional)

If you completed the bonus task, you can compare all three agents using one question and save the results to a CSV file:

```bash
python conversational_agent.py --bonus "Compare the current weather in Cairo, Riyadh, and London."
```

## Code overview

- Part 1: Retrieves current weather and forecasts from WeatherAPI and connects them as tools.
- Part 2: Adds a calculator tool and step-by-step reasoning.
- Part 3: Adds safer tool execution, parallel tool execution, multiple tool steps, and structured JSON output.

## Example prompts

Try questions like:
- What’s the weather in Tokyo right now?
- Which is warmer in °C: 20°C in Paris or 68°F in New York?
- What’s the temperature difference between Cairo and London right now?
- Average maximum temperature in Cairo over the next 3 days?
- Compare weather in Cairo, Riyadh, and London.

## Notes

Basic mode only uses weather tools.  
Mode 2 is used when calculations are needed.  
Mode 3 includes error handling, parallel tool execution, and multi-step tool usage.

If the program does not run correctly, check:
- API key
- Base URL
- Location name
- Environment variables

## Helpful links

- OpenAI Function Calling Documentation
- Structured Outputs / JSON Responses
- WeatherAPI Documentation
