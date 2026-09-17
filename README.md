# TDK Docker Compose example

Run TDK CLI from Docker Compose without installing the binary on your host.

## Quick start

```sh
docker compose run --rm tdk tdk --version
docker compose run --rm tdk tdk project --yes
printf "\n" | docker compose run --rm -T tdk tdk resource api --type backend --stack pre-alpha --path services/pre-alpha/api
docker compose run --rm tdk tdk project --check
```

The working directory is mounted into the container at `/workspace`, so generated files appear in this repo.

## Start a stack

Install Tilt on the host if you want to run the generated stack directly:

```sh
tdk up pre-alpha
```

For container-only smoke testing, validate the generated project instead:

```sh
docker compose run --rm tdk tdk project --check
```

