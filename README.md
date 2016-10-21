# asciinema2gif

Build your own image

    sudo docker build -t asciinema2gif .

Test image

    sudo docker run -it --name asciinema-some lhuckaz/asciinema2gif asciinema rec

or

Test image with docker commands and keep container in background

    sudo docker run -d --name asciinema-some -v /var/run/docker.sock:/var/run/docker.sock -v $(which docker):/usr/bin/docker lhuckaz/asciinema2gif sleep infinity

Run commands in background container

    sudo docker exec -it asciinema-some asciinema rec

Run asciinema2gif with nº (Ex. https://asciinema.org/api/asciicasts/8332)

     sudo docker exec -it asciinema-some asciinema2gif --size small --speed 2 --theme solarized-dark -o "/home/asciinema/another.gif" https://asciinema.org/api/asciicasts/<nº>


Copiar .gif for your host

    sudo docker cp asciinema-some:/home/asciinema/another.gif ~/another.gif
