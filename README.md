# Examples of Kubernetes Resources

## Purpose

This example demonstrates the Kubernetes autoscaling feature.

## How-to

You should first use a dedicated namespace for this project. Everything is included in this git repo. Create the namespace first, then, move to the deployment and the service to expose the newly create deployment.
The latter is a basic httpd webserver.

## Access the service

There is already a NodePort in place.
In case you are missing the external ip to access your cluster and if you are using minikube, you can get the url with the following command.

    minikube service --url php-apache --namespace=php-ns

## Launch the testing tool

    kubectl run ab --namespace=php-ns --restart='Never' --image=lucj/ab -- -n 150000 -c 50 http://php-apache

Author : Christian BELLET
