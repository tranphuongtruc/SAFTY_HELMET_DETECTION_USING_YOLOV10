# SAFTY HELMET DETECTION USING YOLOV10
## Description
This project detects whether workers are wearing safety helmets or not.


## Installation

#### Running the Notebook on your computer

1. *Clone the repository:*
    ```sh
    git clone https://github.com/tranphuongtruc/SAFTY_HELMET_DETECTION_USING_YOLOV10.git
    cd SAFTY_HELMET_DETECTION_USING_YOLOV10
    ```

2. *(Optional)Create a virtual environment:*
   
    On Windows:
 
    ```sh
    python -m venv venv
    .\venv\Scripts\activate
    ```

    On macOS and Linux:

    ```sh
    python3 -m venv venv
    source venv/bin/activate
    ```

#### Running the Notebook on Google Colab

1. *Open Google Colab*

    Go to [Google Colab](https://colab.google/)

2. Upload Your Notebook

    Click on ***File*** -> ***Upload notebook***
    Choose the .ipynb file from your local machine.

3. *(optional) Mount Google Drive*

    If your notebook requires access to files stored in your Google Drive, you can mount it using the following code:

    ```sh
    from google.colab import drive
    drive.mount('/content/drive')
    ```


#### NOTES when running the Notebook on your computer and on Google Colab

1. *Download the dataset and unzip folders*

    ```sh
    !gdown '1u-faV2YF1fzpsMyKHMn0PS94SOM0MzTW'
    !mkdir -p safety_helmet_dataset
    !unzip -q '/content/Safety_Helmet_Dataset.zip' -d '/content/safety_helmet_dataset'
    ```

2. *Clone YOLOv10 source code and initialize the model*

    ```sh
    !git clone https://github.com/THU-MIG/yolov10.git
    %cd yolov10
    !pip install -q -r requirements.txt
    !pip install -e .
    !wget https://github.com/THU-MIG/yolov10/releases/download/v1.1/yolov10n.pt
    ```

3. *Save your results after training the model*
    ```sh
    from ultralytics import YOLOv10
    MODEL_PATH = YOLOv10('/content/yolov10/runs/detect/train4/weights/best.pt')
    IMG_PATH = '<path_to_your_image>'
    result = model(source=IMG_PATH)[0]
    result.save('<path_to_save_your_results>')
    ```
