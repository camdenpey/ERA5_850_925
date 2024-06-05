**Prerequisites/Setup:**

1. Conda/Anaconda downloaded onto laptop (https://docs.anaconda.com/free/miniconda/)
  
2. Conda environment set up: open conda command prompt

3. Create environment:
   conda create -n <desired_env_name>

- type y and press enter when prompted

5. Activate environment:
   conda activate <desired_env_name>
   
6. Install packages (bold is absolutely required, others optional but recommended):

- (you could do this via conda install <package> and do it individually, but the most recent dependencies will be installed via conda-forge)


- **jupyter lab - conda install -c conda-forge jupyterlab**
   
   - type y and press enter when prompted

- **xarray, netcdf4, dask, scipy, bottleneck - conda install -c conda-forge xarray netcdf4 dask bottleneck scipy (all in one line)**
  
  - type y and press enter when prompted

- m2-base - conda install m2-base (not necessary, but enables use of unix commands)
  
- numpy
  
- pandas
  
- zarr
  
- **cdsapi - pip install cdsapi  (**note: do last**)**
  
  - type y and press enter when prompted
  
7. On the cds application website, make a profile and log in. Go to ‘Profile’ and scroll down to the bottom where the API key is, keep that handy

8. Create API workfile - create a Windows notebook text file with the following:

    url: https://cds.climate.copernicus.eu/api/v2

    key: UID from cds profile : api key from cds profile
   
10. Save it as whatever you feel like in the main user profile (i.e. C:\Users\peyton.camden) as long as it’s a text file, but then once it’s saved you need to rename it to ‘.cdsapirc’ (no quotes)

    - The dot in front is essential

    - Make sure to take out the ‘.txt’ as well
    
12. Download the notebook (suggested: into the directory you plan on downloading the netcdf files into (i.e. C:\Users\peyton.camden\netcdf))


**To open Jupyter Lab and get to the script:**

1. Open conda command prompt and activate the environment: 
    conda activate <desired_env_name>
  
2. cd into the directory you plan on working out of and/or saving the raw NETCDF files to - cd C:\Users\<username>\<folder/directory>
   
- highly suggest making a new folder either through the command line or just in Windows File Explorer so that you don’t work out of the main C:\Users\<username> directory because it’ll make it a MESS
   
3. Open Jupyter Lab by typing jupyter (space) lab and pressing enter

4. Jupyter Lab should open in a browser tab after a second

- If you’re in the right directory, or can navigate to the right directory from the GUI on the left side of the screen, find ‘download_850_925_era5.ipynb’ wherever you saved it and double click it to open the notebook in Jupyter Lab

