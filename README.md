# Running trustify load tests

The goal is to have load tests, which can be re-run over time to see the evolution of Trustify's performance.

## Running it locally

After clone, run:

```bash
cp publish/baseline.json baseline/
```

Build the containers once:

```bash
podman compose -f compose.yaml build
```

Then run the test:

```bash
podman compose -f compose.yaml run loadtests
```

After the test has run, clean up:

```bash
podman compose -f compose.yaml down
```

## Wait, there is more

### Start a DB instance with an imported dump

To start up a database instance with the imported dump, run the following commands:

```bash
podman compose -f compose.yaml build
podman compose -f compose.yaml up trustify-migrate
```
