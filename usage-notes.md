# Usage Notes #

[Enable Developer Mode on TV](https://developer.samsung.com/tv/develop/getting-started/using-sdk/tv-device)

1. Go to Apps
2. Enter numbers "1,2,3,4,5" on remote keypad
3. enable developer mode
4. enter ip address of machine that will be uploading packages.
5. exit and restart TV (holding power button on remote until it restarts)

Run Docker image in interactive mode

```
podman run -it --rm tizen /bin/bash
```

Inside the docker container

```
$ tizen-studio/tools/sdb devices
* Server is not running. Start it now on port 26099 *
* Server has started successfully *
List of devices attached
$ tizen-studio/tools/sdb connect 192.168.1.100
connecting to 192.168.1.100:26101 ...
connected to 192.168.1.100:26101
$ tizen-studio/tools/sdb devices
List of devices attached 
192.168.1.100:26101 	device    	UN5...FXZA
$ curl -LO  https://github.com/jeppevinkel/jellyfin-tizen-builds/releases/download/2024-11-24-0431/Jellyfin-10.10.z-TrueHD.wgt
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
  0     0    0     0    0     0      0      0 --:--:-- --:--:-- --:--:--     0
100 10.5M  100 10.5M    0     0  7685k      0  0:00:01  0:00:01 --:--:--  9.8M
$ tizen-studio/tools/ide/bin/tizen.sh install -n Jellyfin-10.10.z-TrueHD.wgt -t UN5...FXZA
Transferring the package...
Transferred the package: /home/developer/Jellyfin-10.10.z-TrueHD.wgt -> /home/owner/share/tmp/sdk_tools/tmp
Installing the package...
--------------------
Platform log view
--------------------
install AprZAARz4r.Jellyfin
package_path /home/owner/share/tmp/sdk_tools/tmp/Jellyfin-10.10.z-TrueHD.wgt
app_id[AprZAARz4r.Jellyfin] install start
... omitting for brevity ...
app_id[AprZAARz4r.Jellyfin] install completed
spend time for wascmd is [13123]ms
Installed the package: Id(AprZAARz4r.Jellyfin)
Tizen application is successfully installed.
Total time: 00:00:16.400
```

After installing disable developer mode and restart again