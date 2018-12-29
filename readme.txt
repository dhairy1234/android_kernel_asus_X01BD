1.get kernelcode, eg: kernel-3.18
2.config env:
export PATH=/yourCodebase/$toolchain:$PATH
eg:
export PATH=/yourCodebase/prebuilts/gcc/linux-x86/aarch64/aarch64-linux-android-4.9/bin:$PATH

3.compile parameters
cd kernel/msm-4.4
mkdir out
export ARCH=arm64
export SUBARCH=arm64
export CROSS_COMPILE=aarch64-linux-android-4.9
make O=out project_defconfig
make -j8 O=out 2>&1 | tee build.log
