# LLM Chat Integration Framework

A flexible framework for integrating Large Language Models (LLMs) with various chat platforms including WhatsApp, Instagram, and custom chat interfaces.

## Architecture Overview

This project implements a standardized workflow based on Business Process Model and Notation (BPMN) to handle the integration of LLMs with multiple chat interfaces:

```
User → Message Reception → Pre-Processing → LLM Processing → Post-Processing → Message Delivery → Analytics
```

### BPMN Workflow

1. **User Initiates Interaction**: The process begins when a user sends a message through a chosen platform.
2. **Message Reception**: The system captures the incoming message from the respective platform's API.
3. **Pre-Processing**:
   * Format Normalization: Standardize the message format to ensure consistency.
   * Language Detection: Identify the language of the message for appropriate processing.
4. **LLM Processing**:
   * Input Construction: Formulate the input prompt for the LLM based on the user's message.
   * LLM Invocation: Call the LLM to generate a response.
5. **Post-Processing**:
   * Response Formatting: Adjust the LLM's output to suit the platform's requirements.
   * Content Filtering: Ensure the response complies with content guidelines and policies.
6. **Message Delivery**: Send the processed response back to the user through the original platform.
7. **Logging and Analytics**: Record interaction details for monitoring and improving the system.

## Project Structure

```
llm-chat-integration/
├── config/                     # Configuration files
│   ├── platforms/              # Platform-specific configs
│   │   ├── whatsapp.json       
│   │   ├── instagram.json
│   │   └── custom.json
│   └── llm_providers.json      # LLM API configurations
├── src/
│   ├── adapters/               # Platform-specific adapters
│   │   ├── whatsapp.py
│   │   ├── instagram.py
│   │   └── custom.py
│   ├── core/                   # Core processing modules
│   │   ├── message_reception.py
│   │   ├── preprocessing.py
│   │   ├── llm_processing.py
│   │   ├── postprocessing.py
│   │   ├── message_delivery.py
│   │   └── analytics.py
│   ├── llm/                    # LLM provider integrations
│   │   ├── openai.py
│   │   ├── anthropic.py
│   │   └── huggingface.py
│   ├── utils/                  # Utility functions
│   │   ├── language_detection.py
│   │   ├── content_filtering.py
│   │   └── logging.py
│   └── app.py                  # Main application entry point
├── examples/                   # Example implementations
│   ├── whatsapp_bot.py
│   └── instagram_bot.py
├── tests/                      # Unit and integration tests
├── requirements.txt            # Python dependencies
└── docker-compose.yml          # Docker configuration
```

## Getting Started

### Prerequisites

- Python 3.8+
- API credentials for desired chat platforms
- API keys for LLM providers

### Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/chandratejatiriveedhi/llm-chat-integration.git
   cd llm-chat-integration
   ```

2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Configure platform credentials:
   - Copy the example configuration files in `config/platforms/` and update with your API keys
   - Set up LLM provider credentials in `config/llm_providers.json`

4. Run the application:
   ```bash
   python src/app.py
   ```

## Platform Integration

### WhatsApp
Integrates with WhatsApp Business API to receive and respond to user messages.

### Instagram
Uses Instagram Messaging API to handle direct messages through a business account.

### Custom Chat Interface
Provides a flexible adapter for custom chat interfaces or other messaging platforms.

## LLM Providers

The framework supports multiple LLM providers:

- OpenAI (GPT-4, GPT-3.5)
- Anthropic (Claude)
- HuggingFace models

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This project is licensed under the MIT License - see the LICENSE file for details.
