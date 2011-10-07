Development and testing was done using Visual Studio 2008 in Windows XP/Windows 7 using 
wxWidgets 2.8.11, OpenCV 2.2, TinyXML 2.6.0, HistLib 0.2 libraries
In theory it is possible to compile/run everything under Linux, but has not been tested.  

External Package Sites:
http://www.wxwidgets.org/
http://opencv.willowgarage.com/wiki/
http://www.sourceforge.net/projects/tinyxml
http://code.google.com/p/opencv-histlib/

Directories:
database - this is where cached files are stored in binary format (everything gets generated automatically, ok to delete)
images - this is where all of the input images reside (do not delete!)
setup - this is where the XML setup files are contained  (do not delete!)
log - all of the log files are saved here in the corresponding database directory (everything gets generated automatically, ok to delete)
src - C++ source files
matlab - Useful Matlab script(s)

Windows Build setup:
Environment variables (right click on My Computer, select properties, go to advanced tab, and click on 'environment variables')
OPENCVDIR = C:\OpenCV2.2
TINYXML = C:\tinyxml
WXWIDGETSDIR = C:\wxWidgets-2.8.11

OpenCV-Histlib should be in the same top-level directory as this packages directory. 

PATH should contain C:\OpenCV-2.2.0\bin

Procedure for adding a new image database:
1. Add new subdirectory in images directory (name can be artibrary)
2. Add images with the naming convention: 'LabelName.SomethingSomething.jpg' where 'LabelName' is the class label
3. In the command prompt (start->run cmd) browse to the folder and type 'dir \b > names.txt' or 
   'ls > names.txt' if the prompt supports linux commands. (this will create a text file with the contents of the directory)
4. Remove any non-image files from names.txt
5. Use the following C++ code to generate the XML files for the setup file:
   wxFileName Names("names.txt");
   CRecognitionDb::GenImageXml(Names);
   This will create a 'output.xml' file with the corresponding xml entries
6. Create a new XML file in the setup directory (make a copy of an existing one) and
   be sure to change the name of the database XML line (<database version="0.1" name="NAME">) to the same name as
   the image subdirectory (same name as the directory from step 2)
7. Remove all of the existing <entry/> tags and replace them with the tags generated in step 5.  