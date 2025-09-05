<div align="center">
  
# SAS.6 NAME

</div>


<img width="1920" height="1080" alt="Architecture" src="https://github.com/user-attachments/assets/f328e4f4-e60f-4280-8038-9f4a9c54aba1" />



# Documentation
The aim is to allow users to download, train, and
use AI models and agents on their mobile phones without difficulty. This is
achieved by taking advantage of the features offered by Linux through the
Termux application. Termux is a powerful tool that provides a Linux environment
on mobile devices, making it possible for users to work with AI directly on their
phones. With Termux, users can access a wide range of Linux capabilities, which
simplifies the process of managing AI models. This setup not only makes AI
technology more accessible but also encourages users to explore and experiment
with AI in a way that is convenient and straightforward, right from the palm of
their hands.


### [Download NAME v1.0.3.apk - Latest Version ](https://github.com/Neural-Agent-Modelling-Engine/NAME/releases/download/v1.0.3/NAME.v1.0.3.apk)

<div align="center" style="max-width: 520px; margin: auto;">
  
![v1 0 3](https://github.com/user-attachments/assets/b00e195e-23db-4c85-b679-be118add19fd)


</div>

---

# Ubuntu Install Script (llama.cpp + Modules)


### 1. **nsetup.sh**

The `nsetup.sh` script initiates the installation process by creating the **NAME** folder in the Termux home directory. The folder is specifically placed at `~/NAME`, serving as the root directory for the subsequent setup steps.



### 2. **ndependencies.sh**

The `ndependencies.sh` script installs essential packages required for command-line builds, model downloads, and model execution. These include tools such as **git, cmake, clang, make, wget, unzip, and aria2**, which ensure smooth compilation and model management.



### 3. **nclone.sh**

The `nclone.sh` script clones the official **llama.cpp** GitHub repository created by **ggerganov**. This repository provides the base code used for compiling and running the models.



### 4. **nbuild.sh**

The `nbuild.sh` script is responsible for compiling the **llama.cpp CLI** inside the directory `~/NAME/llama.cpp/build`. However, the build process may encounter challenges on low-end devices, often leading to warnings and eventual errors during compilation.



### 5. **nselect.sh**

The `nselect.sh` script prompts the user to select one of the three available **TinyLlama models**, each offering different sizes and parameters. Once selected, the model choice is saved in the **model.conf** file for later use.



### 6. **ndownload.sh**

The `ndownload.sh` script reads the chosen configuration from **model.conf** and downloads the corresponding model into the directory `~/NAME/llama.cpp/models`. It utilizes tools such as **wget, curl, or aria2** to efficiently complete the download process.



### 7. **fetch.sh**

The `fetch.sh` script retrieves important files such as **names.h** and **bridge.log** from the official **NAME GitHub organization**. Afterward, it ensures that **name.sh** is executable by applying the `chmod +x name.sh` command.


### 8. **nsummary.sh**

The `nsummary.sh` script generates a detailed summary of the installation process. It outlines the **root directory**, **build directory (CLI)**, the **downloaded model**, and the fetched bash scripts, including **name.sh** and **bridge.log**, providing a clear overview of the setup status.


```bash
bash -c 'DIR=${1:-NAME}; for f in nsetup.sh ndependencies.sh nclone.sh nbuild.sh nselect.sh ndownload.sh nfetch.sh nsummary.sh; do curl -fsSL "https://raw.githubusercontent.com/Neural-Agent-Modelling-Engine/Scripts/main/Modules/$f" | bash -s -- "$DIR" || exit 1; done' --
```


