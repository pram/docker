* Java 8 JDK on Windows

Get the latest image

    docker pull mcr.microsoft.com/windows/nanoserver

Create a container

    docker create -t --name HelloNanoServerWorld -h NanoServer -i microsoft/nanoserver

Confirm that the container has been created

    PS C:\Users\pram\Downloads> docker container ls -a
	CONTAINER ID        IMAGE                  COMMAND                    CREATED             STATUS              PORTS               NAMES
	b89321d8ce83        microsoft/nanoserver   "c:\\windows\\system32…"   9 minutes ago       Created                                 HelloNanoServerWorld

Download the latest JDK file from Oracle

Copy JDK onto container

    docker cp .\jdk-8u161-windows-x64.exe HelloNanoServerWorld:/jdk-8u161-windows-x64.exe

Start the container

    docker start -i HelloNanoServerWorld

You should now see a shell open with a `C:\` prompt