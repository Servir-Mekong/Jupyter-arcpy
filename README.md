# Jupyter-arcpy
Setting Up Jupyter notebooks for ArcGIS

1: Download and install ANACONDA
https://www.anaconda.com/download/#windows
*For windows users do not add to path

2: start Anaconda prompt in admin privilege 
conda config --add channels conda-forge (THIS IS A PACKAGE MANAGEMENT)

//START HERE IF YOU HAVE ANACONDA INSTALLED

3: Create ArcPy environment and install dependencies
```
conda create -n arcpy python=2.7
conda activate arcpy
conda install jupyter
conda install numpy==1.9.3
```

4: Link ARCGIS with ArcPy environment (You need to have a local installation of a licensed ARCGIS application)
create a arcpy.pth file in the environment site-package folder: “C:\ProgramData\Anaconda2\envs\arcpy\Lib\site-packages\”
Open the .pth file and add the following lines:
```
# .pth file for arcpy
C:\Program Files (x86)\ArcGIS\Desktop10.X\bin 
C:\Program Files (x86)\ArcGIS\Desktop10.X\arcpy
C:\Program Files (x86)\ArcGIS\Desktop10.X\Scripts
```

Replace “X” in the path with the ArcGIS version installed on your computer and save the file

Link a IPython kernel to the arcpy environment
```
python -m ipykernel install --name arcpy --display-name "Python (arcpy)"
```

```
deactivate arcpy environment
```
```
conda deactivate
```
Start Jupyter Lab environment by running the command
```
Jupyter lab
```
