# ring

The purpose of ring is to create "one ring to rule them all" for package management. Ring was born out of frustration with having to deal with various package management utilities including:
 * apt
 * yum
 * npm
 * pip
 * easy_install
 * gem
 * brew
 * port

Ring queries each of these package management utilities, and infers which to use based on the package's presense or absense in the package repository.

## Using ring

### Installation

Ring installations are done using the install target:

    > sudo ring install simplejson
    simplejson found in pip > installing simplejson via pip
    simplejson installed!

#### Installation from multiple/ambiguous sources

Ring installations that match to one or more package management utilities will prompt you to decide which to use:

    > sudo ring install json
    json found in npm
    json found in pip
    which json do you want to install?
       1. npm
       2. pip
       3. all
    ? 3
    json installed!


You can also force ring to install packages from all matching package management utilities using the --all flag:

    > sudo ring install --all json
    json found in npm
    json found in pip
    json installed!


### Updating

Ring updates using the update target. This delegates to all package management utilities and updates their sources accordingly:

    > sudo ring update
    updating pip...
    updating brew...
    updating npm...
    done!

