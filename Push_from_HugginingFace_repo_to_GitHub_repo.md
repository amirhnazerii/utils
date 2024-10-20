# **Push from HugginingFace repo to GitHub repo**

***by Amirhossein(Amir) Nazeri***

## **Use Git Command Line**

### **1. Clone the HF Repository:**

If you haven't cloned the repository to your local machine, do so with:
\
Link to my HF home: https://huggingface.co/amirhossein20n/spam_not_spam/tree/main
![image.png](https://github.com/amirhnazerii/utils/blob/main/imgs/HF1.png?raw=true)

Follow the steps below: \
 Make sure you have git-lfs installed (https://git-lfs.com)
```
C:\Users\anazeri> git lfs install
C:\Users\anazeri> cd .\HuggingFace\
C:\Users\anazeri\HuggingFace> git clone https://huggingface.co/amirhossein20n/spam_not_spam

```


### **2. Clone the GitHub Repository:**

Do the similar approach as did in the last section now for Git cloning:

```
C:\Users\anazeri> git clone https://github.com/amirhnazerii/utils.git
```



### **3. Copy the Folder to the Local Repository:**

1.   *Navigate to your cloned Git repository directory* and copy the folder

2.   Remove **.git** hidden file from the copied folder `spam_not_spam` (HF folder)

you want to upload into it.

```
cp -r /path/to/your/folder /path/to/cloned/repository/
```

confirm the sucessful cloning:
```
    Directory: C:\Users\anazeri\utils
----                 -------------         ------ ----
d-----         8/27/2024  12:57 PM                spam_not_spam
-a----         8/27/2024  12:32 PM           3228 Datasets.ipynb
-a----         8/27/2024  12:32 PM         126569 Finetune_RoBERTa_TextClassification_LoRA.ipynb
-a----         8/27/2024  12:32 PM           1050 Get large file from google drive
-a----         8/27/2024  12:32 PM        1580524 how-to-load-kaggle-datasets-directly-into-google-colab.pdf
-a----         8/27/2024  12:32 PM         138095 img1.png
-a----         8/27/2024  12:32 PM            611 Pip install in conda environment.md
```

### **4. Add, Commit, and Push the Changes:**

```
C:\Users\anazeri\utils> git add .\spam_not_spam\
C:\Users\anazeri\utils> git commit -m "Training parameters for spam_not_spam added - corrected
C:\Users\anazeri\utils> git push origin main
```
#### **Note:**
if you mistakenly `git add .` a wrong file/folder, you must delete the file + cashe using:

```
git rm -f --cached spam_not_spam
```





