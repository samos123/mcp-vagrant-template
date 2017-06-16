# Vagrantfile for local validation of MCP models
This repo contains a template for easily creating a Vagrantfile for your
MCP models.


# Getting started

1. Clone the repository

    git clone git@gitlab.com:presales-mirantis/mcp-vagrant-template.git
    cd mcp-vagrant-template

2. First you need to generate a deployment key that has access

    ssh-keygen -f deploy_key

3. Give read access to your deploy key at the place where your reclass model is
hosted.

4. Edit the Vagrantfile parameters that are specific to your model

    vim Vagrantfile

You will need to edit following parameters: {{environment\_name}},
{{reclass\_model\_git\_repo}}, {{cfg01\_address}}. You might also
need to add another network for cfg01\_deploy\_address.

Afterwards it will be a simple Vagrant up to validate whether the model can
be correctly traversed.
