# Deploy to Source Code to a Container Repository with Tekton Pipeline

## Intro

A basic `tkn` pipeline that uses `s2i` to build a container image and pushes it to a Docker repository

```
helm upgrade -i test . --set git.url=<GIT URL> --set git.branch=main --set imageCredentials.password=<QUAY PASSWORD> --set imageCredentials.username=<QUAY USERNAME>
```


## Parameters

| Parameter                 | Description                                                        |
|---------------------------|--------------------------------------------------------------------|
| git.url                   | Url of git repo                                                    |
| git.branch                | Repo's branch                                                      |
| image.name                | Image name                                                         |
| image.tag                 | Image Tag                                                          |
| image.url                 | Image Url (Created automatically base on credentials and name/tag) |
| imageCredentials.registry | Registry url (i.e. quay.io)                                        |
| imageCredentials.username | Username for the registry                                          |
| imageCredentials.password | Password for the registry                                          |

## Kubernetes Resources Created

* Pipeline
* Git Pipeline Resource (Source)
* Image Pipeline Resource (Destination)
* Pipeline Task
* Pipeline Run 
* Pull Secret