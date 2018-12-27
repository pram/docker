FROM microsoft/nanoserver:latest

# 7 ZIP
ADD 7z1602-x64.exe \7z1602-x64.exe
RUN 7z1602-x64.exe | more
# RUN powershell Start-Process -Wait -FilePath '\7z1602-x64.exe' -ArgumentList '/S'
RUN powershell SetX /M PATH "\"C:\Program Files\7-zip;$env:PATH\""
RUN powershell Remove-Item -Force /7z1602-x64.exe

# Install Java 8
ADD Java.zip /

RUN powershell Get-ChildItem Env:PATH
RUN powershell ls "\"C:\Program Files\""

RUN 7z.exe e /Java.zip -o/
RUN powershell SetX /M PATH      "\"\java\jdk1.8.0_191\bin;$env:PATH\""
RUN powershell SetX /M JAVA_HOME "\"\java\jdk1.8.0_191\""

CMD java -version