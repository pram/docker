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

Run the java installer (ref https://stackoverflow.com/questions/15292464/how-to-silently-install-java-jdk-into-a-specific-directory-on-windows)

    c:\jdk-8u161-windows-x64.exe /s ADDLOCAL="ToolsFeature,SourceFeature,PublicjreFeature" INSTALLDIR=C:\Java\x64\jdk1.8.0_161 /INSTALLDIRPUBJRE=C:\Java\x64\jre1.8.0_161
