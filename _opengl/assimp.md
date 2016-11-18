---
title: 'Форматы 3D-моделей и библиотека Assimp'
---

Библиотека Assimp поддерживает множество распространённых форматов моделей со следующими ограничениями:

- анимированные модели успешно загружаются из формата MD5
- статичные модели успешно загружаются из форматов MD5, MD3, MD2, BLEND, 3DS, OBJ

## Форматы MD5, MD3, MD2 (`*.md5mesh`, `*.md5anim`, `*.md2` и т.д.)

Формат моделей MD5 был разработан компанией idSoftware для Doom III, игры жанра шутер от первого лица. В этом формате данные о поверхностях модели и об анимациях хранятся в разных файлах:

- геометрические данные (включая скелет модели) хранятся в файлах `*.md5mesh`
- файлы анимации хранятся в файлах `*.md5anim`

Формат полностью поддерживает скелетную анимацию и скиннинг вершин. Формат является текстовым, информация о моделях хранится в кодировке ASCII в виде, похожем на YAML. Текстуры хранятся в отдельных файлах (обычно TGA, DDS).

Форматы моделей MD2 и MD3 считаются старыми, но их до сих пор можно встретить в сети. Они разрабатывались для ранних игр компаннии Id Software, таких как Quake и Doom / Doom II.

### Экспорт из Blender

Экспорт моделей из Blender в формат MD5 возможен с помощью скрипта `io_export_md5.py`. Скрипт [был опубликован на форуме katsbits.com](http://www.katsbits.com/smforum/index.php?topic=167.0).

- Обратите внимание, что работоспособность скрипта может быть нарушена в новых либо слишком старых версиях Blender, следует внимательно выбирать версию скрипта и версию Blender.
- [На github есть доработанный скрипт для Blender 2.77](https://github.com/pink-vertex/blender_addon_md5)

### Где скачать

Скачать примеры моделей в формате MD5 можно в следующих источниках:

- [katsbits.com](http://www.katsbits.com/download/models/#md5)

## Формат Blender (`*.blend`)

Данный формат используется для сохранения и загрузки моделей в [Blender](https://www.blender.org/) (открытом редакторе 3D-моделей). К сожалению, формат представляет из себя бинарный снимок памяти внутренних структур данных Blender, и поэтому сторонним программам и библиотекам трудно его разбирать. В результате Assimp не поддерживает загрузку костей и анимаций из моделей Blender.

## Формат 3D Studio Max (`*.3ds`)

## Формат Wavefront OBJ (`*.obj`)