
# Train Tesseract 5 Guide

This guide provides step-by-step instructions on how to train Tesseract 5, including setting up the necessary environment and fine-tuning Tesseract.

## 1. Install Linux (Ubuntu as a Subsystem on Windows 10)

Follow these steps to install Ubuntu as a subsystem on Windows 10:

1. Open **Windows Features**.
2. Enable **Windows Subsystem for Linux**.
3. Click **OK** and restart your computer.
4. Install **Ubuntu** from the Microsoft Store.
5. Set up a username and password when prompted.
6. Use the following command to access any directory:

   ```bash
   cd /mnt/d/any/dir/you/want/to/access
   ```

## 2. Fine-tuning Tesseract

### 2.1 Install Requirements

First, install the required Python package:

```bash
pip3 install Pillow
```

### 2.2 Download and Set Up Tesstrain

1. Clone the `tesstrain` repository or download it as a zip file from [GitHub](https://github.com/tesseract-ocr/tesstrain?tab=readme-ov-file#windows).

   ```bash
   git clone https://github.com/tesseract-ocr/tesstrain.git
   ```

2. Navigate to the `tesstrain` directory. For example:

   ```bash
   cd "/mnt/d/future link/AljalaliAli/OCR Tesseract Feintuning/2- tesstrain/"
   ```

3. Create a `data` directory inside the `tesstrain-main` folder:

   ```bash
   mkdir data
   ```

4. Inside the `data` directory, create a folder named after your fine-tuned model (e.g., `mde`), and then create a `ground-truth` directory within it. Add your images and corresponding ground truth text files into this directory.

   Example structure:

   ```
   data/
   ├── mde/
       └── ground-truth/
           ├── img_1.tif
           ├── img_1.gt.txt
           ├── img_2.tif
           ├── img_2.gt.txt
           └── ...
   ```

   Ensure that each image file (`.tif`) has a corresponding text file (`.gt.txt`) with the same name.

### 2.3 Prepare Language Data

Run the following command to create the necessary language data:

```bash
make tesseract-langdata
```

### 2.4 Start the Training Process

Choose the start model and begin the training process. This will generate `.box` files, `.lstm` files, and other necessary files.

Example commands:

```bash
make training MODEL_NAME=mde START_MODEL=eng TESSDATA="/mnt/d/future\ link/AljalaliAli/tessdata_best-main"
```

Other examples:

```bash
make training MODEL_NAME=abc START_MODEL=eng TESSDATA="tessdata_best-main"

make training MODEL_NAME=xya START_MODEL=eng TESSDATA="tessdata_best-main"

make training MODEL_NAME=ftk START_MODEL=dig TESSDATA="/mnt/d/future\ link/AljalaliAli/DataGeneration/DataGeneration/Tesseract_5/tessdata"
```

