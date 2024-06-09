# Progress
### Buildutils Repository

I have pushed some changes in my forked repository for the PR build and the Main build (incomplete) workflows linked [here](https://github.com/jaydee029/buildutils/blob/main/.github/workflows/build-pr.yaml) and [here](https://github.com/jaydee029/buildutils/blob/main/.github/workflows/build.yaml).
Succesful run/log of both the workflows can be viewed [here](https://github.com/jaydee029/buildutils/actions/runs/9434952411) and [here](https://github.com/jaydee029/buildutils/actions/runs/9434952410) respectively.

A few changes were made in the dockerfiles while copying them linked [here](https://github.com/jaydee029/buildutils/tree/main/dockerfiles)

The `PR Build` is somewhat complete, i've used basic commands for building and testing the images rather than actions, as it felt unrequired, since the ubuntu runner has drivers for both Makefile as well as docker build, this can be changed if required. The workflow when invoked builds the go binaries using the make file, builds the docker image and tests it by running and eventually removing it.

Features which can be added :-
- caching
- error handling(if req)
- paths- so that the workflow is not invoked on text and similar changes.
  github actions doesnt allow negation in paths like `!**.txt` or `!**.md`, hence file extensions that need to be included would have to be specified individually.

For the `Main build` workflow,does all the things as PR Build workflow in addition the docker images are being succesfully built and pushed into my forked repository's container registery(availale to download). I am still getting used to maven build process, hence that part is remaining. In this workflow i still need to configure how the images should be named, this is also required by the galasabld-ibm-executable job which works by fetching the galasabld image with a tag/label from the conatiner registery. 
  
