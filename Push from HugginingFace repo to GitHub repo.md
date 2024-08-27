{
  "nbformat": 4,
  "nbformat_minor": 0,
  "metadata": {
    "colab": {
      "provenance": []
    },
    "kernelspec": {
      "name": "python3",
      "display_name": "Python 3"
    },
    "language_info": {
      "name": "python"
    }
  },
  "cells": [
    {
      "cell_type": "markdown",
      "source": [
        "# **Push from HugginingFace repo to GitHub repo**\n",
        "\n",
        "***by Amirhossein(Amir) Nazeri***"
      ],
      "metadata": {
        "id": "GWGl15BCdtXJ"
      }
    },
    {
      "cell_type": "markdown",
      "source": [
        "## **Use Git Command Line**\n",
        "\n",
        "### **1. Clone the HF Repository:**\n",
        "\n",
        "If you haven't cloned the repository to your local machine, do so with:\n",
        "\\\n",
        "Link to my HF home: https://huggingface.co/amirhossein20n/spam_not_spam/tree/main\n",
        "![image.png](https://github.com/amirhnazerii/utils/blob/main/imgs/HF1.png?raw=true)\n",
        "\n",
        "Follow the steps below: \\\n",
        " Make sure you have git-lfs installed (https://git-lfs.com)\n",
        "```\n",
        "C:\\Users\\anazeri> git lfs install\n",
        "C:\\Users\\anazeri> cd .\\HuggingFace\\\n",
        "C:\\Users\\anazeri\\HuggingFace> git clone https://huggingface.co/amirhossein20n/spam_not_spam\n",
        "\n",
        "```\n",
        "\n",
        "\n",
        "### **2. Clone the GitHub Repository:**\n",
        "\n",
        "Do the similar approach as did in the last section now for Git cloning:\n",
        "\n",
        "```\n",
        "C:\\Users\\anazeri> git clone https://github.com/amirhnazerii/utils.git\n",
        "```\n",
        "\n"
      ],
      "metadata": {
        "id": "oUpPe-Z0eJvz"
      }
    },
    {
      "cell_type": "markdown",
      "source": [
        "### **3. Copy the Folder to the Local Repository:**\n",
        "\n",
        "1.   *Navigate to your cloned Git repository directory* and copy the folder\n",
        "\n",
        "2.   Remove **.git** hidden file from the copied folder `spam_not_spam` (HF folder)\n",
        "\n",
        "you want to upload into it.\n",
        "\n",
        "```\n",
        "cp -r /path/to/your/folder /path/to/cloned/repository/\n",
        "```\n",
        "\n",
        "confirm the sucessful cloning:\n",
        "```\n",
        "    Directory: C:\\Users\\anazeri\\utils\n",
        "----                 -------------         ------ ----\n",
        "d-----         8/27/2024  12:57 PM                spam_not_spam\n",
        "-a----         8/27/2024  12:32 PM           3228 Datasets.ipynb\n",
        "-a----         8/27/2024  12:32 PM         126569 Finetune_RoBERTa_TextClassification_LoRA.ipynb\n",
        "-a----         8/27/2024  12:32 PM           1050 Get large file from google drive\n",
        "-a----         8/27/2024  12:32 PM        1580524 how-to-load-kaggle-datasets-directly-into-google-colab.pdf\n",
        "-a----         8/27/2024  12:32 PM         138095 img1.png\n",
        "-a----         8/27/2024  12:32 PM            611 Pip install in conda environment.md\n",
        "```"
      ],
      "metadata": {
        "id": "EVKDCs19nBG8"
      }
    },
    {
      "cell_type": "markdown",
      "source": [
        "### **4. Add, Commit, and Push the Changes:**\n",
        "\n",
        "```\n",
        "C:\\Users\\anazeri\\utils> git add .\\spam_not_spam\\\n",
        "C:\\Users\\anazeri\\utils> git commit -m \"Training parameters for spam_not_spam added - corrected\n",
        "C:\\Users\\anazeri\\utils> git push origin main\n",
        "```\n",
        "#### **Note:**\n",
        "if you mistakenly `git add .` a wrong file/folder, you must delete the file + cashe using:\n",
        "\n",
        "```\n",
        "git rm -f --cached spam_not_spam\n",
        "```\n",
        "\n",
        "\n",
        "\n",
        "\n"
      ],
      "metadata": {
        "id": "7r_ZjU0gk_Sk"
      }
    }
  ]
}