# Smart Glasses Project

## Overview

This project aims to develop **Smart Glasses**, an innovative wearable device that combines a camera, AI-based keyword spotting (KWS), and a cloud/server-based backend. The system captures images, processes them based on specific keywords or commands, and interacts with cloud services.

## Features

- **Camera Integration**: Captures images using a camera module.
- **Keyword Spotting (KWS)**: Detects voice commands for hands-free interaction.
- **Server Communication**: Sends image data to a cloud/server for processing.
- **Docker Support**: Containerized environment for easy deployment.
- **Automated Services**: Uses `docker-compose` for managing multiple services.

## Project Structure

```bash
├── firmware/                # Firmware code for the Smart Glasses hardware
│   ├── camera_pins.h        # Pin configurations for the camera module
│   ├── kws.ino              # Arduino-based keyword spotting logic
├── server/                  # Backend server for processing images
│   ├── app.py               # Main application logic
│   ├── requirements.txt     # Python dependencies
│   ├── docker-compose.yml   # Docker setup for services
│   ├── Dockerfile           # Containerization setup
│   ├── .env.example         # Environment variable template
│   ├── start_services.sh    # Script to start backend services
│   ├── uploaded_image.png   # Sample uploaded image for reference
├── .dockerignore            # Exclusions for Docker
├── .gitignore               # Exclusions for Git
├── README.md                # Project documentation (this file)
```

## Installation & Setup

### Prerequisites

- Docker & Docker Compose
- Python 3.x
- Arduino IDE (for firmware development)

### Steps

1. **Clone the Repository**

   ```bash
   git clone https://github.com/parthiv11/smart-glasses.git
   cd smart-glasses
   ```

2. **Set Up Environment Variables**

   Copy the example environment file and edit it with your API keys:

   ```bash
   cp .env.example .env
   ```

   Edit the `.env` file to include your API keys:

   ```env
   DEEPGRAM_API_KEY=your_deepgram_api_key
   MODEL_NAME=gemini-1.5-flash
   GEMINI_API_KEY=your_gemini_api_key
   ```

3. **Install Dependencies**

   Navigate to the server directory and install the required Python packages:

   ```bash
   cd server
   pip install -r requirements.txt
   ```

4. **Run the Server**

   Use Docker Compose to build and start the services:

   ```bash
   docker-compose up --build
   ```

5. **Deploy Firmware to Smart Glasses**

   - Open `kws.ino` in the Arduino IDE.
   - Connect the Smart Glasses hardware via USB.
   - Upload the firmware to the device.

## Usage

1. **Wear the Smart Glasses**: Ensure the device is powered on and properly fitted.
2. **Voice Commands**: Use predefined voice commands to capture images or perform other actions.
3. **Data Processing**: Captured images are sent to the server for processing.
4. **Results Access**: View processed data or results on the backend server or associated application.

## Contributing

Contributions are welcome! Please fork the repository and submit a pull request with your changes. Ensure that your code adheres to the project's coding standards and includes appropriate tests.

## License

This project is licensed under the MIT License. See the `LICENSE` file for more details.
