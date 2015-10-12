# Création d'une image

## 1) Commande de base

Récupération d'une image:

    docker pull ubuntu

    > Using default tag: latest
    > latest: Pulling from library/ubuntu
    > 48731f0a6276: Pull complete
    > 9302827ed0a5: Pull complete
    > f03f3645bde1: Pull complete
    > cdd474520b8c: Pull complete
    > library/ubuntu:latest: The image you are pulling has been verified. Important: image verification is a tech preview feature and should not be relied on to provide security.
    > Digest: sha256:40cd91cbcaac863fa2fc0b8a8eaa440565ef5ce498d60177988f6f55ec691d9d
    > Status: Downloaded newer image for ubuntu:latest

Visualisation des images en local:

    docker images

    > REPOSITORY                      TAG                 IMAGE ID            CREATED             VIRTUAL SIZE
    > ubuntu                          latest              cdd474520b8c        19 hours ago        188 MB

Suppression d'une image:

    docker rmi ubuntu

    > Untagged: ubuntu:latest
    > Deleted: cdd474520b8c2c0418260fc9dcd999c84fe35bd3a36304aeb47517a290e5a5c4
    > Deleted: f03f3645bde1a45143056ad6bc9d352199f13cdb01c6d59a1c972432c9fc7e97
    > Deleted: 9302827ed0a51fe7f0cacb08e970b13c09da240ae8c4a8b559fb38e430f6be13
    > Deleted: 48731f0a6276cfb5d94a8f18690d56f88a586e701f1dd7f56889f26be990277d

Visualisation des containers en train de s'executer:

    docker ps

Visualisation de tous les containers:

    docker ps -a

## 2) Création d'une image

A partir de rien:

    tar cv --files-from /dev/null | docker import - simon/scratch

A partir d'un fichier Dockerfile:

   docker build --tag="simon/scratch:2" .
