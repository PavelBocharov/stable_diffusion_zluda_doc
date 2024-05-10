# Установка (AMD HIS + ZLUDA)

Source ZLUDA: [https://github.com/vladmandic/automatic/wiki/ZLUDA](https://github.com/vladmandic/automatic/wiki/ZLUDA)\
Source AMD HIS: [https://rocm.docs.amd.com/projects/install-on-windows/en/develop/](https://rocm.docs.amd.com/projects/install-on-windows/en/develop/)\


* Установить GIT
  * 🔗: [https://gitforwindows.org/](https://gitforwindows.org/)
* Установить Python 3.9, 3.10 или 3.11 (на момент мая 2024 с 3.12 не работает)
  * 🔗: [https://www.python.org/downloads/](https://www.python.org/downloads/)
* Установить AMD HIS
  * 🔗: [https://rocm.docs.amd.com/projects/install-on-windows/en/develop/](https://rocm.docs.amd.com/projects/install-on-windows/en/develop/)
* Если старая видеокарта (до AMD Radeon RX 6800) подменить либы
  * 🔗: [https://github.com/vladmandic/automatic/wiki/ZLUDA#replace-hip-sdk-library-files-for-unsupported-gpu-architectures](https://github.com/vladmandic/automatic/wiki/ZLUDA#replace-hip-sdk-library-files-for-unsupported-gpu-architectures)
* Установить Automatic 1111 (**SD.Next** edition)
  * 🔗: [https://github.com/vladmandic/automatic/wiki/ZLUDA#install-or-update-sdnext](https://github.com/vladmandic/automatic/wiki/ZLUDA#install-or-update-sdnext)
  * `git clone https://github.com/vladmandic/automatic`\
    `cd automatic`\
    `webui.bat --use-zluda --debug --autolaunch`



