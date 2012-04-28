![huff](https://raw.github.com/benburton/huff/master/img/huff.png)

The purpose of huff is to allow you to "huff" packages out of all your different package management utilities (ok, it's not the best name... but it's short and wasn't taken). Huff was born out of frustration with having to deal with various package management utilities including:
 * apt
 * yum
 * npm
 * pip
 * easy_install
 * gem
 * brew
 * port

Huff queries each of these package management utilities, and infers which to use based on the package's presense or absense in the package repository.

## Installing Huff

You can install huff running the following command (provided that you have wget installed):

    wget https://raw.github.com/benburton/huff/master/huff && chmod +x huff && ./huff --install-local

## Using huff

### Installing Packages

Huff installations are done using the install target:

    > sudo huff install simplejson
    simplejson found in pip > installing simplejson via pip
    simplejson installed!

#### Installation packages from multiple/ambiguous sources

Huff installations that match to one or more package management utilities will prompt you to decide which to use:

    > sudo huff install json
    json found in npm
    json found in pip
    which json do you want to install?
       1. npm
       2. pip
       3. all
    ? 3
    json installed!


You can also force huff to install packages from all matching package management utilities using the --all flag:

    > sudo huff install --all json
    json found in npm
    json found in pip
    json installed!


### Updating

Huff updates using the update target. This delegates to all package management utilities and updates their sources accordingly:

    > sudo huff update
    updating pip...
    updating brew...
    updating npm...
    done!

