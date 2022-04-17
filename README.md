# sdeproject
Neural Data Completion for Relational Databases
This is a replication of official repository of ReStore https://github.com/DataManagementLab/restore?msclkid=0979471ebdac11ec8c281947118c33d5 

# Go to your google drive and replicate this repository
!git clone https://github.com/DataManagementLab/restore.git

# Make destination forled if you wish to use persistent storage and move the code to desired folder
!mkdir 'gdrive/MyDrive/SDE/' \n
!mv restore 'gdrive/MyDrive/SDE/'
!ls 'gdrive/MyDrive/SDE/' # Check

# Copy the datasets
!wget https://public.opendatasoft.com/explore/dataset/airbnb-listings/download/?format=csv&timezone=Europe/Berlin&lang=en&use_labels_for_header=true&csv_separator=%3B
!wget http://homepages.cwi.nl/~boncz/job/imdb.tgz

