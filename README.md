docker run -d \
    -p 25500:25500 \
    --restart=always \
    --name subconverter tindy2013/subconverter:latest


docker run -d \
    --name watchtower \
    --restart always \
    -v /var/run/docker.sock:/var/run/docker.sock \
    containrrr/watchtower \
    --cleanup \
    subconverter
