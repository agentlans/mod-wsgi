FROM agentlans/mod-wsgi
# Be this user
USER appuser
# Source code of the app
ADD src/ /home/appuser/src/
# Install required packages
RUN source /home/appuser/venv/bin/activate && pip install -r /home/appuser/src/requirements.txt
# Run from the app's directory
WORKDIR /home/appuser/src
CMD ["/home/appuser/venv/bin/mod_wsgi-express", "start-server", "--user", "appuser", "--group", "appgroup", "/home/appuser/src/wsgi.py"]
