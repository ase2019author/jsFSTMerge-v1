jsFSTMerge v1
========
A semistructured merge tool for JavaScript applications.

Compilation
-----------
This project uses Gradle to manage all dependencies and versioning. 

Installation
-------------
Double-click on the jar from the [/installer](https://github.com/ase2019author/jsFSTMerge-v1/tree/master/installer) folder.
In case double-click does not work, install with the command 
`java -jar s3mInstaller.jar`

Usage
-------------

Usage data (such as the number of detected conflicts, number of merged scenarios, and more useful details for studying the benefits and drawbacks of the tool) is stored in the `$HOME/.jfstmerge` folder.  A summary of collected statistics that might help one decide to continue using the tool is available in the `jfstmerge.summary` file.

#### Running with git

After installation, the tool is automatically integrated with git, with no need for further configuration. Then every time you invoke the `git merge` command, the tool is executed.

#### Running standalone

Use the jar from the [/binary](https://github.com/ase2019author/jsFSTMerge-v1/tree/master/binary) folder, or from the installed folder.

* Merging 3 files:

  `java -jar pathto/jFSTMerge.jar -f "mine" "base" "theirs" -o "output"`

Where *mine*, *base*, *theirs* and *output* are filepaths.
The attribute -o is optional, if omitted, *theirs* is used as the output file.

* Merging 3 directories:

  `java -jar pathto/jFSTMerge.jar -d "mine" "base" "theirs" -o "output"`

Where *mine*, *base*, *theirs* and *output* are directory paths.
The attribute -o is optional, if omitted, *theirs* is used as the output directory.

<!-- 
For integration with git type the two commands bellow:

   `git config --global merge.tool jfstmerge`
   
   `git config --global mergetool.jfstmerge.cmd 'java -jar pathto/jFSTMerge.jar -f \"$LOCAL\" \"$BASE\" \"$REMOTE\" -o \"$MERGED\"'`

Then, after the "git merge" command detects conflicts, call the tool with:

   `git mergetool -tool=jfstmerge`
-->
