FROM python:3.5

RUN apt-get update \
  && apt-get clean \
  && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*


RUN groupadd -g 799 rs8960 && \
    useradd -r -u 999 -g rs8960 rs8960

# Set up a working folder and install the pre-reqs
WORKDIR /app

RUN pip install Flask

RUN pip install requests

USER rs8960

COPY --chown=rs8960:rs8960 . .

CMD [ "python", "./FS.py" ]
