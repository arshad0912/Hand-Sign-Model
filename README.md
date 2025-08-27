# Hand-Sign-Model
Research Progress Update 
Summary of Progress
Transitioned from unstable third-party ASL models to a fully functional finger-spelling video generation pipeline using
the ASL Alphabet Dataset. Successfully generates English → ASL videos and lays the foundation for word-level ASL
recognition.
- Initial Exploration
Goal: English → ASL sentence-level video with ≥ 90% accuracy. Repositories attempted: SignGAN-ASL (404),
SignAvatar (dependency conflicts), Zenodo ASL datasets (404), MediaPipe-ASL-CNN (missing requirements). Errors:
fatal: could not read Username, tar archive errors. Dependency issues: numpy 1.26 vs 2.0, protobuf 4.25 vs 5.29,
opencv-python build failures.
- Fallback & Stabilization
Dataset Used: ASL Alphabet Dataset (A–Z letters):
https://www.kaggle.com/datasets/grassknoted/asl-alphabet?select=asl_alphabet_test. Implemented dependency-free
pipeline using imageio + Pillow. MP4 (H.264) generation with GIF fallback. Generated /tmp/asl_fingerspell.mp4 and
/tmp/asl_fingerspell.gif successfully for 'HELLO WORLD'. Verified complete A–Z coverage ensuring no missing letters.
-Future Work Plan
1) Dataset Expansion: Search for word-level ASL datasets or extract frames from hand-sign tutorial videos for further
video output. 2) Model Cross-Validation using VideoMAE
(https://github.com/MCG-NJU/VideoMAE?tab=readme-ov-file), WLASL (https://github.com/dxli94/WLASL), and
Hugging Face Video Classification (https://huggingface.co/docs/transformers/tasks/video_classification). 3)
Fine-tuning MediaPipe-CNN or LoRA adapters for word-level recognition. 4) Deployment via ONNX / TF-Lite for web &
mobile.
Next Research Plan
Isolate dependency-free environment using Docker. 28–29 Aug: Harvest 100 English ↔ ASL gloss pairs via
self-recorded 30 FPS clips. 30 Aug: Fine-tune MediaPipe-CNN with LoRA. 31 Aug: Export ONNX model. 1 Sep: Share
Colab notebook demo with video output.
Risks & Mitigations
Repo downtime: Mirror weights to Hugging Face. Build failures: Use Docker + prebuilt wheels. Dataset gaps: Synthetic
fallback pipeline ensures continuity.
Deliverables Ready
Colab Notebook: asl_fallback.ipynb; Fork Repo (WIP): MediaPipe-ASL; Dockerfile: env/Dockerfile; Dataset Coverage:
ASL Alphabet Dataset fully integrated.
Key Achievement
First fully functional English → ASL finger-spelling video output using verified dataset with zero dependency errors.
Cross-validation plan with VideoMAE, WLASL, Hugging Face Video Classification for accuracy checks.
