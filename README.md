# RENOCUU - Renoir 8 CU unlock

Phisicaly renoir has 8 CUs in the silicon. Some are disabled depending on the CPU.
This patch to linux `amdgpu` driver masks the disable bits from firmware enabling
full 8 CUs.

Ive tried to enable more than 8 CUs but it has no effect, reported CU count caps
out at 8. It doesnt lead to any hangs or instability, so you can try and play with
it on your hardware (report any interesting findings).

### Test hardware

Ive tested it on Thinkpad L14, running Ryzen 5 4500U with 6CUs out of the box.
Enabling all 8 produced an expected uplift of ~33% in hashcat (compute) benchmark.


## Acknowlegements

This whole idea is basicaly a port of [ravencuu](https://github.com/xrip/ravencuu)
to renoir
