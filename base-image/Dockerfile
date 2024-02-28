# Build the mod_wsgi
FROM alpine
RUN apk update && apk add gcc apache2-dev python3 py3-pip python3-dev musl-dev
WORKDIR /home/appuser
RUN python -m venv venv && . venv/bin/activate && pip install mod_wsgi
# Copy the environment over
FROM alpine
# Create a group called appusers and a user called appuser
RUN addgroup -S appgroup && adduser -S appuser -G appgroup
# Copy the built mod_wsgi
RUN apk update && apk add python3 apache2
COPY --from=0 /home/appuser/venv /home/appuser/venv
RUN chown -R appuser /home/appuser/venv
