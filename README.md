# puppet-package-builder

Allow you to build a package (rpm/deb) from a standard Puppet module.

This script only works with new Puppet modules that contains the metadata.json file. Old modules that contains the Modulefile file will not work with this script.

## Usage
```
usage: puppet-package-builder [-h] [-p PATH] [--prefix PREFIX]
                              [-t {deb,rpm,tar}] [-r REPO] [-d DEST]

This script allows you to automatically build packages from Puppet modules.

optional arguments:
  -h, --help            show this help message and exit
  -p PATH, --path PATH  The path of the module to build (default: current dir)
  --prefix PREFIX       The prefix given to your package (default: puppet-
                        mod-)
  -t {deb,rpm,tar}, --type {deb,rpm,tar}
                        The type of package you want to create (deb, rpm, tar)
                        (default: rpm)
  -r REPO, --repo REPO  Select the repository to generate the rpm (default:
                        /etc/pkg_repos/puppet-mod)
  -d DEST, --dest DEST  The directory to install the puppet module (default:
                        /usr/share/puppet/modules-repo)
```
All the default parameters can be set on the script by editing the variables on the Configuration part.

## Examples



## How it works

The script will build your module with the `puppet module build` command.
Then fpm will build your package with all the available informations on the metadata.json file.

## TODO
There is some issue that I need to correct :
* The dependencies doesn't work correctly, sometimes it's not written correctly on the metadata.json file
* Add a check for every values used from the metadata.json file (description, author etc...)
