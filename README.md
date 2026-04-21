# Autonomous Smart Weed Detection & Removal Robot 🚜🌿

An end-to-end autonomous agricultural robot designed to detect and physically eradicate weeds using edge AI, cloud training, and embedded hardware.

## 📁 Repository Structure
* `cloud_trainer/`: Contains the Streamlit web app (`app.py`) for manual data annotation and automated Kaggle dataset synchronization (`dataset-metadata.json`).
* `pi5_code/`: The main Python control loop (`raspberry_pi_prog.py`) for the Raspberry Pi 5. Handles live camera streaming, YOLOv8 inference, and UART communication.
* `esp32_code/`: The C++ code (`allmotor_control.ino`) for the ESP32 microcontroller. Manages the motor drivers and triggers the physical cutting mechanism.
* `yolo_models/`: Directory for storing the compiled `.pt` weights fetched from cloud training.
* `docs/`: Project documentation, circuit diagrams, and hardware schematics.

## 🛠️ Hardware Stack
* **Main Processing:** Raspberry Pi 5
* **Microcontroller:** ESP32
* **Vision:** USB Web Camera
* **Actuation:** Motor Drivers, DC Motors, Physical Cutter Mechanism

## 🚀 How to Use
1. **Cloud Training:** Run the Streamlit app locally (`streamlit run cloud_trainer/app.py`) to annotate field images and push them to Kaggle for YOLO retraining.
2. **Edge Deployment:** Pull the newly trained `.pt` model into the `yolo_models/` directory on the Raspberry Pi.
3. **Hardware Execution:** Flash the ESP32 via the Arduino IDE, connect it to the Pi via serial, and run `python3 pi5_code/raspberry_pi_prog.py` to initiate the autonomous search and eradicate sequence.