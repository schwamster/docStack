
![Architecture diagram](logo.png)

# docStack

docStack is a document management system with extensible amount of postproscessing services that make it easier to find, analyze and export your documents.

## What is docStack?

docStack makes document management easy. upload documents in a variety of formats. docStack will store the data and provide you with the 
tools to find the documents again at some later time. docStack will also run a number of post-processing steps on your documents to make it a lot
easier to find stuff again. 

* text extract: docStack will extract the text out of your document no matter if it is a scan, photo or a word document
* tagging: dockStack will extract tags from your document
* language detection: docStack will detect the language of your document
* content analysis: docStack will try to find out what kind of document it is and provide you with key entities of that document kind

docStack is also very much under development and is mainly used to figure out how to do a couple of things: microservices, docker, cognitive services...


## Continuous integration / delivery

| service  | git  | build  | docker  |
|---|---|---|---|
| doc-stack-app  | https://github.com/schwamster/doc-stack-app  | [![CircleCI](https://circleci.com/gh/schwamster/doc-stack-app.svg?style=shield&circle-token)](https://circleci.com/gh/schwamster/doc-stack-app)  | [![Docker Automated buil](https://img.shields.io/docker/automated/jrottenberg/ffmpeg.svg)](https://hub.docker.com/r/schwamster/doc-stack-app/)  |
| doc-stack-app-api  | https://github.com/schwamster/doc-stack-app-api  | [![CircleCI](https://circleci.com/gh/schwamster/doc-stack-app-api.svg?style=shield&circle-token)](https://circleci.com/gh/schwamster/doc-stack-app-api)  | [![Docker Automated buil](https://img.shields.io/docker/automated/jrottenberg/ffmpeg.svg)](https://hub.docker.com/r/schwamster/doc-stack-app-api/)  |
| text_worker  | https://github.com/schwamster/text_worker  | [![CircleCI](https://circleci.com/gh/schwamster/text_worker.svg?style=shield&circle-token)](https://circleci.com/gh/schwamster/text_worker)  | [![Docker Automated buil](https://img.shields.io/docker/automated/jrottenberg/ffmpeg.svg)](https://hub.docker.com/r/schwamster/text-worker/)  |
| ocr_service  | https://github.com/schwamster/ocr_service  | [![CircleCI](https://circleci.com/gh/schwamster/ocr_service.svg?style=shield&circle-token)](https://circleci.com/gh/schwamster/ocr_service)  | [![Docker Automated buil](https://img.shields.io/docker/automated/jrottenberg/ffmpeg.svg)](https://hub.docker.com/r/schwamster/ocr_service/)  |
| pdf_to_text  | https://github.com/schwamster/pdf_to_text  | [![CircleCI](https://circleci.com/gh/schwamster/pdf_to_text.svg?style=shield&circle-token)](https://circleci.com/gh/schwamster/pdf_to_text)  | [![Docker Automated buil](https://img.shields.io/docker/automated/jrottenberg/ffmpeg.svg)](https://hub.docker.com/r/schwamster/pdf_to_text/)  |
| doc-store  | https://github.com/schwamster/doc-store  | [![CircleCI](https://circleci.com/gh/schwamster/doc-store.svg?style=shield&circle-token)](https://circleci.com/gh/schwamster/doc-store)  | [![Docker Automated buil](https://img.shields.io/docker/automated/jrottenberg/ffmpeg.svg)](https://hub.docker.com/r/schwamster/doc-store/)  |
| luis_adapter_service  | https://github.com/schwamster/luis_adapter_service  | [![CircleCI](https://circleci.com/gh/schwamster/luis_adapter_service.svg?style=shield&circle-token)](https://circleci.com/gh/schwamster/luis_adapter_service)  | [![Docker Automated buil](https://img.shields.io/docker/automated/jrottenberg/ffmpeg.svg)](https://hub.docker.com/r/schwamster/luis_adapter_service/)  |
| doc-identity  | https://github.com/schwamster/doc-identity  | [![CircleCI](https://circleci.com/gh/schwamster/doc-identity.svg?style=shield&circle-token)](https://circleci.com/gh/schwamster/doc-identity)  | [![Docker Automated buil](https://img.shields.io/docker/automated/jrottenberg/ffmpeg.svg)](https://hub.docker.com/r/schwamster/doc-identity/)  |

## Documentation

### Overview

![Architecture diagram](docStack.png)

### Getting started

The eaiest way to get up and running is with docker. All services described in the Overview are available as docker images (see continuous integration/delivery).
For more info on how to get started with docker go here: https://docs.docker.com/engine/getstarted/

After cloning this project you will have to set a number of environment variables on your computer (see docker-compose.yml to find out were they are used)

    - ComputerVisionKey
    - LuisAppId
    - LuisSubscriptionKey
    - DocStackAdminPassword

More info on how to set environment variables:

[Windows](https://technet.microsoft.com/en-us/library/ff730964.aspx) | [Unix/Linux](http://unix.stackexchange.com/questions/117467/how-to-permanently-set-environmental-variables)

#### ComputerVisionKey

We are using [Microsofts Cognitive Services](https://www.microsoft.com/cognitive-services/en-us/computer-vision-api) in the ocr_service to turn images and pdfs to text.
You will have to get your own Api Key ( free up to a reasonable limit for now) from [here](https://www.microsoft.com/cognitive-services/en-us/computer-vision-api)
Set the environment variable "ComputerVisionKey" to that value. 

#### LuisAppId & LuisSubscriptionKey

We are using [Language Understanding Intelligent Services](https://www.luis.ai/) in analyze the text of the documents.
You will have to get your own Api Key ( free up to a reasonable limit for now) from [here](https://www.luis.ai/)
Set the following environment variables:

LuisAppId => what luis app (model) to use default is the msft example app with the cortana model
LuisSubscriptionKey => Your own subscription key from luis

#### DocStackAdminPassword

Right now there is only one user you can use to log on:
username: admin
password: whatever you set in the "DocStackAdminPassword" environmentvariable

The password is used by doc-identity as an admin password. Usermanagment and so forth is still under construction.

#### Running for the first time

After you have set the environment variables and docker is up and running just navigate to the root of this project and run:

        docker-compose up

docker will now pull all images and then run each service.

Open a browser and navigate to http://localhost:4200 to access the application.

### How does the application work

tbd.

## Contribution

Contributors are very welcome. If you are interested to find out how a microservice infrastructure might work (still trying to figure that out myself...)
or you think the document management is interesting or if you see where we are doing things wrong dont hesitate to help out.

Please follow this guideline if you want to contribute:

* Fork the repository.
* Create a branch to work in.
* Make your feature addition or bug fix.
* Don't forget the unit tests.
* Send a pull request.

Please join the conversation here:

[![Join the chat at https://gitter.im/docStack-im/Lobby](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/docStack-im/Lobby?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

## License

Copyright © Bastian Töpfer and contributors.
docStack is provided as-is under the MIT license. For more information see [LICENSE](https://github.com/schwamster/docStack/LICENSE).

## Acknowledgement

Some services use external services:

Powered by Microsoft’s Cognitive Services: https://www.microsoft.com/cognitive-services

The logo was made with [Logo Maker](http://logomakr.com)

Stack graphic by [Freepik](http://www.flaticon.com/authors/freepik) from [Flaticon](http://www.flaticon.com/) under [Creative Commons BY 3.0](http://creativecommons.org/licenses/by/3.0/)

The architecture diagram was made with [draw.io](https://www.draw.io/)
