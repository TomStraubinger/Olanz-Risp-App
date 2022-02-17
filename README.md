# Olanz-Risp-App
R Shiny App for simulation of Olanzapine and Risperidone dosing
================================================================


Installation Instructions
-------------------------
The application was created using the R package, Shiny. Shiny gives one the ability to utilize the computing power of the statistical language, R Programming, in a highly flexible, interactive web application.
The population pharmacokinetic model used for the application is based on the published model of Bigos et. al. It is a one compartment, population pharmacokinetic model. Sex, race, and smoking status were identified as covariates on drug clearance, and thus were included in the application. 


### Step 1: Download and Install R Programming and RStudio.


R Programming Link: https://cran.rstudio.com/

Rstudio link: https://www.rstudio.com/products/rstudio/download/

### Step 2: Install All Required Packages 

Open RStudio and copy and paste the following in the console and run:

install.packages(c("Shiny", "deSolve", "plyr", "reshape2", "grid", "dplyr", "magrittr", "tidyr", "LambertW", "DT")) 


### Step 3: Unzip folder and open server.R or UI.r file in RStudio.

Right click on zipped folder and click “Extract all” and choose destination.

Navigate to folder and open either the server.R file or UI.r file in RStudio. If RStudio is the default program to open R scripts just double click on file. If R studio is not the default program, right click the file and use the “Open with” option.

Using the application
----------------------
### Initial Dosing Tab
 
You can either simulate for a specific dose, target a specific trough concentration, or target a specific receptor occupancy at the steady state trough. Under the “Parameters” tab, a recommended dose amount will be generated to achieve the target. 
Select check boxes accordingly, based on whether or not the patient is a smoker, male, and/or African.
On the bottom, when the CATIE study checkbox is selected, it will show you results from the CATIE study and how well the model predicted each individual’s concentrations. In the final app, instead of CATIE study subjects, this feature will be able to display concentrations from patients, if plasma levels are measured.


### Adaptive Dosing Tab

On the navigation bar at the top of the app, there is a tab labelled “Adaptive Dosing”. Click it to navigate to the adaptive dosing page.
In the initial dosing page, drug clearance is predicted based on what the mean clearance would be in patients with certain characteristics (sex, race, smoking status). However, not all subjects with the same characteristics will have the exact same drug clearance. Thus, the adaptive dosing feature allows you to enter in a blood draw time and measured concentration after the first dose was given, and an updated prediction for clearance will be calculated. This updated clearance is patient specific.
With the better informed prediction for clearance, you can now perform all the same tasks as in the previous tab: simulate for a specific dose, target a specific trough concentration, or target a specific receptor occupancy at the steady state trough.
The blue lines shows the profile from the original dose and the green from the adjusted dose. 
