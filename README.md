# JACK example tools

This repository holds the official JACK example clients and tools, which have
been tracked in the
[example-clients](https://github.com/jackaudio/example-clients) and
[tools](https://github.com/jackaudio/tools) repositories in the past.

**WARNING**:

*In its current form, this project has conflicting files with the
[jack1](https://github.com/jackaudio/jack1) and
[jack2](https://github.com/jackaudio/jack2) projects (when installed).
The efforts for consolidating and eventually removing the example-clients and
tools from both projects are tracked in
[jackaudio/jack1#109](https://github.com/jackaudio/jack1/issues/109) and
[jackaudio/jack2#805](https://github.com/jackaudio/jack2/issues/805).
The installation and use of this project is therefore deemed experimental until
both issues are resolved.
However, testing is very much welcomed!*

## Dependencies

The project requires the following dependencies:

* [alsa-lib](https://www.alsa-project.org/wiki/Main_Page)
* [celt](https://gitlab.xiph.org/xiph/celt)
* [jack1](https://github.com/jackaudio/jack1) or [jack2](https://github.com/jackaudio/jack2)
* [opus](https://www.opus-codec.org/)
* [readline](https://tiswww.case.edu/php/chet/readline/rltop.html)
* [libsamplerate](https://libsndfile.github.io/libsamplerate/)
* [libsndfile](https://libsndfile.github.io/libsndfile/)
* [libzita-alsa-pcmi](https://kokkinizita.linuxaudio.org/linuxaudio/)
* [libzita-resampler](https://kokkinizita.linuxaudio.org/linuxaudio/)

## Building

jack-example-tools uses the [meson build system](https://mesonbuild.com).

To configure the project, meson's [universal
options](https://mesonbuild.com/Builtin-options.html#universal-options) (e.g.
**--prefix**) can be used to prepare a build directory:

```bash
meson --prefix=/usr build
```

To build the applications and libraries [ninja](https://ninja-build.org/) is
required:

```bash
ninja -C build
```

## Installing

Meson is able to install the project components to the system directories (when
run as root), while honoring the **DESTDIR** environment variable:

```bash
DESTDIR="/some/other/location" meson install -C build
```

## License

All files (unless noted otherwise) are licensed under the terms of the
**GPL-2.0-or-later** (see [LICENSE](LICENSE)).

The code in [tools/zalsa](tools/zalsa) is provided via [Fons Adriansen's
zita-ajbridge](https://kokkinizita.linuxaudio.org/linuxaudio/zita-ajbridge-doc/quickguide.html)
and licensed under the terms of the **GPL-3.0-or-later** (see
[tools/zalsa/LICENSE](tools/zalsa/LICENSE)).