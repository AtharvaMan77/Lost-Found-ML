\# 🔍 Lost \& Found AI

\### Find What's Lost. Reconnect What's Found.



An AI-powered Lost \& Found application that helps people reconnect with misplaced belongings through intelligent image and text matching.



<p align="center">

&#x20; <img src="https://img.shields.io/badge/Python-3.11-blue?logo=python" alt="Python">

&#x20; <img src="https://img.shields.io/badge/Backend-Flask-black?logo=flask" alt="Flask">

&#x20; <img src="https://img.shields.io/badge/Deep%20Learning-PyTorch-ee4c2c?logo=pytorch" alt="PyTorch">

&#x20; <img src="https://img.shields.io/badge/Vision-OpenCLIP-6c63ff" alt="OpenCLIP">

&#x20; <img src="https://img.shields.io/badge/Storage-Git%20LFS-green" alt="Git LFS">

</p>



\---



\## 🌟 About the Project



Losing a personal belonging can be frustrating. Finding it again shouldn't be.



\*\*Lost \& Found AI\*\* is a web-based application designed to connect people who have lost belongings with people who have found them.



The platform brings together a frontend interface, Flask backend, database management, and machine-learning components to make the matching process more efficient.



Users can submit lost or found item reports, including relevant descriptions and images. The matching system analyzes available information, identifies similarities, and ranks potentially matching reports for review.



The goal is to make lost-and-found management smarter, more organized, and more accessible through AI-assisted matching.



\## ✨ Key Features



| Feature | Description |

|---|---|

| 👤 User Authentication | User registration and authentication functionality |

| 📦 Lost Item Reporting | Submit details about misplaced belongings |

| 🔎 Found Item Reporting | Register items that have been found |

| 🖼️ Image Matching | Compare visual representations of item images |

| 📝 Text Matching | Analyze item descriptions for similarities |

| 🧠 AI Match Ranking | Rank candidate reports using matching signals |

| 🗄️ Database Management | Manage application records using SQLite |

| ⚙️ Modular Backend | Organize application functionality through Flask routes and services |



\## 🏗️ System Architecture



The application is organized into four main layers:



1\. \*\*Frontend:\*\* Provides the interface for users to interact with the application.

2\. \*\*Backend:\*\* Handles requests, authentication, item submissions, and communication with application services.

3\. \*\*Database:\*\* Stores and manages application information.

4\. \*\*Machine Learning:\*\* Analyzes item information and helps identify potentially matching reports.



\### 🔄 Application Workflow



```mermaid

flowchart TD

&#x20;   A\["👤 User"] --> B\["🌐 Frontend Interface"]

&#x20;   B --> C\["⚙️ Flask Backend"]



&#x20;   C --> D\["🔐 Authentication"]

&#x20;   C --> E\["🗄️ SQLite Database"]

&#x20;   C --> F\["🤖 Matching Engine"]



&#x20;   F --> G\["🖼️ Image Similarity"]

&#x20;   F --> H\["📝 Text Similarity"]

&#x20;   F --> I\["📍 Category, Location \& Time Signals"]



&#x20;   G --> J\["📊 Match Ranking"]

&#x20;   H --> J

&#x20;   I --> J



&#x20;   J --> K\["🔎 Potential Match Results"]

&#x20;   K --> B

```



\### How It Works



1\. \*\*Report:\*\* A user submits a lost or found item report.

2\. \*\*Process:\*\* The Flask backend receives and processes the submitted information.

3\. \*\*Analyze:\*\* The matching components analyze available image and textual information.

4\. \*\*Compare:\*\* Similarity signals are used to evaluate candidate reports.

5\. \*\*Rank:\*\* The system ranks potentially matching items.

6\. \*\*Review:\*\* Users can review potential matches and verify them independently.



\*AI-generated matches are suggestions for human review, not proof of ownership.\*



\## 🤖 Machine Learning



The Machine Learning component focuses on identifying similarities between lost and found items using computer vision, text analysis, and similarity-based matching.



\### 🖼️ Image Matching with OpenCLIP



The project uses OpenCLIP-based visual representations to compare item images.



