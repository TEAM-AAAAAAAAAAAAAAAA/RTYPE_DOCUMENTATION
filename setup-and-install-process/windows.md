---
description: How to setup R-THAAAAAÏ on Windows operating system
layout: editorial
---

# 🪟 Windows

## Dependencies installation

As stated in the introcution, R-THAAAAAAÏ is dependent of 2 libraries, SFML and Boost.

{% hint style="danger" %}
Usage of bundled package manager, vcpkg, is strongly recommended.

Use system-wide library at your own risk.

You may also want to take a look here: [#remember-when-compiling](windows.md#remember-when-compiling "mention")&#x20;
{% endhint %}

### How to install dependendcies using bundled vcpkg&#x20;

vcpkg is bundled as a submodule inside of the R-THAAAAAAÏ.

{% hint style="info" %}
If the vcpkg directory is empty when you clone the repository, you **will** need to update and sync the submodule.

To update vpckg submodule, simply: `git submodule init` and `git submodule update vcpkg`
{% endhint %}

Inside the vcpkg directory you should have a file called `bootstrap-vcpkg.bat`, launch it.

In order to install every dependencies needed by the project. You will need to install those packages from vcpkg: `sfml:x64-windows` `boost-asio:x64-windows` `boost-thread:x64-windows` `boost-property-tree:x64-windows`

<pre class="language-powershell"><code class="lang-powershell"><strong>.\vcpkg\vcpkg install sfml:x64-windows boost-asio:x64-windows boost-thread:x64-windows boost-property-tree:x64-windows</strong></code></pre>

{% hint style="info" %}
Installing can take a little bit of time the first time you install but doesn't reflect on the compiling time of the project as it write the libraries on the disk, more precisely inside the `vcpkg/installed` directory.
{% endhint %}

Dependencies should have been properly installed by now. If you're encountering any issues during dependencies install, refer back to the steps in this section. if the problem persist, please refer to the error message from the terminal and look at the official vcpkg repository if this error was already encountered. You can also file a new bug report at [https://github.com/TEAM-AAAAAAAAAAAAAAAA/RTYPE/issues/new?assignees=\&labels=\&template=bug\_report.md\&title=](https://github.com/TEAM-AAAAAAAAAAAAAAAA/RTYPE/issues/new?assignees=\&labels=\&template=bug\_report.md\&title=)

## How to compile with Visual Studio 17 2022

{% hint style="danger" %}
Compiling with any other compiler on windows is currently unsupported.

Compile at your own risk
{% endhint %}

{% hint style="success" %}
The CMakeSettings.json can be found at the root of the repository, providing an easy configuration of the build toolchain.
{% endhint %}

{% hint style="info" %}
It is recommended to have a valid installation of CMake.
{% endhint %}

### Things to remember when compiling our project <a href="#remember-when-compiling" id="remember-when-compiling"></a>

The cmake variable `SFML_DIR`  shall always be set to the installation path of sfml, wether it's installed with vcpkg or not.

If you are using Visual Studio, you should be able to launch directly the solution by loading the directory as a CMake project.

If you want to compile using the CLI. You can do so by first, configure the build folder:

```
cmake -S . -B build -DCMAKE_BUILD_TYPE=Debug -DCMAKE_TOOLCHAINFILE='vcpkg/scripts/buildsystems/vcpkg.cmake' -DSFML_DIR='vcpkg/installed/x64-windows/share/sfml' -DCMAKE_WINDOWS_EXPORT_ALL_SYMBOLS=TRUE
```

You'll then need to build the project:

```
cmake --build build -j 10
```

## Resources

* VCPKG
  * Official website: [https://vcpkg.io/](https://vcpkg.io/)
  * Official github repository: [https://github.com/microsoft/vcpkg](https://github.com/microsoft/vcpkg)
* SFML
  * Official website + documentation : [https://www.sfml-dev.org](https://www.sfml-dev.org)
  * Official github repository: [https://github.com/SFML/](https://github.com/SFML/)
*
