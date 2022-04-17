# sdeproject
  Neural Data Completion for Relational Databases  

# Go to your google drive and replicate this repository
!git clone https://github.com/DataManagementLab/restore.git  
# Make destination forled if you wish to use persistent storage and move the code to desired folder
  !mkdir 'gdrive/MyDrive/SDE/'  
  !mv restore 'gdrive/MyDrive/SDE/'  
  !ls 'gdrive/MyDrive/SDE/' # Check  

# Install necessary packages
!pip3 install --upgrade setuptools  
!pip3 install --upgrade pip  
!pip install paramiko  
!pip install pandas  
!pip install numpy  
!pip install tables  
!pip install --no-binary :all: nmslib  
!pip install xgboost==0.90  
!pip install numba  
!pip install scp  
!pip install torch==1.5.1+cu101  
!pip install torchvision==0.6.1+cu101 -f https://download.pytorch.org/whl/torch_stable.html  
!pip install jupyter  
!pip install matplotlib  
!pip install seaborn  
!pip install sklearn  
!pip install networkx  
!pip install spflow  
!pip install nmslib  
# go to the repository created 
%cd 'gdrive/MyDrive/SDE/restore'  

# Download the datasets
!wget https://public.opendatasoft.com/explore/dataset/airbnb-listings/download/?format=csv&timezone=Europe/Berlin&lang=en&use_labels_for_header=true&csv_separator=%3B  
!wget http://homepages.cwi.nl/~boncz/job/imdb.tgz  
Now move the dataset to desired folders and make sure to use the path properly in all executions  

# preprocess the dataset normalize and generate HDF files
!python3 completion.py --preprocess --dataset airbnb --raw_data_directory ../research-data/incomplete-db/airbnb/all-raw --normalized_data_directory ../research-data/incomplete-db/airbnb/preprocessed  
!python3 completion.py --preprocess --dataset imdb --raw_data_directory ../research-data/incomplete-db/imdb/all-raw --normalized_data_directory ../research-data/incomplete-db/imdb/preprocessed  
!python3 completion.py --generate_hdf --dataset airbnb --normalized_data_directory ../research-data/incomplete-db/airbnb/preprocessed --hdf_data_directory ../research-data/incomplete-db/airbnb/hdf_preprocessed  
!python3 completion.py --generate_hdf --dataset imdb --normalized_data_directory ../research-data/incomplete-db/imdb/preprocessed --hdf_data_directory ../research-data/incomplete-db/imdb/hdf_preprocessed  

# Generate commands for experiments
!python3 exp_commands.py  

# For generation of graphs follow the colab colde available at https://colab.research.google.com/drive/1bwKTBs7SjeLWukKBL2559ynaLKVg6dW3?usp=sharing 

# This is a replication of official repository of ReStore
