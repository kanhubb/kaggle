# kaggle
this repositories is all my kaggles Notebooks

this the link to all the dataset : 
https://drive.google.com/drive/folders/1BDKpRRBDroeaRlxhfsD2dpiIZNmtohvt?usp=sharing

after that you just need to adapt the paths to your configuration :

i use a code at the begigning of all my notebooks, it can connect automatically to my data in google colab / kaggle / local configuration.
``` python
import numpy as np
import pandas as pd
import sys
import os
# Define the base path depending on the environment
nameCompetition = "equity-post-HCT-survival-predictions"
if 'google.colab' in sys.modules:
    from google.colab import drive
    drive.mount('/content/drive')
    base_path = "/content/drive/MyDrive/data/kaggle/" + nameCompetition
    print("Google Colab detected. Base path set to:", base_path)
elif "KAGGLE_KERNEL_RUN_TYPE" in os.environ:
    base_path = "/kaggle/input/" + nameCompetition
    print("Kaggle environment detected. Base path set to:", base_path)
else:
    base_path = "/mnt/g/Mon Drive/data/kaggle/" + nameCompetition
    print("Local environment detected. Base path set to:", base_path)
# List all files in the base path directory
if os.path.exists(base_path):
    print(f"Contents of the directory '{base_path}':")
    for dirname, _, filenames in os.walk(base_path):
        for filename in filenames:
            print(os.path.join(dirname, filename))
else:
    print(f"The directory '{base_path}' does not exist.")
```

after that you just need to create an environement and intall the dependencies .
