# DocuMind-AI

## AI-Based Intelligent Document Information Extraction

DocuMind AI is a deep learning project for automated information extraction from documents using OCR and LayoutLMv3. The project combines document text, word positions, and document layout to identify and extract important information from business documents.

The system processes documents and generates structured information in JSON format.

## Model Used

### LayoutLMv3

LayoutLMv3 is a multimodal Transformer model designed for document understanding. It considers:

* Text content
* Document layout
* Spatial positions of words

The pretrained LayoutLMv3 model was fine-tuned on a document understanding dataset for information extraction.

## Document Processing Pipeline

The system follows an end-to-end pipeline:

1. Input document is uploaded.
2. OCR extracts text from the document.
3. Word-level bounding boxes are generated.
4. Text and layout information are passed to LayoutLMv3.
5. The fine-tuned model predicts the required entities.
6. Predictions are converted into structured JSON output.

## Model Performance

The fine-tuned model was evaluated using Precision, Recall, and F1-Score.

| Metric    |  Score |
| --------- | -----: |
| Precision | 0.3871 |
| Recall    | 0.3672 |
| F1-Score  | 0.3769 |

The model was fine-tuned for 3 epochs and successfully learned to identify document entities from unseen documents.

## Information Extraction

The system can identify important information from business documents and return the results in a structured format.

Example output:

```json
{
  "document_type": "invoice",
  "entities": [
    {
      "label": "company_name",
      "value": "Example Company"
    },
    {
      "label": "invoice_number",
      "value": "INV-001"
    }
  ]
}
```

## Technologies Used

* Python
* Google Colab
* PyTorch
* Hugging Face Transformers
* LayoutLMv3
* Tesseract OCR
* Pytesseract
* PDF2Image
* Gradio
* NumPy
* Scikit-learn

## Project Notebook

The complete implementation is available in the Jupyter/Google Colab notebook:

`DocuMind_LayoutLMv3.ipynb`

## Application

A Gradio-based interface was developed to allow users to upload documents and obtain extracted information through the trained model.


