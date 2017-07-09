# RMI
### File transfer using Java Remote Method Invocation

A file sharing system is built using Java Remote Method Invocation.
This system contains two types of entities : a file server and a client. 
The client is able to upload files to the server, download a given file from the server, explore files and directories, create or delete directories.

Steps to use this code on command line:  
1. Compile all the 4 classes using the command  
`javac ClassName.java`

2. Run the server class RMIServer.java, pass a portnumber available on your local machine to run the server on.  
`java RMIServer.java start <portnumber>`  
*Note: On running the server, a new directory is automatically created in your C: called "ServerStorage" which acts as the root storage directory for the server. The client can upload a file to, download a file from, or make new directories inside C://ServerStorage. The client can use other locations too, since no security has been provided to prevent the client from doing so in the code. But please avoid such path names.*

3. Set the server location (local host and port number) to your environment variables.  
`set SERVER_PORT=127.0.0.1:<portnumber>`

4. Run the client code:  
  - To upload a file  
`java RMIClient.java upload <path_on_client> <C:/ServerStorage/filename>`

  - To download a file (FileNotFoundException thrown if file doesnot exist).  
`java RMIClient.java download <C:/ServerStorage/existing_filename_on_server> <path_on_client/newfilename>`  

  - To list the directories and file present on the server.  
`java  RMIClient.java dir <C:/ServerStorage/path_existing_directory_on_server>`

  - To create a new directory.  
`java RMIClient.java mkdir <C:/ServerStorage/new_directory_name>`

  - To delete an existing directory.  
`java RMIClient.java rmdir <C:/ServerStorage/existing_directory_name>`

  - To delete a file.  
`java RMIClient.java rm <C:/ServerStorage/existing_file_name>`

5. To shutdown the client.  
`java RMIClient.java shutdown` 
