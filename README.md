# 1Password CLI (op) docker image

Here is an unofficial Dockerfile for the [1Password command-line tool][ophomepage].

It is available on [docker hub][dockerhubpage] based on [Debian][debianhubpage] and using the last available release from the official [1Password CLI download page][opdlpage].

## Changelog

- 2020-02-29 Upgrading 1Password CLI to 0.8.0
- 2020-02-29 Upgrading 1Password CLI to 0.7.1
- 2019-10-30 Upgrading 1Password CLI to 0.7.0
- 2019-10-22 Upgrading 1Password CLI to 0.6.2
- 2019-09-19 Initial version: 1Password CLI v0.6.1 on Debian Buster

## run with docker run

    docker run --rm -it tophfr/op

## run with my fake op bin command (really a bash script launching docker run for you)

    wget -O $HOME/bin/op https://raw.githubusercontent.com/tophfr/docker-op/master/bin/op
    chmod a+x $HOME/bin/op

then just run `op` like you would with a standard install (without docker)

## run with my bash function

Add this line to you `.bashrc`:

    source &lt;(curl -s https://raw.githubusercontent.com/tophfr/docker-op/master/bin/bash.function.sh)

(or copy the script somewhere and source it from your `.bashrc`)

then just run `op` like you would with a standard install (without docker) from a new bash session.

  [ophomepage]: https://support.1password.com/command-line-getting-started "1Password command-line tool"
  [opdlpage]: https://app-updates.agilebits.com/product_history/CLI "1Password CLI downloads"
  [dockerhubpage]: https://hub.docker.com/r/tophfr/op "1Password CLI (op) hub page"
  [debianhubpage]: https://hub.docker.com/_/debian "Docker Official Images hub page"

