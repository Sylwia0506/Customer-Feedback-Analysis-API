# Customer Feedback Analysis API

A comprehensive solution for analyzing customer feedback using natural language processing. This application automatically detects sentiment and classifies topics from customer feedback, helping companies respond quickly to critical issues and monitor customer trends in real-time.

## Features

- **Sentiment Analysis**
  - Detects positive, negative, and neutral sentiment
  - Provides confidence scores for each prediction
  - Uses DistilBERT model for accurate analysis

- **Topic Classification**
  - Automatically categorizes feedback into topics:
    - Customer Service
    - Pricing
    - Delivery
    - Product Quality
    - Other
  - Uses BART model for zero-shot classification

- **Real-time Analysis**
  - Instant feedback processing
  - Live updates of sentiment and topic distributions
  - Interactive visualizations

- **Logging & Reporting**
  - Automatic logging of all analyses
  - Maintains history of last 100 feedback entries
  - Generates statistical reports
  - Stores logs in `logs/app.log`

- **Modern Web Interface**
  - Responsive design using Bootstrap
  - Interactive charts with Chart.js
  - Real-time updates
  - Mobile-friendly layout

## Technical Stack

- **Backend**
  - FastAPI (Python web framework)
  - Transformers (Hugging Face)
  - PyTorch
  - Pydantic for data validation

- **Frontend**
  - HTML5
  - CSS3
  - JavaScript (ES6+)
  - Bootstrap 5
  - Chart.js

- **DevOps**
  - Docker containerization
  - Python 3.9
  - Uvicorn ASGI server

## Setup

### Local Development

1. Create a virtual environment:
```bash
python -m venv venv
source venv/bin/activate  # On Windows: .\venv\Scripts\Activate.ps1
```

2. Install dependencies:
```bash
pip install -r requirements.txt
```

3. Run the application:
```bash
uvicorn app.main:app --reload
```

### Docker Deployment

1. Build the Docker image:
```bash
docker build -t feedback-analyzer .
```

2. Run the container:
```bash
docker run -p 8000:8000 feedback-analyzer
```

## API Endpoints

- `POST /analyze`
  - Analyzes feedback text
  - Request body: `{"text": "your feedback text"}`
  - Returns sentiment and topic analysis

- `GET /report`
  - Generates statistical report
  - Returns sentiment and topic distributions

- `GET /recent`
  - Returns recent feedback entries
  - Optional `limit` parameter (default: 100)

- `GET /health`
  - Health check endpoint

## Project Structure

```
.
├── app/
│   ├── main.py           # FastAPI application
│   ├── models.py         # Pydantic models
│   ├── analyzer.py       # Sentiment and topic analysis
│   └── logger.py         # Logging functionality
├── static/
│   ├── index.html        # Frontend interface
│   ├── styles.css        # Custom styles
│   └── app.js           # Frontend logic
├── logs/                 # Application logs
├── requirements.txt      # Python dependencies
├── Dockerfile           # Docker configuration
└── README.md            # Documentation
```

## API Documentation

Once the server is running, visit:
- Swagger UI: `http://localhost:8000/docs`
- ReDoc: `http://localhost:8000/redoc`

## Contributing

1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Push to the branch
5. Create a Pull Request

## License

This project is licensed under the MIT License - see the LICENSE file for details. 