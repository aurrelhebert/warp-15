## First install Warp 10 

http://www.warp10.io/getting-started/

Adapt X.Y.Z to the Warp 10 version number needed

```
wget https://dl.bintray.com/cityzendata/generic/io/warp10/warp10/X.Y.Z/
tar xf warp10-X.Y.Z.tar.gz
cd warp10-X.Y.Z/bin

```

You will need to set-up a JVM, and then initialise Warp 10 as indicated in getting started. You will have to update the MAX_OPS attribute in conf file to load all the fuel station data in one raw. Set it at 1000000.

## Push Fuel data set

Once Warp 10 is running you can add the Fuel data that are stored in snapshot.mc2 file.
To load them, just update the WRITE_TOKEN in the snapshot file (line 11). Then execute.

```
curl -v http://127.0.0.1:8080/api/v0/exec --data-binary @snapshot.mc2
```

## Run the demo

You can now run both demo script. The first one doesn't need to access any data store on Warp10 and can be executed as if.
The second one need to access the fuel data, previously stored, a READ_TOKEN is necessare and the script have to be updated (line 5).

To execute the script, you can open your navigator and access quantum at the following URL
```
127.0.0.1:8090
```

Or you can send a command using the exec entry point of Warp10
```
curl -v http://127.0.0.1:8080/api/v0/exec --data-binary @File_Name
```

Feel free to update the Script to see how to manipulate the data!