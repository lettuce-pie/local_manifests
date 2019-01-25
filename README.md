Getting Started
---------------

To get started with Android, you'll need to get
familiar with [Git and Repo](https://source.android.com/source/using-repo.html).

1. Set up your environment (use any of the hundreds of guides out there on XDA)

3. Initialize repo of the required ROM, for example [LineageOS](https://github.com/LineageOS) 16.0
 ```
    mkdir lineage && cd lineage
    repo init -u https:/github.com/LineageOS/android/ -b lineage-16.0
 ```
4. Now create a local_manifests dir and download the reqired manifest to that folder
 ```
    mkdir .repo/local_manifests
    wget https://github.com/lettuce-pie/local_manifests/raw/master/lineage-16.0-lettuce.xml -O .repo/local_manifests/lettuce.xml
 ```
5. Then to sync up:
 ```
    repo sync -f --force-sync
 ```
   OR a more space-saving, faster way to sync:
 ```
    repo sync -c -f --force-sync --no-tags --no-clone-bundle --optimized-fetch --prune
 ```

6. Finally, build it !
 ```
    . build/envsetup.sh
    lunch lineage_lettuce-userdebug && mka bacon
 ```
