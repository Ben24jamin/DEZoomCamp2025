##this file contains how to make a basic docker file.
FROM is the python version 
RUN we then pip install pandas using the above python version
WORKDIR /app we then create a volume for the docker to write cahnges
COPY we than link the pipline in app and write it to the docker image in app
ENTRYOINT we then tell the docker file where to start running and what to run ie. the pipeline

##now the pipeline we import the libraries 
that we need to run the pipeline it imports from the docker OS
we can now write a script in the pipeline to do things on runing the docekr image


docker build -t test:pandas .

docker run -it test:pandas 2025-06-10