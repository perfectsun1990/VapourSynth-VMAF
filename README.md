Description
===========

VMAF filter for VapourSynth. VMAF is a perceptual video quality assessment algorithm developed by Netflix. Refer to the [FAQ](https://github.com/Netflix/vmaf/blob/master/FAQ.md) page for frequently asked questions of VMAF.


Note
====

The folder `model` must be located in the same folder as `VMAF.dll`.


Usage
=====

    vmaf.VMAF(clip reference, clip distorted[, int model=0, string log_path="", int log_fmt=0, bint psnr=False, bint ssim=False, bint ms_ssim=False, int pool=0, bint ci=False])

* reference, distorted: Clips to calculate VMAF score. Only YUV420P8, YUV422P8, YUV444P8, YUV420P10, YUV422P10, and YUV444P10 are supported.

* model: Sets which model to use. Refer to the [models](https://github.com/Netflix/vmaf/blob/master/resource/doc/models.md) page for more details.
  * 0 = vmaf_v0.6.1.pkl
  * 1 = vmaf_4k_v0.6.1.pkl

* log_path: Sets the file path of the log file.

* log_fmt: Sets the format of the log file.
  * 0 = xml
  * 1 = json

* psnr: Whether PSNR is also calculated.

* ssim: Whether SSIM is also calculated.

* ms_ssim: Whether MS-SSIM is also calculated.

* pool: Sets the method to pool the per-frame scores.
  * 0 = mean
  * 1 = harmonic mean
  * 2 = min

* ci: Whether confidence interval is enabled. Refer to the [VMAF confidence interval](https://github.com/Netflix/vmaf/blob/master/resource/doc/conf_interval.md) page for more details.


Compilation
===========

Requires `libvmaf`.

```
./autogen.sh
./configure
make
```
