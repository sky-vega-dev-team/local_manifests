# Local manifests of the Pantech VEGA (msm8974)

Devices: IM-A880S (ef56), IM-A890 (ef59), IM-A900 (ef60), IM-A910 (ef63), IM-A920 (ef65)

## LineageOS 21.0 (branch `lineage-21.0`)

Based on [LineageOS-UL](https://github.com/LineageOS-UL/android) with the
patches of the official LineageOS 21.0 that it misses and the fixes of these
devices in [sky-vega-platform](https://github.com/sky-vega-platform).

```bash
repo init -u https://github.com/LineageOS-UL/android.git -b lineage-21.0 --git-lfs
git clone https://github.com/sky-vega-dev-team/local_manifests.git -b lineage-21.0 .repo/local_manifests
repo sync -c -j8 --force-sync --no-clone-bundle --no-tags
source build/envsetup.sh
lunch lineage_ef63-ap2a-userdebug
m bacon
```

- `pantech.xml`: the device, kernel and vendor trees, and the platform
  projects of sky-vega-platform in place of the ones of LineageOS-UL
- `official.xml`: the projects of the official LineageOS 21.0 that
  LineageOS-UL lacks
- `remove.xml`: the projects that break the build of these devices
