# FocusMode 🎯

FocusMode is a smart web application that uses your webcam and a machine learning model to provide real-time feedback on your engagement level. It helps you stay focused during study sessions or work by gently monitoring your attention and providing a live engagement score.
-----

## 🚀 Key Features

  * **Real-time Engagement Analysis**: Uses a TensorFlow model to classify your focus level in real-time.
  * **Computer Vision Powered**: Employs OpenCV to process webcam frames directly in the browser-backend pipeline.
  * **Modern Web Interface**: A clean and simple frontend built with React and Vite.
  * **Engagement Score**: Calculates and displays an overall engagement percentage based on the analysis.
  * **Privacy-Focused**: All image processing can be handled locally; images are not stored long-term.

-----

## ⚙️ How It Works

The application has a simple client-server architecture:

1.  **Frontend (React)**: The user interface captures video from the webcam. It periodically sends frames as images to the backend API.
2.  **Backend (Python)**: A lightweight server receives the images. The `predict.py` script preprocesses each image and feeds it into the pre-trained TensorFlow/Keras model (`model83.h5`).
3.  **Analysis & Response**: The model predicts an "engagement" score. The backend aggregates these scores and sends a clean JSON response back to the frontend.
4.  **UI Update**: The React frontend dynamically updates the displayed engagement percentage.

Here is a simplified flow diagram:

```
[User @ Webcam] --> [React Frontend] --> [Python API] --> [ML Model] --> [JSON Response] --> [UI Update]
```

-----

## 🛠️ Getting Started

Follow these instructions to get a copy of the project up and running on your local machine for development and testing purposes.

### Prerequisites

You will need the following software installed on your machine:

  * [Node.js](https://nodejs.org/en/) (which includes `npm`)
  * [Python 3.8+](https://www.python.org/downloads/) and `pip`

### Installation

1.  **Clone the repository:**

    ```sh
    git clone https://github.com/Raviteja-021/focusmode.git
    cd focusmode
    ```

2.  **Setup the Backend:**

      * Navigate to the backend directory (`cd backend`).
      * Create and activate a Python virtual environment:
        ```sh
        # For macOS/Linux
        python3 -m venv venv
        source venv/bin/activate

        # For Windows
        python -m venv venv
        .\venv\Scripts\activate
        ```
      * Install the required Python packages:
        *(**Note**: You need to create a `requirements.txt` file in your `backend` directory with the content below)*
        ```sh
        pip install -r requirements.txt
        ```

3.  **Setup the Frontend:**

      * Navigate to the frontend directory (`cd ../frontend`).
      * Install the required `npm` packages:
        ```sh
        npm install
        ```

### Running the Application

1.  **Start the Backend Server:**

      * From the `backend` directory, start the server (assuming you wrap your logic in a Flask app named `app.py`).
        ```sh
        python app.py
        ```
      * The backend will typically run on `http://127.0.0.1:5000`.

2.  **Start the Frontend Application:**

      * From the `frontend` directory, start the Vite development server.
        ```sh
        npm run dev
        ```
      * Open your browser and navigate to **http://localhost:5173** (or the URL provided in your terminal).

-----

## 💻 Technology Stack

  * **Frontend**: [React](https://reactjs.org/), [Vite](https://vitejs.dev/)
  * **Backend**: [Python](https://www.python.org/)
  * **ML/CV**: [TensorFlow](https://www.tensorflow.org/), [OpenCV](https://opencv.org/)
  * **API Framework (Recommended)**: [Flask](https://flask.palletsprojects.com/) or [FastAPI](https://fastapi.tiangolo.com/)

-----

## 🌟 Future Improvements

  * [ ] Create a historical graph to track focus over a session.
  * [ ] Add sound alerts for when focus drops significantly.
  * [ ] Allow users to tune the sensitivity of the model.
  * [ ] Package the application into a standalone desktop app using Electron.

-----

## 📜 License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details.

-----

## 🙏 Acknowledgments

  * Hat tip to anyone whose code was used as inspiration.
  * Thanks to the creators of the libraries and frameworks that made this possible.
