About libojph-feedstock
=======================

Feedstock license: [BSD-3-Clause](https://github.com/conda-forge/libojph-feedstock/blob/main/LICENSE.txt)

Home: https://github.com/hmaarrfk/OpenJPH

Package license: BSD-2-Clause

Summary: A fork of OpenJPH (HTJ2K / JPEG 2000) with the rev12 and rev13 reversible kernels, co-installable with OpenJPH.

Development: https://github.com/hmaarrfk/OpenJPH

libojph is a C++ JPEG 2000 / High-Throughput JPEG 2000 (HTJ2K) codec built
from a fork of OpenJPH. Besides the 5/3 and 9/7 wavelet kernels, it
encodes and decodes the reversible predict-only kernels rev13 and rev12
(JPEG 2000 Part 2, signalled with ATK markers), so that decoding with r
skipped resolutions returns exactly image[::2**r, ::2**r]. On x86-64 it
dispatches at run time to Google Highway SIMD kernels.

Its files (libojph, include/ojph, lib/cmake/ojph, ojph.pc) do not overlap
with the openjph package, so both can be installed in one environment.
Use it from CMake with find_package(ojph CONFIG REQUIRED) and the target
ojph::ojph, or with pkg-config's ojph module.

Current build status
====================


<table><tr>
    <td>GitHub Actions</td>
    <td>
      <a href="https://github.com/conda-forge/libojph-feedstock/actions/workflows/conda-build.yml">
        <img src="https://github.com/conda-forge/libojph-feedstock/actions/workflows/conda-build.yml/badge.svg?event=push&branch=main">
      </a>
    </td>
  </tr>
    
  <tr>
    <td>Azure</td>
    <td>
      <details>
        <summary>
          <a href="https://dev.azure.com/conda-forge/feedstock-builds/_build/latest?definitionId=30185&branchName=main">
            <img src="https://dev.azure.com/conda-forge/feedstock-builds/_apis/build/status/libojph-feedstock?branchName=main">
          </a>
        </summary>
        <table>
          <thead><tr><th>Variant</th><th>Status</th></tr></thead>
          <tbody><tr>
              <td>osx_64</td>
              <td>
                <a href="https://dev.azure.com/conda-forge/feedstock-builds/_build/latest?definitionId=30185&branchName=main">
                  <img src="https://dev.azure.com/conda-forge/feedstock-builds/_apis/build/status/libojph-feedstock?branchName=main&jobName=osx&configuration=osx%20osx_64_" alt="variant">
                </a>
              </td>
            </tr>
          </tbody>
        </table>
      </details>
    </td>
  </tr>
</table>

Current release info
====================

| Name | Downloads | Version | Platforms |
| --- | --- | --- | --- |
| [![Conda Recipe](https://img.shields.io/badge/recipe-libojph-green.svg)](https://anaconda.org/conda-forge/libojph) | [![Conda Downloads](https://img.shields.io/conda/dn/conda-forge/libojph.svg)](https://anaconda.org/conda-forge/libojph) | [![Conda Version](https://img.shields.io/conda/vn/conda-forge/libojph.svg)](https://anaconda.org/conda-forge/libojph) | [![Conda Platforms](https://img.shields.io/conda/pn/conda-forge/libojph.svg)](https://anaconda.org/conda-forge/libojph) |

Installing libojph
==================

Installing `libojph` from the `conda-forge` channel can be achieved by adding `conda-forge` to your channels with:

```
conda config --add channels conda-forge
conda config --set channel_priority strict
```

How to use
----------

<details>
<summary>With conda</summary>

```
conda install libojph
```

</details>

<details>
<summary>With mamba</summary>

```
mamba install libojph
```

</details>

<details>
<summary>With pixi</summary>

```
# for adding to your local project
pixi add libojph
# for installing globally
pixi global install libojph
```

</details>

Search package versions
-----------------------

It is possible to list all of the versions of `libojph` available on your platform:

<details>
<summary>With conda</summary>

```
conda search libojph --channel conda-forge
```

</details>

<details>
<summary>With mamba</summary>

```
mamba search libojph --channel conda-forge
```

</details>

<details>
<summary>With pixi</summary>

```
pixi search libojph --channel conda-forge
```

</details>

<details>
<summary>With mamba repoquery, which may provide more information</summary>

```
# Search all versions available on your platform:
mamba repoquery search libojph --channel conda-forge

# List packages depending on `libojph`:
mamba repoquery whoneeds libojph --channel conda-forge

# List dependencies of `libojph`:
mamba repoquery depends libojph --channel conda-forge
```

</details>



About conda-forge
=================

[![Powered by
NumFOCUS](https://img.shields.io/badge/powered%20by-NumFOCUS-orange.svg?style=flat&colorA=E1523D&colorB=007D8A)](https://numfocus.org)

conda-forge is a community-led conda channel of installable packages.
In order to provide high-quality builds, the process has been automated into the
conda-forge GitHub organization. The conda-forge organization contains one repository
for each of the installable packages. Such a repository is known as a *feedstock*.

A feedstock is made up of a conda recipe (the instructions on what and how to build
the package) and the necessary configurations for automatic building using freely
available continuous integration services. Thanks to the awesome service provided by
[Azure](https://azure.microsoft.com/en-us/services/devops/) and [GitHub](https://github.com/)
it is possible to build and upload installable packages to the
[conda-forge](https://anaconda.org/conda-forge) [anaconda.org](https://anaconda.org/)
channel for Linux, Windows and OSX respectively.

To manage the continuous integration and simplify feedstock maintenance,
[conda-smithy](https://github.com/conda-forge/conda-smithy) has been developed.
Using the ``conda-forge.yml`` within this repository, it is possible to re-render all of
this feedstock's supporting files (e.g. the CI configuration files) with ``conda smithy rerender``.

For more information, please check the [conda-forge documentation](https://conda-forge.org/docs/).

Terminology
===========

**feedstock** - the conda recipe (raw material), supporting scripts and CI configuration.

**conda-smithy** - the tool which helps orchestrate the feedstock.
                   Its primary use is in the construction of the CI ``.yml`` files
                   and simplify the management of *many* feedstocks.

**conda-forge** - the place where the feedstock and smithy live and work to
                  produce the finished article (built conda distributions)


Updating libojph-feedstock
==========================

If you would like to improve the libojph recipe or build a new
package version, please fork this repository and submit a PR. Upon submission,
your changes will be run on the appropriate platforms to give the reviewer an
opportunity to confirm that the changes result in a successful build. Once
merged, the recipe will be re-built and uploaded automatically to the
`conda-forge` channel, whereupon the built conda packages will be available for
everybody to install and use from the `conda-forge` channel.
Note that all branches in the conda-forge/libojph-feedstock are
immediately built and any created packages are uploaded, so PRs should be based
on branches in forks, and branches in the main repository should only be used to
build distinct package versions.

In order to produce a uniquely identifiable distribution:
 * If the version of a package **is not** being increased, please add or increase
   the [``build/number``](https://docs.conda.io/projects/conda-build/en/latest/resources/define-metadata.html#build-number-and-string).
 * If the version of a package **is** being increased, please remember to return
   the [``build/number``](https://docs.conda.io/projects/conda-build/en/latest/resources/define-metadata.html#build-number-and-string)
   back to 0.

Feedstock Maintainers
=====================

* [@hmaarrfk](https://github.com/hmaarrfk/)

