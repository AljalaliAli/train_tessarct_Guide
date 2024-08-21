Train Tesseract Guide

Here are the main points on how to train Tesseract 5:
#######################################################
Install Linux (Ubuntu as a subsystem on Windows 10)
#######################################################

1- Go to "Windows Features aktivieren oder deaktivieren".
2- Choose "Windows Subsystem for Linux".
3- Click "OK" and restart.
4- Install Ubuntu (as an app) from the Windows Store.
5- Choose a username and password.
6- Use the command cd /mnt/d "any/dir/you/want/to/access".

#########################################################
Fine-tuning Tesseract
#########################################################

1- Install the tesstrain from this dir in Nextcloud, or from github repository:
"https://github.com/tesseract-ocr/tesstrain?tab=readme-ov-file#windows".
You can do this using the git command or just download it as a zip file and then unzip it.

2- Move to the tesstrain folder directory. (python project from tessarct)
For example:

cd "/mnt/d/future link/AljalaliAli/OCR Tesseract Feintuning/2- tesstrain/"


3- Create a data directory in tesstrain-main.

4- Then create a mde-ground-truth directory in the data directory (mde for the fine-tuned model name)

Inside the ground-truth directory, add the images and the truth   texts.
For example: img_1.tff, img_1.gt.txt, img_2.tff,
img_2.gt.txt ....... img_n.tff, img_n.gt.txt. (The text to describe each image must have the same name as the image.)
.(done from another sw! see creat_new_font_grou nd_truth and creat_ground_truth)

5- make langdata

make 'tesseract-langdata'

6- Choose the start model and start the training. It will create .box files, .lstm files, and everything else:

make training MODEL_NAME=mde START_MODEL=eng TESSDATA="/mnt/d/future\ link/AljalaliAli/tessdata_best-main"

another example:
make training MODEL_NAME=abc START_MODEL=eng TESSDATA="tessdata_best-main"

make training MODEL_NAME=xya START_MODEL=eng TESSDATA="tessdata_best-main"
another example:
make training MODEL_NAME=ftk START_MODEL=dig TESSDATA="/mnt/d/future\ link/AljalaliAli/DataGeneration/DataGeneration/Tesseract_5/tessdata"


