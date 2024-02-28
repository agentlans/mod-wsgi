# mod-wsgi
Production grade server container for Python WSGI apps

- Run Python Flask apps easily, robustly, and with minimal configuration.
- Designed as a replacement for `flask run` which is suitable for development only.

## Required

- [Docker](https://www.docker.com)
- GNU make (convenience only, not necessary)

## Use

To deploy a webapp:
1. Go to [`helloworldapp/src`](helloworldapp/src)
2. Change `webapp.py` to your code
3. Add the necessary Python packages to `requirements.txt`
4. Keep `wsgi.py` as it is. Don't change it.
5. In [`helloworldapp`](helloworldapp), run `make build` and `make run`
6. Open a web browser and visit `localhost` to see your app.

You shouldn't need this but to build the base image [`agentlans/mod-wsgi`](https://hub.docker.com/r/agentlans/mod-wsgi):
```bash
cd base-image
bash Build.sh
```

## Author, Licence

Copyright :copyright: 2024 By Alan Tseng

Apache 2.0
