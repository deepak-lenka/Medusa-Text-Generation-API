# Medusa Text Generation API

This project implements a FastAPI-based web server that provides text generation capabilities using the Medusa language model. It's designed to run in a Jupyter notebook environment and uses ngrok to expose the local server to the internet.

## Features

- Text generation using the Medusa 1.0 Zephyr 7B Beta model
- FastAPI web server for handling generation requests
- 8-bit quantization for efficient model inference
- Ngrok integration for exposing the local server
- Asynchronous request handling
- Built-in testing script

## Requirements

- Python 3.7+
- PyTorch
- Transformers
- FastAPI
- Uvicorn
- Pyngrok
- Nest-asyncio
- Aiohttp

## Installation

1. Clone this repository:
   ```
   git clone https://github.com/yourusername/medusa-text-generation-api.git
   cd medusa-text-generation-api
   ```

2. Install the required packages:
   ```
   pip install fastapi uvicorn torch transformers accelerate medusa pyngrok nest-asyncio aiohttp bitsandbytes
   pip install git+https://github.com/FasterDecoding/Medusa.git
   ```

3. Set up your Hugging Face account and have your access token ready.

## Usage

1. Open the Jupyter notebook `medusa_api.ipynb`.

2. Run the cells to set up the model, create the FastAPI app, and start the server.

3. The notebook will display a public URL provided by ngrok. You can use this URL to send requests to your API.

4. To generate text, send a POST request to the `/generate` endpoint with a JSON payload containing the prompt and max_length:

   ```python
   import requests

   url = "YOUR_NGROK_URL/generate"
   payload = {
       "prompt": "What is artificial intelligence?",
       "max_length": 100
   }
   response = requests.post(url, json=payload)
   print(response.json())
   ```

5. The API will return a JSON response with the generated text and the generation time.

## Testing

The notebook includes a testing script that sends multiple prompts to the API and displays the results. Run the testing cells to see the API in action.

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This project is open source and available under the [MIT License](LICENSE).

## Acknowledgements

- This project uses the Medusa model from the [FasterDecoding](https://github.com/FasterDecoding/Medusa) project.
- Thanks to the creators of FastAPI, Transformers, and all other open-source libraries used in this project.
