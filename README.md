# PhishGuard

An intelligent machine learning-based system for detecting and classifying phishing websites and URLs in real-time.

## Overview

PhishGuard is a sophisticated security tool that employs advanced machine learning algorithms to identify phishing attempts with high accuracy. By analyzing URL structures, website features, and behavioral patterns, the system provides reliable protection against online fraud and phishing attacks.

## Features

- **Intelligent URL Analysis**: Comprehensive feature extraction from URLs to identify phishing indicators
- **Machine Learning Classification**: Trained models for accurate phishing detection
- **Real-Time Detection**: Fast and efficient URL scanning and classification
- **Web Interface**: User-friendly Flask-based web application
- **Docker Support**: Ready-to-deploy containerized solution
- **Dataset Processing**: Tools for converting and processing Kaggle phishing datasets
- **Scalable Architecture**: Built for production deployment and integration

## Tech Stack

- **Language**: Python 3.7+
- **ML Framework**: Scikit-learn / XGBoost
- **Web Framework**: Flask
- **Containerization**: Docker & Docker Compose
- **Data Processing**: Pandas, NumPy
- **Model Pipeline**: Feature extraction → Classification → Prediction

## Project Structure

```
phishguard/
├── app.py                        # Flask web application
├── model.py                      # ML model training and inference
├── feature_extractor.py          # URL feature extraction module
├── main.py                       # Main execution script
├── convert_kaggle_dataset.py     # Dataset conversion utility
├── inspect_csv.py                # CSV data inspection
├── simple_inspect.py             # Additional inspection tools
├── requirements.txt              # Python dependencies
├── setup.py                      # Package setup configuration
├── config.toml                   # Configuration file
├── Dockerfile                    # Docker image definition
├── docker-compose.yml            # Docker Compose configuration
└── .gitignore                    # Git ignore rules
```

## Installation

### Prerequisites

- Python 3.7 or higher
- pip package manager
- Docker & Docker Compose (optional, for containerized deployment)

### Local Setup

1. **Clone the repository**
   ```bash
   git clone https://github.com/Yash-Sainii/phishguard.git
   cd phishguard
   ```

2. **Create virtual environment** (optional but recommended)
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Start the application**
   ```bash
   python app.py
   ```
   The application will be available at `http://localhost:5000`

### Docker Setup

1. **Build and run with Docker Compose**
   ```bash
   docker-compose up --build
   ```

2. **Or build and run manually**
   ```bash
   docker build -t phishguard .
   docker run -p 5000:5000 phishguard
   ```

## Usage

### Web Application

Access the web interface after starting the application:
```bash
python app.py
```

Submit URLs through the web interface for real-time phishing detection results.

### Command Line Interface

Analyze URLs directly from the terminal:
```bash
python main.py <url>
```

### Feature Extraction

Extract features from URLs for custom analysis:
```bash
python feature_extractor.py --url <url>
```

### Data Processing

Convert Kaggle phishing datasets to compatible format:
```bash
python convert_kaggle_dataset.py --input <dataset_path> --output <output_path>
```

### Data Inspection

Inspect and validate your dataset:
```bash
python inspect_csv.py --file <csv_file_path>
python simple_inspect.py --file <csv_file_path>
```

## Configuration

Customize the application behavior by editing `config.toml`:

```toml
[model]
algorithm = "xgboost"
threshold = 0.5

[features]
max_features = 30

[server]
port = 5000
debug = false
```

## Model Training

To train or retrain the phishing detection model:

1. Prepare your phishing dataset
2. Process the dataset:
   ```bash
   python convert_kaggle_dataset.py
   ```

3. Train the model:
   ```bash
   python model.py --train --data <dataset_path>
   ```

4. Evaluate performance:
   ```bash
   python model.py --evaluate --data <test_dataset>
   ```

## API Endpoints

- `POST /predict` - Predict phishing status for a URL
- `GET /status` - Check application status
- `POST /batch` - Batch process multiple URLs

## Performance

PhishGuard achieves robust performance through:
- Advanced feature engineering for URL analysis
- Ensemble machine learning models
- Continuous model optimization
- High precision and recall rates

## Contributing

We welcome contributions from the community! To contribute:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit changes (`git commit -m 'Add AmazingFeature'`)
4. Push to branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## License

This project is open source and available under the MIT License. See LICENSE file for details.

## Security Notice

PhishGuard is designed to enhance security awareness but should not be relied upon as the sole security measure. Always:

- Verify website authenticity through multiple methods
- Never share sensitive credentials on unverified sites
- Keep your browser and security software updated
- Enable two-factor authentication where available

## Troubleshooting

### Port Already in Use
```bash
python app.py --port 8080
```

### Missing Dependencies
```bash
pip install --upgrade -r requirements.txt
```

### Docker Issues
```bash
docker-compose down
docker-compose up --build
```

## Support & Contact

For issues, feature requests, or questions:
- Open an issue on GitHub
- Check existing issues for solutions
- Review documentation in the repository

## Future Roadmap

- [ ] Browser extension integration
- [ ] Real-time threat intelligence API
- [ ] Enhanced mobile support
- [ ] Improved model accuracy
- [ ] Community threat database

