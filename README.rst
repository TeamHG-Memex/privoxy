privoxy
=======

This is based on Jessie Frazelle's jess/privoxy image
(`github <https://github.com/jessfraz/dockerfiles/tree/master/privoxy>`_,
`blog post <https://blog.jessfraz.com/post/tor-socks-proxy-and-privoxy-containers/>`_)
with a few very minor tweaks (turned off debug logging, pinned alpine version,
container is versioned).

Example usage: run a privoxy in a container and link to a tor socks proxy container::

    docker run -d \
        --restart always \
        # the link inside the container must be named "torproxy"
        --link torproxy:torproxy \
        -v /etc/localtime:/etc/localtime:ro \
        -p 8118:8118 \
        --name privoxy \
        hyperiongray/privoxy:0.1.0

Dockerhub link: https://hub.docker.com/r/hyperiongray/privoxy/
