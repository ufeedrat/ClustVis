# ClustVis
Souce code of [ClustVis](http://biit.cs.ut.ee/clustvis/) web tool.

The code is distributed under GNU GPLv3. If you are interested in other licensing options, please contact the author.

To run ClustVis locally, you can use a snapshot of ClustVis [Docker image](https://hub.docker.com/r/taunometsalu/clustvis/) from Docker Hub. You can also try to build the image from the Dockerfile but ClustVis code may not work correctly with the newest versions of the R packages if the changes have broken backward compatibility.

To use the Docker image, you need to have [Docker](https://www.docker.com/) installed. Then use the following code:

```
sudo docker pull taunometsalu/clustvis
mkdir ~/customClustvis/
cd ~/customClustvis/
wget https://github.com/taunometsalu/ClustVis/archive/master.zip
unzip master.zip
sudo docker run -d \
	--name customClustvis \
	-p <myPort>:3838 \
    -v ~/customClustvis/ClustVis-master/:/srv/shiny-server/:ro \
    taunometsalu/clustvis
```

ClustVis should then be running on ```<myURL>:<myPort>```.
