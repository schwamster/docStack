
![Architecture diagram](logo.png)

# docStack

## What is docStack?

docStack makes document management easy. upload documents in a variety of formats. docStack will store the data and provide you with the 
tools to find the documents again at some later time. docStack will also run a number of post-processing steps on your documents to make it a lot
easier to find stuff again. 

* text extract: docStack will extract the text out of your document no matter if it is a scan, photo or a word document
* tagging: dockStack will extract tags from your document
* language detection: docStack will detect the language of your document
* content analysis: docStack will try to find out what kind of document it is and provide you with key entities of that document kind

docStack is also very much under development and is mainly used to figure out how to do a couple of things: microservices, docker, cognitive services...

## Contribution

Contributors are very welcome. If you are interested to find out how a microservice infrastructure might work (still trying to figure that out myself...)
or you think the document management is interesting or if you see where we are doing things wrong dont hesitate to help out.

Please join the conversation here:

[![Join the chat at https://gitter.im/docStack-im/Lobby](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/docStack-im/Lobby?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

## Current State

In this state we just want to put out a POC without focusing on a lot of the important details. The first thing we want to proove is: upload a document, extract text, put it in a store, make the docs searchable in the client

### Build States

| service  | git  | build  | docker  |
|---|---|---|---|
| doc-stack-app  | https://github.com/schwamster/doc-stack-app  | [![CircleCI](https://circleci.com/gh/schwamster/doc-stack-app.svg?style=shield&circle-token)](https://circleci.com/gh/schwamster/doc-stack-app)  | [![Docker Automated buil](https://img.shields.io/docker/automated/jrottenberg/ffmpeg.svg)](https://hub.docker.com/r/schwamster/doc-stack-app/)  |
| doc-stack-app-api  | https://github.com/schwamster/doc-stack-app-api  | [![CircleCI](https://circleci.com/gh/schwamster/doc-stack-app-api.svg?style=shield&circle-token)](https://circleci.com/gh/schwamster/doc-stack-app-api)  | [![Docker Automated buil](https://img.shields.io/docker/automated/jrottenberg/ffmpeg.svg)](https://hub.docker.com/r/schwamster/doc-stack-app-api/)  |
| text_worker  | https://github.com/schwamster/text-worker  | [![CircleCI](https://circleci.com/gh/schwamster/text_worker.svg?style=shield&circle-token)](https://circleci.com/gh/schwamster/text_worker)  | [![Docker Automated buil](https://img.shields.io/docker/automated/jrottenberg/ffmpeg.svg)](https://hub.docker.com/r/schwamster/text-worker/)  |
| ocr_service  | https://github.com/schwamster/ocr_service  | [![CircleCI](https://circleci.com/gh/schwamster/ocr_service.svg?style=shield&circle-token)](https://circleci.com/gh/schwamster/ocr_service)  | [![Docker Automated buil](https://img.shields.io/docker/automated/jrottenberg/ffmpeg.svg)](https://hub.docker.com/r/schwamster/ocr_service/)  |
| pdf_to_text  | https://github.com/schwamster/pdf_to_text  | [![CircleCI](https://circleci.com/gh/schwamster/pdf_to_text.svg?style=shield&circle-token)](https://circleci.com/gh/schwamster/pdf_to_text)  | [![Docker Automated buil](https://img.shields.io/docker/automated/jrottenberg/ffmpeg.svg)](https://hub.docker.com/r/schwamster/pdf_to_text/)  |
| luis_adapter_service  | https://github.com/schwamster/luis_adapter_service  | [![CircleCI](https://circleci.com/gh/schwamster/luis_adapter_service.svg?style=shield&circle-token)](https://circleci.com/gh/schwamster/luis_adapter_service)  | [![Docker Automated buil](https://img.shields.io/docker/automated/jrottenberg/ffmpeg.svg)](https://hub.docker.com/r/schwamster/luis_adapter_service/)  |


## Getting started

![Architecture diagram](docStack.png)
