# Automated k6 load testing with Atlassian Bamboo

This is an example repo for how to setup k6 with [Atlassian Bamboo](https://www.atlassian.com/software/bamboo) CI/CD to build load testing into an automation flow.

The full guide describing how to use this repository is located [here](https://blog.loadimpact.com/).

## Run Local

```bash
# Run locally
k6 run scripts/test.js

# Run via Docker
docker run -i loadimpact/k6 run - <scripts/test.js
```

## Run Cloud

```bash
# Run directly
k6 login cloud --token <YOUR_K6_CLOUD_API_TOKEN>
k6 cloud scripts/cloud-test.js

# Run via Docker
docker run -i -e K6_CLOUD_TOKEN=<API_TOKEN> loadimpact/k6 cloud - <scripts/cloud-test.js

# Alternative Docker version with mounting option
docker run -i -e K6_CLOUD_TOKEN=<API_TOKEN> -v "$PWD/scripts:/cloud-test.js" loadimpact/k6 cloud /cloud-test.js
```
