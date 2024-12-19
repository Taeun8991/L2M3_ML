# **How to Run the ML Model**

##  **0. Prerequisites**
To run the ML model, you need to prepare several essential files in advance. Below is a list of required files and their descriptions:

1. **Metal Feature File**:  
   - A **.csv file** containing features for the metals used in the model, such as **atomic weight**, **electron affinity**, and other relevant properties.  

2. **MOF Structure Files**:  
   - A directory containing **.cif files** of the MOFs (Metal-Organic Frameworks). The features of MOFs will be extracted from these structure files.  

3. **Metal Type and Linker File**:  
   - A file that identifies the **metal type** and **linker SMILES** used in each MOF, which is extracted from the **.cif files**.  

4. **Target Property File**:  
   - A file containing the **target property values** for each MOF. This file will be used to create the **y vector** for training the ML model.  

---

##  **1. Feature Extraction**
The feature extraction process can be done using the **`feature_extraction.ipynb`** notebook located in the `feature_extraction` directory.  

### 🛠 **How to run feature extraction:**
1. **Prepare the MOF .cif files**:  
   - Make sure you have a directory containing all the **.cif files** you want to extract features from.  

2. **Run the feature extraction script**:  
   - Open **`feature_extraction.ipynb`** in Jupyter Notebook or any compatible environment.  
   - Specify the path to the directory containing the **.cif files**.  
   - Run the notebook to extract features.  

###  **Outputs:**
- **X vector list**: A list containing the extracted features for each MOF.  
- **Refcode list**: A list of reference codes corresponding to each row of the X vector.  

---

##  **2. Running the ML Model**
Once you have extracted the necessary features, you can proceed with running the machine learning model.

###  **Steps to run the ML model:**
1. **Create the Y vector**:  
   - Use the **Refcode list** obtained from the feature extraction process to match the corresponding target property values from the **Target Property File**.  
   - This process will generate the **Y vector**, which contains the target property values for each MOF.  

2. **Select an ML model**:  
   - Choose the ML model you want to use for training. Options may include models like **Linear Regression**, **Random Forest**, **Gradient Boosting**, etc.  

3. **Train and test the model**:  
   - Split the data into a **training set** and a **test set**.  
   - Train the model using the training set and evaluate its performance on the test set.  

4. **Hyperparameter tuning (optional)**:  
   - For better model performance, you can apply **GridSearchCV** to tune the hyperparameters.  
   - This step is optional but recommended for optimizing model performance.  
