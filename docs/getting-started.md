# Getting Started

This project serves as a fully working and tested solution for deploying preview
environments for your Pull Requests so you can get fast feedback before changes are merged to master.
This allows you to avoid having human approval inside your release pipeline to speed up delivery of changes merged to master.

When the Preview Environment is up and running GitHub Action Bot will comment on your Pull Request
with a link so in one click your team members can try out the preview.

Typically the creation of preview environments is automated inside the GitHub Workflow of application source code repository.

## Technologies used

**Terraform**[^1] is used to provision infrastructure resources like VPC, compute instances, DNS records.

**K3s**[^2] was chosen as a leightweight Kubernetes platform of choice for running applications in Cloud environment.

**OVH**[^3] public cloud is used as a Cloud provider for hosting K3s.

**DigitalOcean**[^4] is used to mnanage DNS records of K3s cluster (exposing controller and infrastructure resources to the outside world)
as well as smaller pieces like applications hosted on top of K3s (e.g. Traefik).

**Flask**[^5] is used as web framework to build an example application - Blog.

All Docker images are stored in public **DockerHub**[^6] registry.

Entire source code is stored in **GitHub**'s [netguru-interview](https://github.com/netguru-interview) organisation.

**GitHub Actions**[^7] are used for continuous integration, running tests, building application's Docker image.


**ArgoCD**[^8] is used for continuous deployment part of the process.

[^1]: [K3s: Lightweight Kubernetes.](https://k3s.io/)
[^2]: [Use Infrastructure as Code to provision and manage any cloud, infrastructure, or service.](https://www.terraform.io/)
[^3]: [The OVHcloud Public Cloud offers you a large number of cloud solutions that are billed on a pay-as-you-go basis.](https://www.ovhcloud.com/en/public-cloud/)
[^4]: [DigitalOcean's DNS tools let you manage DNS records for non-DigitalOcean resources.](https://www.digitalocean.com/docs/networking/dns/)
[^5]: [Flask is a micro web framework written in Python.](https://flask.palletsprojects.com/en/1.1.x/)
[^6]: [Storing and distribution system for named Docker images.](https://hub.docker.com/)
[^7]: [GitHub Actions enables you to create custom software development life cycle (SDLC) workflows directly in your GitHub repository.](https://docs.github.com/en/actions)
[^8]: [Argo CD is a declarative, GitOps continuous delivery tool for Kubernetes.](https://argoproj.github.io/argo-cd/)
