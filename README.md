# PHP SSIS Documentor
PHP script that reads ssis packages, extracts all SQL statements and creates documentation as html pages.

## Set Up The Environment

### Install Command Line Client
First you have to install the tfs command line client on your linux system. Go to Microsoft's [Cross-Platform Command-Line Client- Beginner's Guide](https://msdn.microsoft.com/en-us/library/hh873092.aspx) and download the client. Follow the instructions for installation and accept the EULA.

### Create Workspace

```
$ tf workspace -new Beta1 -collection:http://TFS-SERVER:8080/tfs/DefaultCollection
```

If you find out that you wanted a different name for your workspace, you can rename it with this command:
```
$ tf workspace -collection:http://TFS-SERVER:8080/tfs/DefaultCollection -newname:Documentation Beta1
```

To see a list of all workspaces use
```
$ tfs workspaces
```

Now you have to create a directory and map a part of your collection to that directory:
```
$ mkdir "My Project"
$ tf workfold -map $/"My Project" -workspace:Beta1 "DefaultCollection/My Project"
