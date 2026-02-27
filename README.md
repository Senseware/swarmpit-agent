# Swarmpit agent

Senseware-maintained fork of the Swarmpit Docker agent.

## Senseware Fork Notice

This repository is maintained by Senseware as a fork of `swarmpit/agent`.

Why we forked:

- Upstream and app-side defaults were tied to outdated Docker API assumptions.
- We needed a maintained agent aligned with the Senseware Swarmpit fork and modern Docker releases.

What this fork maintains:

- Default Docker API target `1.52` (Docker v29.0 API level), with env override support.
- Release pipeline and image publishing for `ghcr.io/senseware/swarmpit-agent`.
- Compatibility alignment with https://github.com/Senseware/swarmpit.

Issue tracking for this fork:

- https://github.com/Senseware/swarmpit-agent/issues

Changelog:

- [CHANGELOG.md](CHANGELOG.md)

[![version](https://img.shields.io/github/release-pre/Senseware/swarmpit-agent.svg)](https://github.com/Senseware/swarmpit-agent/releases) 
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](https://github.com/Senseware/swarmpit-agent/pulls)

## Run

```{r, engine='bash', count_lines}
docker run -d \
  --name agent \
  --volume /var/run/docker.sock:/var/run/docker.sock \
  ghcr.io/senseware/swarmpit-agent:latest
```

### Parameters

- STATS_FREQUENCY - default to **30**
- EVENT_ENDPOINT - default to **http://app:8080/events**
- HEALTH_CHECK_ENDPOINT - default to **http://app:8080/version**
- DOCKER_API_VERSION - default to **1.52** (Docker v29.0 API level)
- DEBUG_EVENT - default to **false**
- DEBUG_STATS - default to **false**

For modern Docker Engine releases, use API version **1.44** or newer.

## Important!

In case you are deploying agent inside Swarmpit [stack](https://github.com/Senseware/swarmpit/blob/master/docker-compose.yml)
with some sort of customization, make sure that Swarmpit service name (default to **app**) match domain name set by EVENT_ENDPOINT & HEALTH_CHECK_ENDPOINT. 
