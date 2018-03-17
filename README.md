# Jupyter-arcpy
Setting Up Jupyter notebooks for ArcGIS 10.X with a 64bit installation

**1: Download and install ANACONDA [(Select 2.7 python and 64 bit for ML installation)](https://www.anaconda.com/download/#windows)**

NOTE: DO NOT CHECK ANYHTING UNDER THE ADVANCED OPTIONS TAB DURING INSTALL (This will destroy your ArcGIS Installation)

**2: Add Community package management system**

Start "Anaconda Prompt" with admin privileges
```
conda config --prepend channels conda-forge
```
//START HERE IF YOU HAVE ANACONDA INSTALLED

**3: Create ArcPy environment and install dependencies**
Check to see if you have an arcpy setup already
```
conda info --envs
```
Setup ArcPy Environment
```
conda create -n arcpy python=2.7
conda activate arcpy
conda install jupyter
conda install numpy==1.9.3
```

**4: Link ARCGIS with ArcPy environment**
(You need to have a local installation of a licensed ARCGIS application)
create a arcpy.pth file in the environment site-package folder: “C:\ProgramData\Anaconda2\envs\arcpy\Lib\site-packages\”
Open the .pth file and add the following lines:
```
# .pth file for arcpy
C:\Program Files (x86)\ArcGIS\Desktop10.X\bin64 
C:\Program Files (x86)\ArcGIS\Desktop10.X\arcpy
C:\Program Files (x86)\ArcGIS\Desktop10.X\Scripts
```

NOTE: eplace “X” in the path with the ArcGIS version installed on your computer and save the file

**5: Link a IPython kernel to the arcpy environment**
add kernel to environment
```
python -m ipykernel install --name arcpy --display-name "Python (arcpy)"
```
deactivate arcpy environment
```
conda deactivate
```
**6: Start Jupyter environment by running the command**

change directory to your notebook folder location
```
jupyter lab
```
