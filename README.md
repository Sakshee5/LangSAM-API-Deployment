# Lang-SAM Deployment

[Hugging Face Deployment](https://huggingface.co/spaces/sakshee05/langSAM)

Contains deployment of the Lang-SAM (Language-Segment Anything) model along with SAM2 for advanced image segmentation capabilities. The project provides a FastAPI backend with a web interface for easy interaction.

## Features

- Language-guided image segmentation using Lang-SAM
- Advanced segmentation capabilities with SAM2
- FastAPI backend with CORS support
- Web interface for easy interaction
- OpenAI integration for product name processing

## Prerequisites

- Python 3.12
- OpenAI API key (for product name processing)

## Installation

1. Clone the repository:
```bash
git clone https://github.com/Sakshee5/LangSAM-API-deployment.git
cd LangSAM-API-deployment
```

3. Create and activate a virtual environment:
```bash
python -m venv .venv
source .venv/bin/activate  # On Windows: .venv\Scripts\activate
```

4. Install dependencies:
```bash
pip install -r requirements.txt
```

## Model Setup

### Lang-SAM Model
The Lang-SAM model will be automatically downloaded when you first run the application.

### SAM2 Model
Since the SAM2 model weights are too large for GitHub, you'll need to download them separately:

1. Download the SAM2 model weights:
   - Model: `sam2.1_hiera_small.pt`
   - Place it in the root directory of the project

2. Download the model configuration:
   - Config file: `configs/sam2.1/sam2.1_hiera_s.yaml`
   - Place it in the `configs/sam2.1/` directory

## Environment Setup

Create a `.env` file in the root directory with your OpenAI API key:
```
OPENAI_API_KEY=your_api_key_here
```

## Running the Application

1. Start the FastAPI server:
```bash
uvicorn main:app --reload
```

2. Run `index.html` to test. Either use the deployed Hugging Face endpoints already set up or replace with `localhost` to test locally

## API Endpoints

- `GET /`: Health check endpoint
- `POST /segment`: Image segmentation endpoint
- `POST /openai/chat`: Product name processing endpoint


- Lang-SAM: [GitHub Repository](https://github.com/luca-medeiros/lang-segment-anything)
- SAM2: [Original Implementation](https://github.com/facebookresearch/segment-anything)
