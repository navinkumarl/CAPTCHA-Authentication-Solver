# CAPTCHA Text Recognition and Image Classification Experiments

This repository contains two independent notebook experiments:

1. **Text recognition with TensorFlow/Keras:** a convolutional and bidirectional LSTM model trained with CTC loss to recognize text in CAPTCHA images.
2. **Image classification with PyTorch:** a VGG16-based transfer-learning experiment that classifies CAPTCHA image tiles into five image categories.

The second experiment is a five-class image classifier; the repository does not establish that it solves or interacts with live reCAPTCHA challenges. These materials are intended for authorized experimentation with data you are permitted to process. Do not use them to bypass access controls or automate protected services.

## Experiments

| Directory | Notebook | Scope |
| --- | --- | --- |
| [`tensorflow-captcha-ocr/`](./tensorflow-captcha-ocr/) | [`tensorflow_text_ocr.ipynb`](./tensorflow-captcha-ocr/tensorflow_text_ocr.ipynb) | Data preparation, training, and evaluation cells for text OCR using TensorFlow/Keras and MLTU. |
| [`tensorflow-captcha-ocr/`](./tensorflow-captcha-ocr/) | [`tensorflow_ocr_model.ipynb`](./tensorflow-captcha-ocr/tensorflow_ocr_model.ipynb) | Defines the residual CNN and bidirectional LSTM model used by the text-recognition experiment. |
| [`pytorch-recaptcha-image-classification/`](./pytorch-recaptcha-image-classification/) | [`pytorch_vgg16_classifier.ipynb`](./pytorch-recaptcha-image-classification/pytorch_vgg16_classifier.ipynb) | PyTorch/torchvision image-classification experiment using VGG16 transfer learning. |
| [`pytorch-recaptcha-image-classification/`](./pytorch-recaptcha-image-classification/) | [`pytorch_vgg16_classifier_project.ipynb`](./pytorch-recaptcha-image-classification/pytorch_vgg16_classifier_project.ipynb) | A closely related variant of the VGG16 classification workflow. |

The two PyTorch notebooks contain overlapping training and evaluation workflows but configure different Google Drive data locations. The repository does not identify either notebook as the primary, current, or earlier version.

These are separate experiments with different frameworks and data workflows; the repository does not provide a shared application or API.

## Technology

- **Text OCR:** TensorFlow, Keras, MLTU, OpenCV, NumPy, pandas, and Python Levenshtein.
- **Image classification:** PyTorch, torchvision, NumPy, Matplotlib, and tqdm.
- **Notebook environments:** Jupyter notebooks; the PyTorch notebooks include Google Colab and Google Drive references.

Dependencies are installed within the TensorFlow notebook; versions are not fully pinned, and no repository-wide environment file is provided.

## Data and model artifacts

### TensorFlow text-recognition data

The TensorFlow notebook contains cells that download an archive named `captcha_images_v2.zip` into a `Datasets` directory. The downloaded data is not included in this repository. The notebook also fetches a helper file from an external repository.

### PyTorch image-classification data

The PyTorch notebooks define five labels: `Bicycle`, `Bridge`, `Bus`, `Car`, and `Traffic Light`. The image dataset is not included in the current repository. Notebook paths refer to Google Drive locations, so they do not describe a ready-to-use local data path.

The PyTorch notebook documentation identifies an upstream dataset source. Before obtaining, using, or redistributing the data, verify the upstream dataset's current terms and confirm that any modifications are also permitted.

### Model weights

No trained `.pth` checkpoint is included in the current repository. The PyTorch notebook contains model-saving code, but this repository does not provide a standalone model-loading application or a verified checkpoint-use procedure.

## Repository layout

```text
.
├── README.md
├── pytorch-recaptcha-image-classification/
│   ├── pytorch_vgg16_classifier.ipynb
│   └── pytorch_vgg16_classifier_project.ipynb
└── tensorflow-captcha-ocr/
    ├── tensorflow_ocr_model.ipynb
    └── tensorflow_text_ocr.ipynb
```

## Setup and reproducibility

The notebooks are the only implementation files currently included. There is no `requirements.txt`, `pyproject.toml`, Conda environment file, or other repository-wide dependency manifest.

- The TensorFlow notebook includes dependency-installation cells, downloads data and helper code, and refers to `/content/` paths.
- It imports `model` and `configs` modules that are not present as Python files. The model definition is in `tensorflow_ocr_model.ipynb`.
- The PyTorch notebooks mount Google Drive and refer to dataset paths there. The expected image dataset and saved model checkpoint are not included.
- No automated test suite or separate script/CLI entry point is present.

The notebooks may require environment and path adjustments. Their presence and saved outputs do not establish that the workflows are currently reproducible.

## Evaluation and licensing

The notebooks contain training and evaluation code, but the repository does not include a consolidated, independently reproducible results report. No license file or explicit licensing terms for the code, dataset, or model weights are present. The notebooks reference external datasets, helper code, and pretrained model weights; review each upstream project's license and attribution requirements, and confirm that redistribution of modified notebooks, data, and derived weights is permitted before public release or reuse.
