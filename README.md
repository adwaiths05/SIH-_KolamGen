# SIH-_KolamGen

This repository demonstrates two methods for generating single-stroke drawings inspired by Kolam art:

1. **L-System Generation:**  
   Generates a single continuous stroke based on L-systems, a formal grammar used to model the growth processes of plant development, but also applicable to generating complex patterns.

2. **Image Vectorization and Eulerian Path:**  
   Processes a collection of Kolam images, extracts edge information, builds a graph from these edges, and attempts to find an Eulerian path or circuit to represent the drawing as a single stroke. If a single path is not found, it draws the largest connected component as multiple segments.

---

## Setup

1. **Clone the Repository:**  
   ```bash
   git clone https://github.com/adwaiths05/SIH-_KolamGen.git
   cd SIH-_KolamGen
   ```

2. **Install Dependencies:**  
   Run the first code cell in the notebook or execute:
   ```bash
   pip install -r requirements.txt
   ```
   (If a `requirements.txt` is not available, install the following manually: `networkx`, `svgwrite`, `numpy`, `pillow`, `opencv-python`, `python-dotenv`, `IPython`, `pathlib`, and optionally `roboflow`.)

3. **Prepare Images (for Image Vectorization):**  
   If you are using the image vectorization method, place your Kolam images in a directory accessible by the notebook.  
   The current code expects images in `/content/drive/MyDrive/kolam/Single`.  
   You may need to adjust this path or upload images directly to your Colab session.

---

## Usage

### 1. L-System Generation

- The second code cell (`cell_id: 1c4f31b4`) generates a single stroke Kolam using an L-system.
- Modify the `KolamParams` object to experiment with different L-system rules, iterations, symmetry, and grid configurations.
- Run the cell to generate and display the SVG output. The output file will be saved to the `out` directory.

### 2. Image Vectorization and Eulerian Path

- The third code cell (`cell_id: BTvdPgBgdy2Z`) processes images to generate single-stroke drawings.
- Ensure your images are in the specified directory (`/content/drive/MyDrive/kolam/Single` by default).
- Adjust parameters like `quantization_factor`, `max_dist`, and `resample_step` within the `draw_single_stroke_kolam_from_image` function call to fine-tune the vectorization and path-finding process.
- Run the cell to process all images in the directory, attempt to find single strokes, and save the resulting SVGs to the `out` directory. The first few generated SVGs will be displayed.

---

## Output

- Generated SVG files will be saved in the `out` directory.

---

## Libraries Used

- **roboflow:** Potentially used for data loading or processing .
- **networkx:** For graph creation and Eulerian path/circuit finding.
- **svgwrite:** For generating SVG files.
- **numpy:** For numerical operations.
- **pillow (PIL):** For image loading and manipulation.
- **opencv-python (cv2):** For image processing, specifically edge detection.
- **IPython.display:** For displaying SVGs in the notebook.
- **pathlib:** For handling file paths.

---

## Main Functions

- **kolam_lsystem:** (Assumed from context) Generates L-system paths.
- **KolamParams:** (Assumed from context) Defines parameters for L-system generation.
- **generate_kolam:** (Assumed from context) Generates Kolam patterns using L-systems.
- **to_svg:** Converts paths and dots to an SVG file.
- **list_images:** Lists image files in a directory.
- **load_and_preprocess_kolam:** Loads, resizes, and performs edge detection on an image.
- **find_eulerian_path_or_circuit:** Finds an Eulerian path or circuit in a graph.
- **quantize:** Quantizes complex points to integer tuples.
- **resample_poly:** Resamples a polyline for smoothing.
- **draw_single_stroke_kolam_from_image:** Main function for processing images, finding paths, and generating SVG.

---

## Acknowledgements

This project is inspired by Kolam art and explores computational techniques for generating continuous-stroke drawings.

---