The image encoder converts an image into a numerical embedding that captures visual information. These embeddings can then be compared using cosine similarity.



\### 🧠 V4 Metric-Learning Model



A dedicated metric-learning model was developed to improve image similarity comparisons.



\*\*Model architecture\*\*



| Component | Configuration |

|---|---|

| Vision Backbone | OpenCLIP ViT-B-32 |

| Input Embedding | 512 dimensions |

| Projection Layer | Linear 512 → 128 |

| Output Embedding | 128 dimensions |

| Normalization | L2 normalization |

| Similarity Metric | Cosine similarity |



\*\*Inference pipeline\*\*



```text

Input Image

&#x20;   ↓

OpenCLIP ViT-B-32 Encoder

&#x20;   ↓

512-D Image Embedding

&#x20;   ↓

Learned Linear Projection

&#x20;   ↓

128-D Embedding

&#x20;   ↓

L2 Normalization

&#x20;   ↓

Cosine Similarity

&#x20;   ↓

Image Similarity Score

```



\### 📊 V4 Model Evaluation



The V4 metric-learning image matcher was evaluated on a held-out test dataset.



| Evaluation Metric | Test Result |

|---|---:|

| ROC AUC | \*\*0.8880\*\* |

| Average Precision | \*\*0.8806\*\* |

| Accuracy | \*\*80.21%\*\* |

| Precision | \*\*74.58%\*\* |

| Recall | \*\*91.67%\*\* |

| F1 Score | \*\*82.24%\*\* |



\*\*Evaluation configuration\*\*



\- Training samples: 2,800

\- Validation samples: 480

\- Test samples: 480

\- Best validation epoch: 16

\- Validation-selected threshold: approximately 0.596



\*\*Important:\*\* These metrics describe the V4 image-matching model on its evaluation dataset. They do not represent the accuracy of the entire application. The cosine similarity score is not a calibrated probability.



\### 📝 Text and Multimodal Matching



The broader matching approach considers multiple signals:



\- \*\*Image similarity:\*\* Visual similarity between item images.

\- \*\*Text similarity:\*\* Similarity between item descriptions.

\- \*\*Category compatibility:\*\* Whether the reported item categories are compatible.

\- \*\*Location proximity:\*\* Geographic closeness of reported locations.

\- \*\*Time proximity:\*\* Time difference between lost and found reports.



Combining these signals can help rank candidate matches more effectively than relying on a single matching factor.



\## 🛠️ Technology Stack



| Layer | Technologies |

|---|---|

| Programming Language | Python |

| Frontend | HTML, CSS, JavaScript |

| Backend | Flask |

| Database | SQLite |

| Deep Learning | PyTorch |

| Image Embeddings | OpenCLIP |

| Image Processing | OpenCV |

| Object Detection Model | YOLO |

| Similarity Comparison | Cosine Similarity |

| Model Storage | Git LFS |



\## 📁 Project Structure



```text

Lost-Found-ML/

│

├── LostFoundFrontend/             # Frontend interface

│   ├── index.html

│   └── Other frontend HTML files

│

├── handoff/                       # ML inference and integration resources

│   ├── inference.py

│   ├── inference\_test\_report.json

│   ├── backend\_integration\_example.py

│   └── models/

│       └── open\_clip\_model.safetensors

│

├── routes/                        # Flask application routes

│   ├── auth\_routes.py

│   ├── claim\_routes.py

│   ├── item\_routes.py

│   ├── match\_routes.py

│   └── upload\_routes.py

│

├── services/                      # Matching and ranking services

│   ├── details\_match\_service.py

│   ├── image\_match\_service.py

│   ├── match\_ranking\_service.py

│   └── text\_match\_service.py

│

├── vision/                        # Computer vision modules

│   ├── image\_match.py

│   ├── image\_model.py

│   ├── image\_preprocess.py

│   ├── lost\_found\_pipeline.py

│   ├── yolo\_detect.py

│   └── vision/

│       └── ...

│

├── app.py                         # Flask application entry point

├── auth\_routes.py

├── database.py

├── schema.sql

├── requirements.txt

├── metric\_learning\_v4\_model.pt

├── metric\_learning\_v4\_metrics.json

└── yolo11n.pt

```



