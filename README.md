# Code Gen: A code generation agent

This project leverages the power of transformers and the Hugging Face pipeline to streamline coding tasks, enhance code interaction through chatbots, and generate coding templates from existing codebases. Our solutions utilize state-of-the-art language models to provide developers with intuitive and efficient tools for code completion, conversation with code, and template generation.

## Features

- **Code Completion:** Utilize Polycoder for context-aware code completions, focusing on naming conventions and code quality.
- **Conversational Code Interaction:** Interact with your codebase using GPT-3.5 and its local version, GPT-Neo, through a sophisticated chatbot interface.
- **Template Generation:** Generate reusable code templates from your company's codebase using a specialized model, ensuring consistency and adherence to best practices.

## System Requirements

- **Google Colab** for running notebooks in the cloud.
- **TPU** acceleration for optimal performance.
- **Disk Space:** At least 127.7 GB available.
- **RAM:** At least 12.7 GB.

## Dependencies

This project requires the following Python libraries:

- `transformers`
- `torch`, `torchvision`, `torchaudio` (for PyTorch-based models)
- `openai` (for GPT-3.5 access)
- `python-dotenv` (for environment variable management)
- `panel` (for web interfaces in notebooks)

## Installation

Start by cloning this repository to your local machine or Google Colab environment:

```bash
git clone <repository-url>
```

Install the required dependencies:

```bash
pip install transformers torch torchvision torchaudio openai python-dotenv panel
```

## Running the Notebooks

To run the notebooks with Google Colab and take advantage of TPU acceleration, follow these steps:

1. Open Google Colab and import your notebook.
2. Go to `Edit` -> `Notebook settings` or `Runtime` -> `Change runtime type` and select `TPU` as the hardware accelerator.
3. Make sure your Colab environment meets the disk space and RAM requirements mentioned above.
4. Execute the following snippet at the beginning of your notebook to ensure compatibility with TPU:

```python
import torch

assert torch.cuda.is_available()
device = torch.device("cuda")
```

5. Run the notebooks as usual, the TPU will automatically be utilized for operations supported by PyTorch.

## Models Used

This project utilizes the following models from the Hugging Face Transformers library:

- **Polycoder** for code completion.
- **GPT-3.5** and **GPT-Neo** for conversational code interaction.
- **Custom/Specified Model (e.g., Falcon 7b)** for template generation from codebases.

## Example Usage

Here's a quick snippet to get started with the Hugging Face pipeline and GPT-3.5 for conversational code interaction:

```python
from transformers import pipeline

# Initialize the chatbot pipeline
chatbot = pipeline("conversational", model="gpt-3.5-turbo")

# Example conversation with the chatbot
response = chatbot("Hello, how can I help you with your code today?")

print(response)
```

## Contributing

We welcome contributions and suggestions! Please fork the repository and submit pull requests with your improvements. For major changes or questions, please open an issue first to discuss what you would like to change.

## License

[MIT](LICENSE)

