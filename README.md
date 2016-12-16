SARAH-Server-NodeJS for Docker on Alpine
========================================
This project pepares a minimalist Docker image with JpEncausse's SARAH-Server-NodeJS. It installs SARAH-Server-NodeJS from [JpEncausse's Github](https://github.com/JpEncausse/SARAH-Server-NodeJS)

You can install the latest build of this image by running `docker pull skydiscover/sarah-server-nodejs`.

This image can be used as a centralised S.A.R.A.H server.

What is S.A.R.A.H
-----------------

The goal of the S.A.R.A.H Project is the creation of an intelligent home connected to the internet of things in the spirit of the Eureka TV show.

The idea is to make available for all advanced technologies of voice, gesture and QRCode recognition.

Start SARAH-Server-NodeJS instance
----------------------------------

Starting a SARAH server instance is simple:

```
docker run --name <MyServerName> -e TZ=<TimeZone> -p <ServerPort>:8080 -d skydiscover/sarah-server-nodejs:latest
```
... where `<MyServerName>` is the name you want to assign to your container, `<TimeZone>` is your timezone, for exemple, for Paris: `TZ=Europe/Paris` and `<ServerPort>` is the port any client will use to connect to your server.

Other available options are:

`-p <ClientPort>:8888` - To configure the client port

`-v <PluginsPath>:/home/pi/SARAH-Server-NodeJS/plugins` - to mount an host folder as the server plugins folder (you will need this if you want to share plugins between the server and the clients)