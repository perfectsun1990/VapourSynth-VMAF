Description
===========

VMAF filter for VapourSynth. VMAF is a perceptual video quality assessment algorithm developed by Netflix. Refer to the [FAQ](https://github.com/Netflix/vmaf/blob/master/FAQ.md) page for frequently asked questions of VMAF.


Note
====

The folder `model` must be located in the same folder as `VMAF.dll`.


Usage
=====

    vmaf.VMAF(clip reference, clip distorted[, int model=0, string log_path=None, int log_fmt=0, bint ssim=False, bint ms_ssim=False, int pool=1, bint ci=False])

* reference, distorted: Clips to calculate VMAF score. Any planar format except RGB with integer sample type of 8-16 bit depth is supported.

* model: Sets which model to use. Refer to the [models](https://github.com/Netflix/vmaf/blob/master/resource/doc/models.md) page for more details.
  * 0 = vmaf_v0.6.1.pkl
  * 1 = vmaf_4k_v0.6.1.pkl

* log_path: Sets the path of the log file.

* log_fmt: Sets the format of the log file.
  * 0 = xml
  * 1 = json
  * 2 = csv

* ssim: Whether to also calculate SSIM score.

* ms_ssim: Whether to also calculate MS-SSIM score.

* pool: Sets the method to pool the per-frame scores.
  * 0 = mean
  * 1 = harmonic mean
  * 2 = min

* ci: Whether to enable confidence interval. If True, it uses vmaf_b_v0.6.3 for `model=0` and vmaf_4k_rb_v0.6.2 for `model=1`. Refer to the [VMAF confidence interval](https://github.com/Netflix/vmaf/blob/master/resource/doc/conf_interval.md) page for more details.


Compilation
===========

Requires `libvmaf`.

```
meson build
ninja -C build
ninja -C build install
```
