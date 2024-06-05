# **Prerequisites/Setup:**

1. Conda/Anaconda downloaded onto laptop (https://docs.anaconda.com/free/miniconda/)
  
2. Conda environment set up: open conda command prompt

3. Create environment:
   conda create -n <desired_env_name>

    - type y and press enter when prompted

5. Activate environment:
   conda activate <desired_env_name>
   
6. Install packages (bold is absolutely required, others optional but recommended):

    - you could do this via conda install <package> and do it individually, but the most recent dependencies will be installed via conda-forge


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

8. Create API workfile - create a Windows notebook text file with the following, in this exact formatting:

        url: https://cds.climate.copernicus.eu/api/v2

        key: UID from cds profile : api key from cds profile
   
10. Save it as whatever you feel like in the main user profile (i.e. C:\Users\peyton.camden) as long as it’s a text file, but then once it’s saved you need to rename it to ‘.cdsapirc’ (no quotes)

    - The dot in front is essential

    - Make sure to take out the ‘.txt’ as well
    
12. Download the notebook (suggested: into the directory you plan on downloading the netcdf files into (i.e. C:\Users\peyton.camden\netcdf))


# **To open Jupyter Lab and get to the script:**

1. Open conda command prompt and activate the environment: 
    conda activate <desired_env_name>
  
2. cd into the directory you plan on working out of and/or saving the raw NETCDF files to - cd C:\Users\<username>\<folder/directory>
   
    - highly suggest making a new folder either through the command line or just in Windows File Explorer so that you don’t work out of the main C:\Users\<username> directory because it’ll make it a MESS
   
3. Open Jupyter Lab by typing jupyter (space) lab and pressing enter

4. If you’re in the right directory, or can navigate to the right directory from the GUI on the left side of the screen, find ‘download_850_925_era5.ipynb’ wherever you saved it and double click it to open the notebook in Jupyter Lab.




# **Actually running the script:**

1. In the first cell, enter the latitude and longitude values for the points you’re trying to extract values for, and name them (note: if it’s in quotes/brackets or has commas, leave it)

    - Traditional latitude/longitude conventions apply (see https://cds.climate.copernicus.eu/toolbox/doc/how-to/1_how_to_retrieve_data/1_how_to_retrieve_data.html#retrieve-multiple-variables-or-parameters-via-one-request for more info)
    
    - If you need to add additional sites, add a comma after the end bracket, press enter, and use the same naming and formatting conventions the rest of the sites use
    
    - If you need to remove sites/locations (run only one site, for example):
    
        - Comment out a line (nullify it) by putting # immediately in front of the site you desire to comment out
      
        - If it turns a teal-ish color, you’ve successfully commented it out
      
        - If you need to comment out multiple lines, you’ll need multiple #’s (one for each line)
      
    - Press shift and enter on the keyboard at the same time to run the cell.

2. In the second cell, put the year of data you want to extract in YYYY format next to ‘selected_year =” and the month next to ‘selected_month =’ in a M format (1 for January, it will not let you put 01) and run the cell by pressing shift and enter at the same time again

    - You shouldn’t need to edit anything else for the retrieval cell, but you could to get other data

    - If you want pressure levels that aren’t just 850 and 925mb, or would like to add additional pressure levels to those, make adjustments next to ‘pressure_level’ appropriately
    
        - Don’t remove the brackets unless you only want one single level
      
        - Use the same formatting conventions as existing levels
      
        - Levels you can use can be found in the ERA5 documentation (https://confluence.ecmwf.int/display/CKB/ERA5%3A+data+documentation#heading-Levellistings)
    
    -  Can similarly force change anything in the retrieval cell to get different data, let me know if you need to do that because there’s endless possibilities

4. Run the cell. You’ll know everything is working right if a pink box appears underneath the retrieval cell with messages along the line of ‘welcome to CDS!’ and ‘request is queued’

5. Congrats, you should have your data now!
   
    - Make sure you know what directory the .nc file is saved to, because if you goofed up the first part, you’ll have to tweak this next part.

5. To convert to a CSV, you’ll have to change the local_storage_directory to wherever you’re running the notebook from, whether it’s the same as where you saved the NETCDF files or not.

    - If the NETCDFs are being saved to a different location than where the notebook is running from, change the netcdf_dir accordingly.
  
    - Unless you change where you want the CSVs to save to, you shouldn’t need to change the csv_dir, but do whatever you want

6. shift + enter, shift + enter, shift + enter (run the cells)

7. Hooray! If you didn’t get any error messages, the CSV files should be in the S drive or wherever else you saved them!



# **To close Jupyter Lab in a way that’s least likely to break it:**

1. Go to the ‘Kernel’ tab at the top

2. Click ‘shut down all kernels’

3. Go to the ‘File’ tab at the top

4. Click ‘Shut Down’ (do NOT log out)

5. X out of browser

6. In the command prompt that you opened Jupyter from, type exit and press enter

7. Ta da

