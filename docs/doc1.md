---
id: doc1
title: Installation
sidebar_label: Installation
slug: /
---

Check the [documentation](https://docusaurus.io) for how to use Docusaurus.

## Проект не с CMake 
Если вы не используете CMake как систему сборки, вам стоит попробовать сборки Fresponze SDK, доступные на странице [Releases](https://github.com/suirless/Fresponze/releases) на GitHub.

В каждой архиве есть несколько элементов:
* *include - папка заголовочных файлов Fresponze SDK*
* *bin - папка с готовыми для использования скомпилированные библиотеки (на ваш выбор - release-static, release-dynamic, debug-static, release-dynamic)*

## Подготовка к установке
Библиотека Fresponze при своей сборке может использовать системные пакеты, не прибегая к клонированию исходников зависимостей. Для такого использования требуется установить в вашу систему необходимый набор библиотек через пакетный менеджер, который на каждой системе может отличаться. 

Для использования такого функционала в Windows, вам нужно установить [vcpkg](https://docs.microsoft.com/ru-ru/cpp/build/vcpkg?view=vs-2019) и после настройки вписать эти команды:

```sh
vcpkg install libogg:x64-windows
vcpkg install opus:x64-windows
vcpkg install opusfile:x64-windows
```

Cписок возможных команд для остальных платформ:

```sh
sudo apt-get install libopus-dev libogg-dev libopusfile-dev             // для Debian
sudo dpkg install -y libopus-dev libogg-dev libopusfile-dev             // для Arch
brew install opus ogg opusfile                                          // для macOS with Brew
```

## Клонирование репозитория 

Склонируйте [Fresponze](https://github.com/suirless/Fresponze) в нужную вам директорию и создайте папку для постройки приложения через CMake:

```sh
git clone https://github.com/suirless/Fresponze.git
mkdir build
```

## CMake build

Для сборки библиотеки Fresponze с опциями по умолчанию, введите команды:

```sh
cd build
cmake .. -G"Your Generator"
```

Если же вы хотите собрать библиотеку с дополнительными опциями для сборки, то вам следует изучить список возможных опций для библиотеки Fresponze:

```
BUILD_SHARED_LIBS - Build all libraries as DLL
BUILD_OPUSFILE_API - Use opus as available format for media listener (default - ON)
BUILD_RESONANCE_AUDIO_API - Use Resonance Audio as available emitter for advanced mixer (default - ON)
BUILD_FRESPONZE_STATIC - Build Fresponze as static library (default - OFF)
BUILD_EXAMPLES - Build examples for Fresponze library. (default - OFF)
USE_VCPKG - Use vcpkg instead of source packages (default - OFF)
```

Для использования дополнительных опций сборки, требуется ввести флаг `-D` перед названием опции:
```sh
cmake .. -G"Visual Studio 16 2019" -DBUILD_OPUSFILE_API=OFF 
```

Если же вы используется `vcpkg`, то при запуске CMake требуется установить аргумент `-DCMAKE_TOOLCHAIN_FILE` как путь до vcpkg (см. [здесь](https://vcpkg.readthedocs.io/en/latest/examples/installing-and-using-packages/#cmake))

## После сборки

Для дальнейшей разработки с библиотекой Fresponze, вам следует интегрировать её в ваш CMake проект:
```
add_subdirectory(${FRESPONZE_DIR})
target_link_libraries(your_project Fresponze::fresponze)
```