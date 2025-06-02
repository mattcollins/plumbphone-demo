# PlumbPhone

These are some technical technical details about the implementation of PlumbPhone - a demo phone answering agent built on the Vapi.ai voice agent framework.

Demo video: https://x.com/mattcollinsuk/status/1929515238233129280

## Components

- Voice agent framework: Vapi.ai
- Speech-to-text: Deepgram Nova 3
- LLM: OpenAI gpt-4o
- Text-to-speech: Vapi Elliot
- Tools (configured via Vapi's web interface): various - see below

## Tools

### Google Calendar Check Availability

- Type: built-in Vapi tool
- Purpose: checks when the plumber is available

### Google Calendar Event Creation

- Type: built-in Vapi tool
- Purpose: books customer visits into the plumber's calendar

### Google Maps Address Validation

- Type: integrated via Cloudflare-hosted custom MCP server
- Purpose: used to check that a customer's address has been transcribed
  correctly

### Google Maps Distance Calculation

- Type: integrated via Cloudflare-hosted custom MCP server
- Purpose: used to check whether a customer's address is within the plumber's service
  area

### SMS Sender

- Type: integrated via Zapier MCP server
- Purpose: used to escalate issues that can't be handled by the agent to the plumber
- Notes: uses Twilio's SMS-sending
