## AI-Powered Content Analyzer
This is a powerful, client-side tool for analyzing image content using a multi-layered AI approach. It runs entirely in the browser with no need for server-side processing or API keys, leveraging open-source models to provide a comprehensive analysis of both text and visual elements within an image.

# Features
* Dual-Channel Analysis: Analyzes both the text prompt used to generate an image and the final image content itself.

* Text Recognition (OCR): Uses Tesseract.js to detect and extract all text within an image.

* Object Detection: Employs a COCO-SSD model via TensorFlow.js to identify and locate up to 80 common objects.

* Contextual Object Classification (CLIP): For each detected object, the tool uses OpenAI's CLIP model (via transformers.js) to classify whether the object represents a hateful symbol or a neutral object.

* Keyword Flagging: Scans both the input prompt and the recognized image text for a customizable list of hateful keywords.

* Zero-API & Privacy-Focused: All models (Tesseract, TensorFlow.js, CLIP) are downloaded and run directly in your browser. No data ever leaves your computer.

# How It Works
The tool performs a multi-step analysis to determine if content is potentially hateful:

1. Prompt Analysis: It first checks the user-provided text prompt for any hateful keywords.

2. Object Detection: It identifies all objects in the uploaded image.

3. CLIP Classification: Each detected object is isolated and classified by CLIP to determine if it is visually similar to a "hateful symbol."

4. Text Recognition: It reads all text present in the image.

5. Final Assessment: The tool provides a final assessment based on a combination of all findings: hateful prompts, hateful keywords in the image text, and objects classified as hateful by CLIP.

# What is Considered Hateful Content?
This tool flags content based on three primary signals:

* Hateful Keywords in Prompts: If the text prompt used to generate the image contains words from a predefined list of hateful terms, the content is flagged. This catches intent at the source.

* Hateful Keywords in Image Text: The tool uses OCR to read text within the image. If any of this text contains words from the hateful keyword list, it is flagged and highlighted.

* Visually Hateful Objects/Symbols: The tool uses the CLIP model to analyze detected objects. If an object is a better match for the description "a photo of a hateful symbol" than "a photo of a neutral object," it is flagged. This helps identify non-textual hate content.

# How to Use
1. Download the index.html file from this repository.

2. Open the index.html file in a modern web browser (like Chrome, Firefox, or Edge).

3. The necessary AI models will begin to download automatically. This may take a moment on the first run.

4. Optionally, enter the text prompt that was used to generate your image.

5. Upload the image you want to analyze.

6. Click the "Analyze Image & Prompt" button to see the results.

# Limitations
Model Size & Performance: The AI models, especially CLIP, are large and can be slow to download and run, particularly on older hardware.

Hate Symbol Recognition: The CLIP model's ability to identify hate symbols is based on its training data and the text prompts used for classification. It is a powerful tool for contextual understanding, but may not be exhaustive or perfect.

Keyword List: The list of hateful keywords is for demonstration purposes and is not comprehensive.

# Contributing
Contributions are welcome! Please feel free to fork the repository, make changes, and submit a pull request.

This tool is for educational and demonstration purposes to showcase modern, client-side AI capabilities.