In order to generate and work with LiPD files in the GeoChronR package we need to install Python, R, and the necessary packages into both environments.

## Installing R and RStudio

1. Download R from the [Comprehensive R Archive Network](https://cran.cnr.berkeley.edu/)
2. Follow prompts to install R
3. Download [RStudio](https://www.rstudio.com/products/rstudio/download/#download)
4. Follow prompts to install RStudio

## Installing the GeoChronR and Dependent Packages

1. Open RStudio
2. Install the devtools package and load it into the R session:

   ```
   install.packages("devtools")
   library(devtools)
   ```

3. Install the pcaMethods package:

   ```
   source("https://bioconductor.org/biocLite.R")
   biocLite("pcaMethods")
   ```

   If it asks to update any packages, don't allow it. It should continue with the installation process with less headache down the road.

4. Install the GeoChronR package:

   ```
   install_github("nickmckay/GeoChronR")
   ```

   This can take a while since the GeoChronR package depends on a lot of other packages which will also be installed in the process.

5. Load the GeoChronR package into the R session and run initial setup:

   ```
   library(geoChronR)
   setupGeoChronR()
   ```

6. Install LiPD Utilities and load the package into the R session:

   ```
   install_github("nickmckay/lipd-utilities", subdir = "R")
   library(lipdR)
   ```

   If you get an error saying that `install_github` is not a function in R run the `library(devtools)` command again and retry the installation.

If you plan on doing your age modeling directly through GeoChronR then you will also need [bacon](http://chrono.qub.ac.uk/blaauw/), [clam](http://chrono.qub.ac.uk/blaauw/), or [Bchron](https://cran.r-project.org/web/packages/Bchron/index.html).

We're now up and running with the GeoChronR package and can get to time uncertainty work! Let start with some [examples](https://uwprod-my.sharepoint.com/personal/fastovich_wisc_edu/_layouts/15/guestaccess.aspx?guestaccesstoken=0bUdE7bR4dhNzP18RurlRle7ZLMsO%2frkYwDPrSdxfgM%3d&folderid=2_0cf27dc073eec4cff93e122123c7f4a92&rev=1) first.

Feel free to [read up](https://uwprod-my.sharepoint.com/personal/fastovich_wisc_edu/_layouts/15/guestaccess.aspx?guestaccesstoken=lHdqzvZzp%2bIB1HXqKTIFjdLYU4JsDrI2mq3TysnqU6o%3d&folderid=2_11c28acdfb2b74a618e7aa38c9b88e5b1&rev=1) on what work is possible with GeoChronR.

---

If you've enjoyed this lab and plan on doing some more work with GeoChronR in the future you'll need a few more things to get up and running with your own data. Currently the only way to generate LiPD files is using a template provided by LinkedEarth. Let's get started by installing Python and the LiPD utilities.

## Installing Python and LiPD Utilities

1. Download [Python](https://www.python.org/)
2. Follow prompts to install Python
3. Open the Python environment
   * In Windows this will be the program named **Python X.XX**
4. In the Python window type:

   ```
   pip install lipd
   ```

   If the command above does not work (it may not for Python 3.6+ users) try:

   ```
   pip3 install --egg lipd
   ```

   * If Python is giving you an error saying `pip` is not a recognized command you need to follow a few extra steps which worked for me, but mileage may vary.
      1. Locate the Python installation directory, its often located in **C:\Users\USERNAME\AppData\Local\Programs\Python\PythonXX-32**
      2. Go into the *Scripts* folder
      3. While holding Shift on the keyboard right click anywhere within the *Scripts* folder and select **Open Command Prompt window here**
      4. With Command Prompt open try the commands above again

With Python installed we can proceed to make our own LiPD file and work with it in the GeoChronR package. The instructions for this process can be found at the [LinkedEarth wiki](http://wiki.linked.earth/Creating_a_LiPD_file). LinkedEarth recommends using a Python interface, however if you don't have one you don't need to install one. You can  open the program on your computer named **Python X.XX** and proceed with the code as they have written it.
