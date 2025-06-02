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

### Built-In Vapi Tools

#### Google Calendar Check Availability

This is used to check when the plumber is available.

#### Google Calendar Event Creation

This is used to book customer visits into the plumber's calendar.

### Tools Integrated via MCP Servers

#### Google Maps Address Validation

This is integrated via a custom MCP server running on Cloudflare. It calls the
Google Maps Address Validation API.

It is used to validate a customer's address in case it has been transcribed incorrectly.

#### Google Maps Distance Calculation

This is integrated via the same customer MCP server as the address validation
tool above. It calls the Google Maps Routes API.

It is used to check whether a customer's address is within the plumber's
service area.

#### SMS Sender

This is integrated via the Zapier MCP server and uses the Twilio SMS sending service.

It is used to send brief messages to the plumber as required.

## Error Handling / Fallback

The agent is encouraged to send the plumber an SMS in the case of any enquiry it
is not sure how to handle.
