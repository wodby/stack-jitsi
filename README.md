# Jitsi Meet application stack for Kubernetes on Wodby

Deploy Jitsi Meet video meetings on Kubernetes with Wodby.

This repository defines the Wodby stack manifests and default service
composition for Jitsi Meet.

<!-- wodby:generated:start -->

## Stack contract

- [Jitsi Meet stack on Wodby](https://wodby.com/stacks/jitsi)
- [Browse Wodby application stacks](https://wodby.com/stacks)
- [Jitsi Meet stack guide](https://wodby.com/docs/2.0/stacks/catalog/jitsi/)
- [Wodby stack documentation](https://wodby.com/docs/2.0/stacks/)
- [Stack manifest reference](https://wodby.com/docs/2.0/stacks/template/)

## Service definitions

- [Jitsi Meet service](https://github.com/wodby/service-jitsi)

## What's included

| Component / service | Default configuration |
| --- | --- |
| Jitsi Meet<br>`jitsi` | required; enabled by default |

Enabled optional services are selected by default but can be excluded when an
app is created. Disabled optional services are available but not selected by
default. Required services cannot be excluded.

## Validate the stack manifest

```bash
wodby stack validate-manifest stack.yml --org <org-id>
```

<!-- wodby:generated:end -->

## Deploy this stack

The stack needs no repository: Jitsi Meet runs from its own images.

1. Enter a moderator password in the Jitsi Meet service's settings when you create the app. The moderator signs in to
   start meetings; with **Allow guests** on, anyone with the link can join once a meeting has started.
2. After the app is created, publish the Jitsi Meet service's `media` port and deploy again. Browsers send audio and
   video to that port over UDP; without it, meetings have no audio or video.

If the app's domain goes through a proxy such as Cloudflare, set the **Media IP address** setting to the cluster's
public IP.

## Maintain a custom version

1. Fork this repository.
2. Edit the stack manifest.
3. Import the repository as a [Git-backed stack](https://wodby.com/docs/2.0/stacks/create/#create-a-git-backed-stack).

When replacing or renaming a stack service, update every related link target
and derivative reference. Stack-local names and referenced service names are
distinct identifiers.
