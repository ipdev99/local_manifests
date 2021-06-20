
### Lineage 16.0
For Nexus 10

---

#### To initialize your local repository.

Make a directory and switch into it.
````bash
mkdir l16
cd l16
````

Initialize the repository.
````bash
repo init -u https://github.com/LineageOS/android.git -b lineage-16.0
````

Then you need a copy of the local build manifest.
````bash
mkdir .repo/local_manifests
curl https://raw.githubusercontent.com/ipdev99/local_manifests/manta-l16/roomservice.xml -o .repo/local_manifests/roomservice.xml
````
or
````bash
curl --create-dirs -L -o .repo/local_manifests/roomservice.xml https://raw.githubusercontent.com/ipdev99/local_manifests/manta-l16/roomservice.xml
````

Then to sync up.
<br>
_The initial sync will take a long time._
````bash
repo sync
````
<br>

Finally to build.

Nexus 10
````bash
source build/envsetup.sh
brunch manta
````
