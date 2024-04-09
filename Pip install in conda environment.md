## Pip install packages in conda environment

1. Run `conda create -n venv_name` and
2. `conda activate venv_name`, where venv_name is the name of your virtual environment.
3. Run `conda install pip`. This will install pip to your venv directory.
4. Find your anaconda directory, and find the actual venv folder. It should be somewhere like `/anaconda/envs/venv_name/`.
5. Install new packages by doing `/anaconda/envs/venv_name/bin/pip install package_name`.

content from Jules Gagnon-Marchand.
ref: https://stackoverflow.com/questions/41060382/using-pip-to-install-packages-to-anaconda-environment
