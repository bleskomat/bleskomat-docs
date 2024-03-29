# Bleskomat Coins ATM

## Platform configuration

In Bleskomat Platform go to Devices > Device Settings

| Name                         | Description                                                                                                                                                                         |
| ---------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| _Reference Phrase_           | Two random words from Bip39 list used to identify the device.                                                                                                                       |
| _Device Type_                | What Bleskomat device you are configuring.                                                                                                                                          |
| _Fiat Currency_              | The fiat currency that the device is going to accept. It requires hardware configuration so it is not possible to only change it here and make it work.                             |
| _Exchange Rates_             | The provider used for the exchange rate that will be done at the moment for each trade.                                                                                             |
| _Fee Percent (%)_            | Percentage of the fee that will be applied to every trade. This is how you make money.                                                                                              |
| _Fixed Fee_                  | A fixed fee denominated in the fiat currency of the device. This is how you make money.                                                                                             |
| _Custom Invoice Memo Prefix_ | If set, this will replace the default invoice memo prefix - e.g. Bleskomat (absurd cake). Your ATM customers will see this in the memo field of their wallet application's invoice. |

## Preparing board for hardware configuration

The only think you need, is to take the Bleskomat Board from the case and connect it with USB to your computer using the CP2101 connector that was provided with your device.

- Disassembling the Bleskomat Board

<video controls muted>
  <source src="./assets/disassembly-bleskomat-coin-board.mp4" type="video/mp4">
</video>

- Connecting Bleskomat Board to your computer with provided CP2101

![](./assets/bleskomat-coins-board-connected.jpeg)

You have to make sure that Bleskomat Board switch is set to "Firmware" so we can configure it.

<video width="320" controls muted>
  <source src="./assets/connect-blesko-board-to-cp2101--computer-firmware-connector.mp4" type="video/mp4">
</video>

## Hardware configuration from Bleskomat Platform

Once you have the board out of the box you connect it to your computer with USB and the Bleskomat Platform will manage the configurations for you.

- If you are on Windows you should install driver https://www.silabs.com/developers/usb-to-uart-bridge-vcp-drivers?tab=downloads and download the file with name "CP210x Windows Drivers".
- If you are on Linux probably you will have to give permissions to your user to access USB running the command: "`sudo chown ${USER}:${USER} /dev/ttyUSB0`"

In the Bleskomat board there are 2 buttons (Boot and Flash). You will be asked to push those buttons during firmware update as it follows:

- Keep "FLASH" button pressed while you pressed and release "BOOT" button. Once the Firmware updated has concluded you should press "BOOT" button alone.

Steps:

1. Connect Bleskomat board to CP2101 provided
1. Make sure that the switch in the Bleskomat Board is set to "FIRMWARE"
1. Connect Bleskomat board to your computer USB
1. Open a supported browser (Google Chrome) with your platform account and go to Devices > Device Settings > Hardware configuration
1. Click on "Connect" and the browser should
1. You should see the message "Detecting Firmware"
1. Once "Detecting Firmware" is completed it will ask you to "Update Firmware"
1. After clicking on "Update Firmware" then in Bleskomat Board keep Button "FLASH" pressed while you press "BOOT" and it will trigger update.
1. One the Firmware update is completed it will try to reconnect to device. When you see the message "Reconnecting to device..." then in Bleskomat Board press "BOOT" button.
1. You should now see "Restarting Device" until you see "Done!"
1. You are done here!
1. Before assembling the board back to device make sure the switch in the board is set to PWR

The above described steps are display in the video below for clarification:

<video controls muted>
  <source src="./assets/bleskomat-coins-hardware-configuration.webm" type="video/mp4">
</video>

## Training Coin acceptor to whatever currency you want

> For now we are shipping all Bleskomat coins configured by default for Euro coins. But you can train it for every currency you want.

> Video coming soon!

1. Access To Coin Parameters Setting
   Keep pressing button A till CP is displayed.
   LED displays CP , press button A to select one of six groups of coins.

1. Clean Up All Coin Parameters
   When it displays CP , keep pressing button B till CC is displayed, it will clean up all six
   groups of coin parameters .

1. Add New Coin Parameters
   When it displays CP , press button A to select the needed coin group （C1~C6）, then press
   button B to displays the current coin value stored , deposit coins needed (it prompts "bi" each
   time deposit a coin), when it prompts “bi.bi.bi”and displays F ,it means this group is fully
   stored and don't need to add coins anymore.

   The coin values should go from 1 to 6 being 1 the smallest denomination you are going to use and 6 the biggest.
   For example for Euro coins:
   1 - 0.05
   2 - 0.10
   3 - 0.20
   4 - 0.50
   5 - 1.00
   6 - 2.00

1. Exit Coin Parameters Setting
   After finish coins parameter setting, keep pressing button A for 2 seconds, release after it
   displays 88.
