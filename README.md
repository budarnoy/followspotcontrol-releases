# FollowSpotControl — выпуски

Здесь лежат только установщики FollowSpotControl и описание каждой версии.
Отсюда программа узнаёт о новых версиях и ставит их сама:
Settings → Preferences → Updates.

## Первая установка

Откройте [последний выпуск](../../releases/latest) и скачайте файл для своей
системы.

FollowSpotControl бесплатен; при установке он показывает лицензионное
соглашение (EULA). Сайт —
[followspotcontrol.stagevision.kz](https://followspotcontrol.stagevision.kz).

- **macOS** — `FollowSpotControl.<версия>.dmg`: перетащите программу в
  Applications; текст соглашения лежит в образе рядом с ней. Нужны macOS
  14.4 или новее и Mac на Apple Silicon.
- **Windows** — `FollowSpotControl.<версия>.exe`: ставит программу в Program
  Files, добавляет ярлык, открытие `.bvs` двойным щелчком и правила
  брандмауэра для Art-Net и NDI®. NDI на Windows берётся из NDI Runtime
  ([ndi.video/tools](https://ndi.video/tools/)).

Программа не подписана сертификатом Apple или Microsoft, поэтому система
при первом запуске предупреждает о ней:

- **macOS:** правой кнопкой по программе → **Open** → **Open**; если не
  открывается — System Settings → **Privacy & Security** → **Open Anyway**.
- **Windows (SmartScreen):** **More info** → **Run anyway**.

## Контрольные суммы

Начиная с 4.0.0-beta.1 суммы стоят в конце описания выпуска: строка
«SHA-256» раскрывается щелчком. Сумма скачанного файла должна совпасть со
строкой для него, иначе файл скачан не до конца — скачайте его снова.

- **macOS** (Terminal): `shasum -a 256 FollowSpotControl.<версия>.dmg`.
- **Windows** (PowerShell): `Get-FileHash .\FollowSpotControl.<версия>.exe -Algorithm SHA256`,
  или `certutil -hashfile FollowSpotControl.<версия>.exe SHA256`.

## Исходники Qt и FFmpeg

Программа использует Qt 6.12 (LGPLv3) и FFmpeg 9.0.1 (LGPLv2.1). Их
исходники — отдельный выпуск [sources-qt6.12.0-ffmpeg9.0.1](https://github.com/budarnoy/followspotcontrol-releases/releases/tag/sources-qt6.12.0-ffmpeg9.0.1):
использованные модули Qt, наши изменения qtbase (`.patch`),
`ffmpeg-9.0.1.tar.gz` и строка, с которой FFmpeg собран
(`ffmpeg-9.0.1-configure.txt`). Ссылка на него — в конце описания каждого
выпуска, собранного с ними.

## Конфиденциальность

Программа ничего не отправляет о вас, вашем компьютере и ваших шоу. В
интернет она обращается только к GitHub — узнать о новой версии (отключается
в Settings → Updates) и скачать выбранную — и к GDTF Share, когда вы сами
входите туда в Fixture Library.

NDI® is a registered trademark of Vizrt NDI AB — [ndi.video](https://ndi.video).
Art-Net™ Designed by and Copyright Artistic Licence.

## Обновление и возврат к прежней версии

Программа при запуске спрашивает GitHub о новой версии; найденная видна
справа в строке состояния. В Settings → Preferences → Updates — все версии с
описанием. Кнопка ставит выбранную: программа скачивает установщик, сверяет
его контрольную сумму, закрывается (сначала спросив о несохранённом шоу),
ставит версию и открывается снова с тем же шоу.

Если с новой версией что-то не так, там же выберите прежнюю и нажмите
Install. Шоу, сохранённое новой версией, старая может не открыть: держите
копию.
