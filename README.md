# airodump-ng-not-showing-any-data-Atheros-QCA9377

Setup of QCA9377 wireless adapter drivers for Ubuntu to enable monitor mode

## Check the drivers' location

```SHELL
ls -1 /lib/firmware/ath10k/QCA9377/hw1.0
```

Sample output:

```TEXT
board-2.bin
board.bin
firmware-5.bin
firmware-6.bin
firmware-sdio-5.bin
notice_ath10k_firmware-5.txt
notice_ath10k_firmware-6.txt
notice_ath10k_firmware-sdio-5.txt
```

**Heads-up**: The `firmware-6.bin` will have to be deleted to make the drivers work.

## Creating a backup of current firmware

```SHELL
cp -rv /lib/firmware/ath10k/QCA9377 ~/QCA9377_BAK
```

## Copying drivers

```SHELL
git clone https://github.com/kostkzn/airodump-ng-not-showing-any-data-Atheros-QCA9377.git

cd airodump-ng-not-showing-any-data-Atheros-QCA9377

sudo cp -rTv QCA9377/ /lib/firmware/ath10k/QCA9377

sudo rm -fv /lib/firmware/ath10k/QCA9377/hw1.0/firmware-6.bin
```
