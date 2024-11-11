How to Set Up GTAM Services Locally
This guide explains how to set up GTAM services locally, which involve more than 15 modules based on both Gradle and Ant build systems. While these modules are deployed independently, the common module (which contains the DAO layer for DB interactions) is shared across all services. Follow the steps below to set up and build the required modules locally.

Pre-Requisites
Ensure that Gradle and Ant are correctly installed and configured on your local machine.
The common module should be built first as it contains necessary dependencies for other modules.
Make sure you have access to the necessary credentials or tokens (if needed) for certain configurations.
Step 1: Build the Common Module
The common module contains all the required DAO layer classes for database interactions. It should be built first.

Navigate to the common module directory.
Use the Ant plugin to build the common module.
bash
Copy code
ant build
This will build the common module and make it available for use by other modules.
Step 2: Add Build File for Other Modules
If you need to run any other specific module locally, follow the steps below:

Add the corresponding build file for the desired module in Ant.

Navigate to the respective module’s directory.
Update the Ant build file for the module and ensure that the appropriate user-specific tokens or configurations (such as .tok files) are set.
Tokenize the module using Ant:

Run the tokenization task in Ant to replace the necessary values in the build files with the corresponding tokens.
bash
Copy code
ant tokenize
This will replace the tokens in the configuration files (such as .xml and .properties files) and generate all the required files.

If the module has any JMS session-specific configurations or other environment-specific settings within the .obj file, comment them out for this local setup. (Note: The setup for the .obj file is not covered in this guide.)

Step 3: Build the Specific Module Using Gradle
Once the common module and other configurations are set up, follow the steps below to build and deploy the specific module:

Navigate to the module directory you want to set up.
Run the Gradle build command to build the module:
bash
Copy code
gradle build
This will build the module, and you should see all the classes and resources being moved to the cbkbuild folder.
If the files are not generated in the cbkbuild folder, ensure that your configuration folder is marked as a resource folder so that the build system recognizes it correctly.
Step 4: Verify Setup
After building the module with Gradle, verify the following:

All generated classes and resources should be in the cbkbuild folder.
If any resources are missing, recheck the build process and configuration paths.
Step 5: Trigger the Main Class
Once the module is built and the setup is complete:

Trigger the main class to run the service.

This will initiate the module and allow you to test its functionality.
Trigger a specific handler (Optional):

Instead of running all handlers, you can trigger a specific handler by specifying the handler name in the program’s arguments.

Additional Notes
Dependencies: Ensure that the dependencies between modules are correctly set. For example, if Module A depends on Module B, Module B must be built and deployed before Module A.
Tokenization: Always remember to replace any environment-specific tokens with appropriate values for your local setup.
Environment-specific Configurations: If any modules have environment-specific configurations (like JMS or database settings), these need to be manually adjusted or commented out to fit your local setup.
By following these steps, you should be able to successfully set up GTAM services locally and trigger the desired handlers for testing and development.

If you encounter any issues or need further clarification, please reach out to the development team for support.
