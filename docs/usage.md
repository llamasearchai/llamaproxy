# Usage Guide

## Basic Usage

### Installation

First, install the package:

```bash
pip install llamaproxy
```

### Initializing the Client

```python
import llamaproxy

# Create a client
client = llamaproxy.Client(api_key="your_api_key")
```

### Processing Queries

```python
# Process a single query
result = client.process("How does machine learning work?")
print(result)

# Process multiple queries
results = client.batch_process([
    "What is deep learning?",
    "How do transformers work?",
    "Explain neural networks"
])
```

## Advanced Usage

### Custom Configuration

```python
config = {
    "model": "llama-3-70b",
    "temperature": 0.7,
    "max_tokens": 1000
}

client = llamaproxy.Client(config=config)
```

### Using Callbacks

```python
def on_complete(result):
    print(f"Processing completed: {result}")

client.process("Analyze this text", callback=on_complete)
```

### Error Handling

```python
try:
    result = client.process("Your query")
except llamaproxy.exceptions.APIError as e:
    print(f"API Error: {e}")
except llamaproxy.exceptions.AuthenticationError as e:
    print(f"Authentication failed: {e}")
except Exception as e:
    print(f"Unexpected error: {e}")
```
