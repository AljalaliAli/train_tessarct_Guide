# Train Tesseract Guide
Here are the main points on how to train Tesseract 5:
#######################################################
Install Linux (Ubuntu as a subsystem on Windows 10)
#######################################################
1- Go to "Windows Features aktivieren oder deaktivieren".
2- Choose "Windows Subsystem for Linux".
3- Click "OK" and restart.
4- Install Ubuntu (as an app) from the Windows Store.
5- Choose a username and password.
6- Use the command `cd /mnt/d "any/dir/you/want/to/access"`.

#########################################################
Fine-tuning Tesseract
#########################################################
1- Install the `tesstrain` from this repository: "https://github.com/tesseract-ocr/tesstrain?tab=readme-ov-file#windows". You can do this using the git command or just download it as a zip file and then unzip it.
2- Move to the `tesstrain` folder directory. For example: `cd "/mnt/d/future link/AljalaliAli/tesseract_fine_tuning/tesstrain-main"`.
3- Create a `data` directory in `tesstrain-main`.
4- Then create a `mde-ground-truth` directory in the `data` directory (mde for the fine-tuned model name).
5- Inside the `ground-truth` directory, add the images and the truth texts. For example: `img_1.tff`, `img_1.gt.txt`, `img_2.tff`, `img_2.gt.txt` ....... `img_n.tff`, `img_n.gt.txt`. (The text to describe each image must have the same name as the image.)
6- Make `tesseract-langdata`.
7- Choose the start model and start the training. It will create `.box` files, `.lstm` files, and everything else:
 `make training MODEL_NAME=mde START_MODEL=eng TESSDATA="/mnt/d/future\ link/AljalaliAli/train_tessarct/tessdata_best-main"`.
