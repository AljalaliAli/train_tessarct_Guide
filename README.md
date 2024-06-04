# train_tessarct_Guide
Hier are the main points how to train tesaract 5
#######################################################
install linux (ubunto as subsystem on windows 10) 
#######################################################
1- go to go to windowsfeature aktivieren oder deaktiveren 
2-choose windows subsystem for linux 
3- ok and restart
4- install ubuto (as app ) from windows store
5- choose user name and psw
6-cd /mnt/d "any/dir/you/want/to/accsses"
#########################################################
fine tunning tessarct
#########################################################
1- install the tesstrain fro this repo:"https://github.com/tesseract-ocr/tesstrain?tab=readme-ov-file#windows"
using git command or just download as zip file then unzip
2- move to the tesstrain folder dir for example:"cd "/mnt/d/future link/AljalaliAli/tesseract_fine_tunning/tesstrain-main"
3- creat data dir in tesstrain-main
4-then creat mde-ground-truth dir in data dir (mde for the finne tunnied moudel name)
5-inside the ground-truth add the images and the truth texts for example: img_1.tff, img_1.gt.txt,img_2.tff, img_2.gt.txt ....... img_n.tff, img_n.gt.txt (text to describe each image the text must have the same img name )
6-make tesseract-langdata
7- choose the start model and start thetraining it will creat ox file and lstm files and every thing:
 make training MODEL_NAME=mde  START_MODEL=eng TESSDATA="/mnt/d/future\ link/AljalaliAli/train_tessarct/tessdata_best-main"
