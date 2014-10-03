# puppet-package-builder

Allow you to build a package with fpm (rpm/deb) from a standard Puppet module.

## Usage
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
