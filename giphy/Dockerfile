FROM python:2.7.14

# Some ENV variables
ENV PATH="/mattermost/bin:${PATH}"
ENV MM_VERSION=4.2.0

# Build argument to set Mattermost edition
ARG edition=entreprise

# Install python
#RUN apt-get update
#RUN apt-get install --assume-yes zip
#RUN apt-get install --assume-yes python-pip python-dev build-essential git
#RUN apt-get install --assume-yes  git
#RUN wget https://github.com/mattermost/mattermost-integration-giphy/archive/master.zip
#RUN unzip master.zip
#RUN ls

# Get integration
RUN git clone https://github.com/numberly/mattermost-integration-giphy.git
WORKDIR mattermost-integration-giphy

RUN python setup.py install > /var/log/giphy_integration_setup.log

# Install some needed packages

CMD ["python","/mattermost-integration-giphy/run.py"]