# prismlauncher-cracked-rpm-build
A **unofficial** repo with files to build rpm for [prismlauncher-cracked](https://github.com/Diegiwg/PrismLauncher-Cracked) project.
This is used to simply build prismlauncher-cracked rpm package using rpmdevtools. 
It can be used on RHEL linux operating systems family (RHEL, Fedora, CentOS)

This is not endorsed by Prism Launcher or by Prism Launcher Cracked Projects.

This project doesnt distribute prismlauncher-cracked binaries.
This project just has build files for easier building of prismlauncher-cracked rpm, and then you can install the rpm to your system

## Instructions
If you are on Fedora 42 you want to add adoptium java repo for temurin-17-jdk package.
To do this just follow instructions [here](https://adoptium.net/installation/linux/#_centosrhelfedora_instructions) (you need to be in root account to run the cat command)

to build th rpm you want to have ``rpmdevtools`` installed.

Next you want to setup ~/rpmbuild directory:
```
rpmdev-setuptree
```
Then get the .spec file:
```
git clone https://github.com/Hydriam/prismlauncher-cracked-rpm-build
cd prismlauncher
```
Get the build dependencies:
```
sudo dnf builddep prismlauncher.spec
```
Now we get the sources, copy patch files and we build the project:
```
spectool -g -R prismlauncher.spec
cp *.patch ~/rpmbuild/SOURCES
rpmbuild -bb prismlauncher.spec
```
The rpm file now should be in ``~/rpmbuild/RPMS`` directory.