\## 🚀 Getting Started



\### Prerequisites



\- Python 3.11 or a compatible version.

\- Git.

\- Git LFS.

\- Required Python dependencies.

\- A compatible PyTorch environment for the selected CPU or GPU setup.



\### 1. Clone the Repository



```bash

git clone https://github.com/AtharvaMan77/Lost-Found-ML.git

cd Lost-Found-ML

```



\### 2. Download Large Model Files



This repository uses Git LFS to manage large model artifacts.



```bash

git lfs install

git lfs pull

```



\### 3. Create a Virtual Environment



For Windows PowerShell:



```powershell

python -m venv .venv

.venv\\Scripts\\Activate.ps1

```



\### 4. Install Dependencies



```bash

pip install -r requirements.txt

```



\### 5. Configure Environment Variables



Configure the environment variables required by the application.



Create a local `.env` file if needed and use the variable names expected by the source code.



\*\*Never commit private credentials, API keys, tokens, or environment files to GitHub.\*\*



\### 6. Initialize the Database



Initialize the SQLite database using the application's database initialization logic and the provided `schema.sql` file.



\### 7. Run the Application



```bash

python app.py

```



Open the local URL displayed in the Flask terminal output.



\*Note: Database initialization, environment configuration, and model paths may depend on the local setup. Check the application source code for the exact runtime requirements.\*



\## 📦 Large Model Files – Git LFS



This repository uses \*\*Git Large File Storage (Git LFS)\*\* to manage large machine-learning model checkpoints.



One of the stored model files is:



`handoff/models/open\_clip\_model.safetensors`



This file contains OpenCLIP model weights. It is a binary checkpoint in the Safetensors format, not a Python source-code file.



Therefore, when opening it on GitHub, the platform provides a downloadable file instead of displaying readable code.



To retrieve the actual model file locally after cloning:



```bash

git lfs install

git lfs pull

```



The downloaded checkpoint can then be accessed by the relevant model-loading code.



Other model artifacts include:



\- `metric\_learning\_v4\_model.pt` – V4 metric-learning checkpoint.

\- `yolo11n.pt` – YOLO model weights.



\## 👨‍💻 Team \& Contributions



This project was developed collaboratively by a \*\*four-member team\*\*.



The complete application brings together frontend development, backend development, database management, and machine learning.



\### Machine Learning Contribution



My primary focus was the Machine Learning component, including:



\- Working with Amazon and Stanford Online Products datasets.

\- Developing and validating image embedding pipelines.

\- Exploring OpenCLIP-based visual representations.

\- Developing the V4 metric-learning image matcher.

\- Evaluating models using ROC AUC, Average Precision, Precision, Recall, and F1 Score.

\- Preparing inference modules and backend integration resources.

\- Supporting integration of ML functionality into the broader application.



\## 🔮 Future Scope



\- Improve multimodal matching performance.

\- Evaluate matching models on additional real-world Lost and Found data.

\- Improve image-matching inference efficiency.

\- Enhance location-aware and time-aware ranking.

\- Integrate notifications for newly identified potential matches.

\- Expand end-to-end testing and deployment support.

\- Improve the overall user experience.



\## 🔒 Privacy \& Data Handling



The repository contains selected project source code, documentation, and model artifacts.



The following types of local or private data are intentionally excluded:



\- Environment files and private credentials.

\- Local database files.

\- User-uploaded images.

\- Generated outputs and temporary files.

\- Test images and local testing data.



Please keep local configuration and private information outside the public repository.



\## ⚠️ Disclaimer



This application provides AI-assisted suggestions to help identify potentially matching lost and found items.



Similarity scores are intended to support human review. They must not be treated as proof of ownership or as a substitute for independent verification.



\## ⭐ Support the Project



If you find this project interesting, consider giving the repository a ⭐!



\*\*GitHub Repository:\*\*  

https://github.com/AtharvaMan77/Lost-Found-ML



\---



\*\*Built with Python, Deep Learning, Computer Vision, and Teamwork.\*\*

