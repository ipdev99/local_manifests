
### Lineage 17.1
For Nexus 7 (2013) and Pixel C

---

#### To initialize your local repository.

Make a directory and switch into it.
````bash
mkdir l17
cd l17
````

Initialize the repository.
````bash
repo init -u https://github.com/LineageOS/android.git -b lineage-17.1
````

Then you need a copy of the local build manifest.
````bash
mkdir .repo/local_manifests
curl https://raw.githubusercontent.com/ipdev99/local_manifests/lineage-17.1/roomservice.xml -o .repo/local_manifests/roomservice.xml
````
or
````bash
curl --create-dirs -L -o .repo/local_manifests/roomservice.xml -O -L https://raw.githubusercontent.com/ipdev99/local_manifests/lineage-17.1/roomservice.xml
````

Then to sync up.
<br>
_The initial sync will take a long time._
````bash
repo sync
````
<br>

Finally to build.

Nexus 7 (2013) WiFi
````bash
source build/envsetup.sh
brunch flo
````
Nexus 7 (2013) LTE (Mobile)
````bash
source build/envsetup.sh
brunch deb
````
Pixel C
````bash
source build/envsetup.sh
brunch dragon
````
