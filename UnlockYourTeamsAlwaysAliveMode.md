In file "MakeYourTeamsStatusAlwaysAlive.md", the script works but how to stop it before it reaches the execution time you have given in input? Follow these key steps
1) Open Task Manager.
2) In the "Process" tab you should find a process named "Microsoft Windows Based Script Host"... this is probably the process that is executing your VBS Script.
To be sure, or if you have more than one process named "Microsoft Windows Based Script Host", you can do this:
3) In the header bar, right-click on "Name" (the name of the processes), and flag "Command line", so that a new column appear with name "Command line" and shows which is the command line that has started the processes.
4) In this column you should see the path and the name of your Script.
5) Then select the process and kill it.
