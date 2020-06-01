Scaffolding: Scaffolding, in general means a structure that supports for the creation of a new  object. Large software projects often have the same project structure like the folders for source code, packages, etc. They often have a large amount of boilerplate code and the code for initial setup of the project. In project generation, scaffolding tools simplify the creation of projects by automatically generating the folder structure, files and other prerequisites required by the project in the beginning itself.
Scaffolding thus helps a developer to concentrate more on developing the project rather than performing the tedious and repeated tasks such as minifying stylesheets, package updates, dependencies management, etc.
Yeoman and Slush are examples of such scaffolding tools.
Yeoman: Yeoman is the leading scaffolding tool for web applications. It uses a generator ecosystem to achieve the task of scaffolding.  A generator is more like a blue print of what is to be done when a new project is created. It contains information like what all folder structures are to be created, required libraries and dependencies etc. Yeoman also provides a playground to host web parts for testing.
Yeoman provides a large number of generators over 5600+ for setting different types of projects like Jhipster for SpringBoot + Angular/React projects, office for creating MS Office projects using any text editor, rn-toolbox for React-Native projects, Generator SharePoint for SPFx etc. Generators are installed using npm.
Yeoman generators run interactively, guiding the developer through a series of questions for the required configuration. The choices made by the developer determine the physical structure and components that are to be installed by Yeoman.  
Yeoman workflow comprises of three types of tools when building a web application:
•	yo – The scaffolding tool : yo scaffolds a new application by writing the build configuration, creating the initial folder structure and installing the dependencies that are required for the application. So, Yo provides an easy way to create all of the boilerplate code that is needed to start the project.
•	gulp – the build tool : Gulp is a popular choice for build tool. It is a tool for automation tasks such as minification (a process of removing unnecessary characters like white space, new line, comments etc from source code of markup languages without changing the intended functionality), compilation, linting (a process of running a program that marks any potential errors like syntax errors or incorrectly spelled variable names etc) and packaging of application for preview, testing and deployment.
•	npm – the package management tool: Yeoman uses npm and bower to install the generator’s required packages. npm is a package manager for Javascript. npm registry is an online database of public and private-paid packages.

The package manager is a collection of software tools that install, upgrade, configure or delete the computer programs in a consistent manner. Packages contain metadata, such as the software's name, description of its purpose, version number, vendor and a list of dependencies necessary for the software to run properly. Upon installation, metadata is stored in a local package database. Package managers typically maintain a database of software dependencies and version information to prevent software mismatches and missing prerequisites. It eliminates the manual installations and updates.
Installation:
@microsoft/generator-sharepoint is the generator used to set up a client-side webpart project in Sharepoint with defaults and we have to install it from npm.
Yeoman requires node and npm to be installed.  Node.js of version 6 or higher, npm 3 or higher is required.
node --version && npm --version
If node is not installed, we can install it from the Node Installation Page. Installation of node generally installs both node and npm. If only npm is not installed, we can install it by using the following command:
npm install --global npm@latest
To install gulp, run the following command in the command line :
npm install gulp -g
First, we have to install yo using npm :
npm install -g yo
To check the successful installation of yo, run the command “yo” in the command prompt. It shows an output as below : 
 
To check the version of yo on our system, run command “yo –version”.	
 
“yo doctor” command helps in troubleshooting common issues that could prevent Yeoman from working correctly. 
 
If yo doctor command is not found, we can install the yeoman doctor from npm by using npm i yeoman-doctor command.
Once we are done with the installation of yo, we then install the generator required for our application. For a SharePoint application, Yeoman SharePoint generator is used to scaffold new client-side solution projects that enables developers to build, package and deploy SharePoint solutions. 
npm install -g @microsoft/generator-sharepoint		
To know the available options for the installed generator, run the help command:
 
The generator asks a series of questions like the name of the component, description of the component, targeted framework, environment etc.
Use the generator to scaffold out a new SharePoint app:
Create a folder where the generator will place all the scaffolded files and set it as the current working directory: 
mkdir hello-world && cd hello-world
To create the scaffolded files, call yo on the command line and pass the name of the generator to it as follows: 
yo @microsoft/sharepoint
The generator asks a series of questions to create the required application. Yeoman will automatically scaffold the app and install the packages, dependencies specific to the selected options.


 
The following is the folder structure generated by the Yeoman after scaffolding:
 
src is the parent directory for our web application. package.json contains the list of packages installed along with their version. node_modules contain the packages and dependencies installed.
To serve code for testing in the browser, run the following command in the terminal: 
gulp serve
It automatically launches the local sharepoint workbench in the browser. “gulp serve --nobrowser” command will not automatically launch the workbench. To build all the packages, “gulp build” is used. To create a new build and minify the required assets, “gulp bundle” command is used.
“gulp package-solution” command creates the solution package (.sppkg) in sharepoint\solution folder. 





