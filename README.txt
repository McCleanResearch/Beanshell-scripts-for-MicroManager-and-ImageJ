Summary: This repository contains a miscellaneous assortment of scripts that are useful with ImageJ or Micromanager.

--------------------------------------------------------------------------------------------------------------------


-The "ControlRelays.bsh" beanshell script can be used to control an RS81 relay switch board from "ControlAnything."
The RS81 board simply opens and closes switches, and this script can be used to send those open/close messages.

-The "Intro_to_beanshell.bsh" beanshell script is self explainatory. It performs some simple arithmetic and then prints the output. 
It designed so that people that are new to Beanshell could read it, run it, and get a sense for how to use the language
without a formal introduction.

-The "simple_micro-manager_operations.bsh" tests that Micromanger can command the microscope to take an image, process
 the image, analyze the image, save results about the analysis, save the image, write the results to a .csv file,
control the microscope stage, and send messages to the microcontroller. It is useful for troubleshooting and it is useful
as a reference for writting new scripts.

-The "callScriptFromScript.bsh" beanshell script does what it says. It sets two variables for the new script, and then calls it.

-Together, the "TrackMate1_script.bsh" and the "TrackMate1_configurationFile.xml" can be used to find the brightest cells in a stack
of images. It was originally created for a BME400 project to characterize where fluorescent cells were in the z-plane of a custom 
microfluidic channel. I also included "TrackMate1_exampleOutput.csv" to show an examplary output.

	Step 1:
	Move all of the .tif stacks to be analyzed into a single directory.

	Step 2:
	To run the script, open Fiji>Plugins>Macros>Record.
	Click the rectangle (or anything really), select Record:Beanshell, then click "Create"
	Then, open the attached .bsh script through File>Open

	Step 3:
	Run the Script.
	Follow the prompts

	Step 4: 
	Analyze the data. Make a nice graph :)
	Note that the ResultsTable created through FIJI will have column headers, but the CSV file will not. The column headers are
	Stack Name, Track_ID, Brightest Frame for that track, median intensity of brightest spot in that track, X_Position of that spot, 	 Y_Position of that spot 
	
	OPTIONAL- You could also create your own trackmate.xml file to set different spot thresholds and track thresholds. 
	NOTE- When analyzing your data, note that I set the height of each pixel to 3.333 microns and the width to 1 micron. These are 		not realistic values, but they bias the tracking against vertically moving tracks (which was useful in the original 			implementation). For unbiased tracking, use: "IJ.run(imp, "Set Scale...", "distance=1 known=1 pixel=1 unit=µm");"
