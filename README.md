## Installation & Requirements

1. **Clone the repository:**
   ```bash
   git clone [https://github.com/tanishgarg-ai/Wheat-disease-classification.git](https://github.com/tanishgarg-ai/Wheat-disease-classification.git)
   cd wheat-disease-classification
   ```

2. **Install dependencies:**
   Ensure you have Python 3.8+ installed. Install the required packages using the `requirements.txt` file.
   ```bash
   pip install -r requirements.txt
   ```
   *Core Dependencies:* `torch`, `torchvision`, `pandas`, `seaborn`, `opencv-python`, `matplotlib`, `numpy`, `Pillow`.

## Usage

### Running Inference
You can test the model on a single image using the provided prediction function. The inference script automatically resizes the image, normalizes it, passes it through the model, and displays a Grad-CAM heatmap overlay.

Open the Jupyter Notebook (`wheat-disease-efficientnet-b3-pytorch-92acc.ipynb`) and run the final cell with your local image path:

```python
from pathlib import Path

# Define the local test directory
TEST_DIR = Path("./data/test")
image_path = str(TEST_DIR / "mite_test/mite_28.png")

# Predict and visualize
predict_image(image_path)
```

### Training the Model
If you wish to retrain the model from scratch or fine-tune it further:
1. Ensure the dataset is placed in the `./data/` directory.
2. Open the notebook and run all cells sequentially. The training loop includes early stopping (patience=3) and learning rate scheduling (ReduceLROnPlateau) out of the box.

## Project Structure
```text
.
├── wheat-disease-efficientnet-b3-pytorch-92acc.ipynb  # Main pipeline and inference Notebook
├── README.md                                          # Project documentation
├── requirements.txt                                   # Python dependencies
├── data/                                              # Dataset folder (must be downloaded separately)
└── saved_models/                                      # Directory for saving trained weights
```

