Authors and Contributors:
Vincent P. Heuring, Ann Root, Robert Kanick, Shane Neuville, Ross Zwisler and
Michael Wilson
Department of Electrical and Computer Engineering
University of Colorado-Boulder
Boulder CO 80309-0425

README-FIRST.txt - This file describes how to download and run ARCTools on
your platform.

README.txt - This file describes how to use the ARCTools program.

README-INSTRUCTIONS.txt - This file lists all the instructions supported by
ARCTools.

DOWNLOADING ARCTools
Download the directory containing the highest verison of ARCTools.  The
directory will contain the following items:
 - A jar file (which is the ARCTools program).
 - A number of readme files (described above).
 - A directory called 'examples', containing a number of sample ARC programs.
The jar file will have a name like this: ARCToolsvX.Y.Z.jar
Where X, Y and Z are integers.  A complete example is: ARCToolsv1.2.3.jar

INSTALLING ARCTools
ARCTools has no installation associated with it.  You only need to have the
Java Runtime Environment (Java) installed on your platform in order to run
ARCTools.

JAVA RUNTIME ENVIRONMENT
PC/Unix users require Java Runtime Environment version 1.4 or higher and Macintosh
users require MJ2.0 or higher.  The Java Runtime Environment is free and can be
download from the Sun Developer Network website: http://java.sun.com/

For information on supported platforms, and to download the Java Runtime
Environment for your platform, see http://java.sun.com/ for PC/Unix users, and
http://www.apple.com/macosx/features/java/ for Macintosh users.

RUNNING ARCTools
PC, MAC and some Unix users running the latest version of Java should be able
to run ARCTools by simply double clicking the jar file. If this does not work
then you must run ARCTools through the command line.

RUNNING ARCTools FROM THE COMMAND LINE
If you are using Java version greater than 1.1, then the simplest way to run
ARCTools from the command line is to navigate the directory containing the
ARCTools jar file and type a command like this:

java -jar ARCToolsvX.Y.Z.jar

Please note that X, Y and Z represent integers that must be replace by the
integers appearing in your version of the ARCTools jar file. For example, if
your jar file is named ARCToolsv1.2.3.jar and you have nagivated to the
directory containing the jar file, then use this command:

java -jar ARCToolsv2.0.3.jar


Users using Java version 1.1 must use the 'jre' command/program as follows:

jre -cp ARCToolsvX.Y.Z.jar MainClass

For example, if you are in the directory containing ARCToolsv1.2.3.jar, you
would type:

jre -cp ARCToolsv1.2.3.jar ARCTools.ARCSim

Please see your java documentation for more details for running jar files from the
command line.
