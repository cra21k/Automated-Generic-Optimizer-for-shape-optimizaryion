# Automated-Generic-Optimizer-for-shape-optimizaryion
A handy tool that integrates commercial analysis tools to optimize  given shape

For the automation to work, there are few files and programs that are prerequisite in a computer.

• C++ compiler

• MATLAB

• ANSYS FLUENT

• ICEM CFD

• SolidWorks or any CAD software

• Windows OS (for .bat fles to work)

The whole program can be divided into three segments

1. Batch files

2. Macros

A.1 The Batch Files

Batch file is a windows command file, which executes specific commands on command prompt. There are few ways to implement the batch files in sequential way. The approach sought here is having a master batch file which calls batch file for each different program. 

This allows us to specify certain commands in the specific batch file for a program to carry out and only upon the completion of that the next batch file is called. The batch files itself have comments to assist new user for different options available to use

A.2 Macros/Scripting

Scripting is a way to create scripts of command which when called from shell of the program execute certain set of tasks and terminate. This facility is available in most commercial analysis tools. 

A.2.1 Solidworks

The use of SolidWorks as mentioned earlier is to create a curve from the points, comments in the program indicate where to change the location of the text file to use custom input or highlighting the segment which is used to create curves. This .swp file can be called from the shell to run and a batch file can be use for simpler execution, this method has its flaws and the software might not terminate at times. 

Solidworks has lot of issues with its API. Its far easier for call back of ANSYS components and MATLAB than SolidWorks and its Visual basic based API. It is recommended to switch to much easier macro and batch friendly CAD softwares like CATIA in the future while implementing this code.

A.2.2 ICEM CFD 

The creation of scripts in ICEM and ANSYS is pretty straight forward. The first step in generating a Replay file is to activate the recording of the commands needed to generate the initial block topology model. All steps in the mesh development process are recorded, including blocking, mesh size, edge meshing, boundary condition definition, and final mesh generation. All steps in the mesh generation process are automated from this point on. This replay functionality is found in File>Replay script.http://www.google.co.in/url?sa=t&rct=j&q=&esrc=s&source=web&cd=2&ved=0CCQQFjAB&url=http%3A%2F%2Forange.engr.ucdavis.edu%2FDocumentation12.1%2F121%2FICEMCFD%2Ficmuser.pdf&ei=vyM4Vc2xBceXuASE8oG4Bw&usg=AFQjCNHTmU6lXqJ8M-zw9a37y3zUeWaZOQ&sig2=bIM4TNZaIoibx0eGZ0UxMg&bvm=bv.91427555,d.c2E&cad=rja

If the model is changed then all one needs to do is start recording of the replay script and for the first model all necessary steps needed fro meshing is done and saved to an external file, once save one needs to change the name of replay file being called in the batch file to be changed to the desired file.

A.2.3 ANSYS FLUENT

For the automated scripting of ANSYS FLUENT one needs to use workbench's record journal tool. The process is similar as mentioned for the case of ICEM CFD. 

• One has to start the Workbench interface

• Use CFD FLUENT, and link ICEM CFS mesh file to it

• In FLUENT specify all the conditions, and intialize and carry out the anlysis

• Set up the results to be output 

• Finally stop recording the journal ans save the file

To use it along with automated program, simple change the link and name of the journal ile in the macro

A.2.4 MATLAB Scripts/Other C++ codes

A general matlab code has been written for this case, changes if needed can be made to be the design by acessing the code directly. Comments has been made sufficiently to assist the user. As all the other cases, the name of the files need to be changed in the batch file for this to work.

The comments in the code itself shall be of use in assisting and explaining the use of each function.

A.3 Current Issues

There are few issues with the automation tool created. 

• SolidWorks is definitely going to be a hindrance in the future implementation, thus is advised to be replaced with different CAD software with better API.

• Although .bat files are a convenient implementation, for the end user it is still has a slight learning curve hence it's a good idea to implement a GUI for the same

• The whole automation is not completely universal, but these can be fixed given some time.
