# __Yukon local manifests__

[![N|Solid](https://www1-lw.xda-cdn.com/files/2017/05/lineageos.png)](https://github.com/LineageOS)
Lineage os

# __status__
```
0= nothing 
1= not even started but code available
2= wip
3= booted
4= done
```

# __Suported variant and status__

* Xperia E3: Flamingo - status 3
* Xperia T2 Ultra: Tianchi - status 1
* Xperia T3: Seagull - status 1
* Xperia M2: Eagle - status 0

# __Guide__
This guide is for yukon `flamingo, seagull, eagle, tianchi`.
- __Prerequisites__
>You need a git acount. 
>64 bit computer && 150Gb free.
>Ubuntu 16.04 lts or 18.04 lts.
>Much patience (the process will be long even more while dl source).
>Min 8Gb of ram ( if you"re too short, decrease this param ( -Xmx4G ) in the following guide.

- __First let's setup environnement__

Read the whole guide one time before start.

```
sudo apt-get install openjdk-8-jdk
sudo apt-get install openjdk-8-jre
sudo apt-get install repo
sudo apt-get install git 
```
Configure your git with 
```
git config --global user.name "example: John Doe"
git config --global user.email example: johndoe@example.com
```
Setup needed tool
```
sudo apt-get install bc bison build-essential ccache curl flex g++-multilib gcc-multilib git gnupg gperf 
imagemagick lib32ncurses5-dev lib32readline-dev lib32z1-dev liblz4-tool libncurses5-dev 
libsdl1.2-dev libssl-dev libwxgtk3.0-dev libxml2 libxml2-utils lzop pngcrush rsync schedtool 
squashfs-tools xsltproc zip zlib1g-dev
```
Add that command to your ~/.bashrc (can be found on Home wile presing CTRL+H) 
```sh
export ANDROID_JACK_VM_ARGS="-Dfile.encoding=UTF-8 -XX:+TieredCompilation -Xmx4G" 
```
If you're on 18.04 bionic ubuntu add also :
```sh
export LC_ALL=C
```
- __Let's dl source__

Creat a dir name LOS and cd it 
```sh
mkdir ~/LOS && cd ~/LOS
```
Init source from LineageOS branch pie
```
repo init -u https://github.com/LineageOS/android.git -b lineage-16.0
```
get the manifest of yukon
```
git clone https://github.com/LOS-yukon/local_manifests.git -b lineage-16.0 .repo/local_manifests
```
sync (dl) 
```
repo sync --force-sync
```
- __Then compile it with__ 

compile it 
```
. build/envsetup.sh && breakfast device_name && brunch device_name
```
- __Where are your result?__ 

in folder `out/target/product/device_name`

# __credit__

Have to be done 
