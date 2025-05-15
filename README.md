# Установка

## Windows (AMD HIS + ZLUDA)

Source ZLUDA: [https://github.com/vladmandic/automatic/wiki/ZLUDA](https://github.com/vladmandic/automatic/wiki/ZLUDA)\
Source AMD HIS: [https://rocm.docs.amd.com/projects/install-on-windows/en/develop/](https://rocm.docs.amd.com/projects/install-on-windows/en/develop/)\\

### Установить GIT

* 🔗: [https://gitforwindows.org/](https://gitforwindows.org/)

### Установить Python

* Python 3.9, 3.10 или 3.11 (на момент мая 2024 с 3.12 не работает
  * 🔗: [https://www.python.org/downloads/](https://www.python.org/downloads/)

### Установить AMD HIS/ROCm

* 🔗: [https://rocm.docs.amd.com/projects/install-on-windows/en/develop/](https://rocm.docs.amd.com/projects/install-on-windows/en/develop/)
* Если старая видеокарта (до AMD Radeon RX 6800) подменить либы
  * 🔗: [https://github.com/vladmandic/automatic/wiki/ZLUDA#replace-hip-sdk-library-files-for-unsupported-gpu-architectures](https://github.com/vladmandic/automatic/wiki/ZLUDA#replace-hip-sdk-library-files-for-unsupported-gpu-architectures)

### Установить Automatic 1111 (**SD.Next** edition)

* 🔗: [https://github.com/vladmandic/automatic/wiki/ZLUDA#install-or-update-sdnext](https://github.com/vladmandic/automatic/wiki/ZLUDA#install-or-update-sdnext)

```bash
git clone https://github.com/vladmandic/automatic
cd automatic
webui.bat --use-zluda --debug --autolaunch
```

## Linux + AMD ROCm

Source SD.Next - [https://github.com/vladmandic/sdnext/wiki/AMD-ROCm](https://github.com/vladmandic/sdnext/wiki/AMD-ROCm)\
Source AMD ROCm - [https://rocm.docs.amd.com/projects/install-on-linux/en/latest/install/quick-start.html](https://rocm.docs.amd.com/projects/install-on-linux/en/latest/install/quick-start.html)

### Установить AMD ROCm

1. Скачать deb и установить - [https://www.amd.com/en/support/download/drivers.html](https://www.amd.com/en/support/download/drivers.html)
2. Через консоль (надо уточнять актуальность):&#x20;

```bash
sudo apt update
wget https://repo.radeon.com/amdgpu-install/6.3.2/ubuntu/noble/amdgpu-install_6.3.60302-1_all.deb
sudo apt install ./amdgpu-install_6.3.60302-1_all.deb
```

3. Скачиваем драйвера и даем пользователю права:

```bash
sudo amdgpu-install --usecase=rocm
sudo usermod -a -G render,video $LOGNAME
# не делал
# sudo apt install rocm
```

### Установка Python

```bash
sudo apt install git python3 python3-dev python3-venv python3-pip
```

### Скачиваем SD.Next

```bash
git clone https://github.com/vladmandic/sdnext
cd sdnext
./webui.sh --use-rocm
```

### Возможная ошибка

Error: Cannot activate python venv

```bash
python3 -c #import venv ran fine without errors
python3 -m venv venv/ #fixed it, thanks for your help
```

## Общие ошибки

* Если происходит хрень то удали папку `venv`, после чего все перекачает и перенастрит - возможно поможет.
