# Grammar Scoring Engine for Voice Samples

A comprehensive system for analyzing speech grammar, providing corrections, and generating detailed reports with visualizations.

## Overview

The Grammar Scoring Engine transcribes spoken language from audio files, evaluates grammatical accuracy, provides corrections, and generates insightful reports. This tool combines state-of-the-art speech recognition, natural language processing, and machine learning to deliver actionable insights into grammar quality.

## Features

- **Speech-to-Text Transcription**: Convert audio recordings into text using OpenAI's Whisper model
- **Grammar Analysis & Correction**: Identify and correct grammatical errors using advanced NLP techniques
- **Error Pattern Detection**: Recognize specific error types including subject-verb disagreement, article errors, run-on sentences, and more
- **Linguistic Complexity Assessment**: Calculate various readability metrics and linguistic features
- **Sentiment & Fluency Analysis**: Evaluate emotional tone and grammatical acceptability
- **Data Visualizations**: Generate insightful charts and graphs representing analysis results
- **Comprehensive PDF Reports**: Create professional reports with scores, metrics, and visualizations

## Installation

```bash
# Clone the repository
git clone https://github.com/shivprasadrahulwad/grammar-scoring-engine.git
cd grammar-scoring-engine



# Download additional resources
python -m nltk.downloader punkt averaged_perceptron_tagger wordnet
python -m spacy download en_core_web_sm
```

## Requirements

This project requires:

```
whisper>=1.0.0
transformers>=4.25.0
torch>=1.13.0
nltk>=3.7
numpy>=1.22.0
pandas>=1.4.0
matplotlib>=3.5.0
seaborn>=0.11.0
spacy>=3.4.0
scikit-learn>=1.0.0
textstat>=0.7.0
fpdf>=1.7.2
```

## Usage

### Basic Usage

```python
from grammar_scoring_engine import GrammarScoringEngine

# Initialize the engine
engine = GrammarScoringEngine()

# Run analysis on an audio file
results = engine.run_full_analysis("path/to/audio_file.mp3", output_dir="./output/")

# Access results
transcription = results["transcription"]
analysis = results["analysis"]
report_path = results["report_path"]
```

### Analyzing Text Directly

```python
# For analyzing text without audio transcription
text = "Your sample text with grammar errors here."
analysis = engine.analyze_grammar(text)

# Generate visualizations and report
engine.generate_visualizations(analysis, output_dir="./output/")
engine.generate_report(analysis, output_dir="./output/")
```

## Analysis Components

The Grammar Scoring Engine provides:

1. **Grammar Score**: Overall measurement of grammatical correctness (0-100)
2. **Error Types**: Breakdown of different error categories
3. **Error Patterns**: Detection of specific grammatical issues
4. **Complexity Metrics**: Multiple readability and linguistic complexity scores
5. **Corrected Text**: Grammatically improved version of the input

## Visualization Outputs

The system generates multiple visualizations:

- Error types bar chart
- Error pattern radar chart
- Readability metrics display
- Grammar score gauge
- Section quality heatmap
- Text improvement comparison

## Applications

This Grammar Scoring Engine is useful for:

- Language education and assessment
- Professional speaking development
- Communication skills training
- Speech therapy progress monitoring
- Academic research in linguistics

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Acknowledgments

- OpenAI for the Whisper speech recognition model
- Hugging Face for transformer models
- The NLTK and spaCy teams for NLP tools
