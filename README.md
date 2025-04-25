# Phonic Twilio Integration

A simple Python application that integrates Phonic's Speech-to-Speech API with Twilio's Programmable Voice Media Streams.

## Overview

This application enables real-time voice conversations between callers and an AI assistant powered by Phonic. When someone calls your Twilio number, the audio is streamed to Phonic for processing, and the AI's response is streamed back to the caller, creating a seamless conversational experience.

## Features

- Real-time audio streaming between Twilio and Phonic
- Fast, low-latency responses
- Customizable voice selection
- Configurable system prompt and welcome message

## Prerequisites

- A Phonic API key (get one at [phonic.co/api-keys](https://phonic.co/api-keys))
- A Twilio account with a phone number
- A publicly accessible server to host this application

## Installation

This project uses [uv](https://github.com/astral-sh/uv) for dependency management. uv is a fast Python package installer and resolver.

1. Install dependencies using uv:

```bash
uv sync
```

This will install all dependencies defined in `pyproject.toml` according to the lock file.

2. Set your Phonic API key as an environment variable:

```bash
export PHONIC_API_KEY="your_phonic_api_key_here"
```

## Usage

1. Run the application:

```bash
python simple_twilio_example.py
```

2. Expose your local server to the internet (e.g., using [ngrok](https://ngrok.com/)):

```bash
ngrok http 8000
```

3. Update the Stream URL in `templates/twilio.xml` with your public URL.

4. Configure your Twilio phone number to use the `/twiml` endpoint as the webhook for incoming calls.

## Configuration

You can customize the following parameters in `simple_twilio_example.py`:

- `SYSTEM_PROMPT`: Instructions for the AI assistant
- `WELCOME_MESSAGE`: The message played when a call connects
- `VOICE_ID`: The Phonic voice to use (default: "greta")

## Project Structure

- `simple_twilio_example.py`: Main application code
- `templates/twilio.xml`: TwiML configuration for Twilio
- `hello.py`: Simple test script
- `pyproject.toml`: Project metadata and dependencies
- `uv.lock`: Lock file for dependencies

## License

This project is available for personal and commercial use under the terms of the license agreement.