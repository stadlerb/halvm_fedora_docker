Fedora base system for HalVM
============================

A base system with all dependencies required by HalVM but without HalVM itself

Github page: <https://github.com/stadlerb/halvm_fedora_docker>

Note: 
-----

By mistake, in version 0.1 the xen utilities are missing from halvm-fedora-base. As I didn't want to rebuild halvm-fedora-runtime, I added them manually to the halvm-fedora-runtime image. If you want to rebuild only halvm-fedora-runtime without building halvm-fedora-base first, please refer to the steps from that image's description.
