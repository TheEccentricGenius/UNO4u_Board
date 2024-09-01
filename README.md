# UNO4u_Board

An UNO form factor board with a AVR128DA28 processor.

This board is designed to be the next generation AVR succesor to the UNO R3 using the AVR128DA28 from Microchip.

The board has a number of features, such as a UPDI programming and UART programming onboard.
The on-board UPDI programming means a bootloader can be burned onto the MCU while it is on the board....No more external programmer required for programming via the ISP header!

## Pinout for your Uno 4u board.
<img src="https://github.com/user-attachments/assets/ace9b617-10f3-4a75-8c1e-0d3605528298" width=75% height=75%>

## How to select a upload mode on your Uno 4u board.
<i>Credits for the upload mode design goes to MCUdude.</i>

Locate the upload mode header using the pinout as a guide.
Below the upload mode header will be the words "UART AUTO UPDI", when shipped the AUTO mode is selected.

To select UART mode, move the jumper shunt to above the UART word.
<img src="https://github.com/user-attachments/assets/401de66c-dc3e-477c-8036-e5821abe53e0" width=50% height=50%>

To select UPDI mode, move the jumper shunt to above the UPDI word.
<img src="https://github.com/user-attachments/assets/6cdc2e34-b10d-49fc-a463-ae76ff16d4de" width=50% height=50%>

Return the jumper shunt to AUTO mode if you desire the board to automatically select UART or UPDI.
<img src="https://github.com/user-attachments/assets/5ab9f90d-cd57-4c04-a2b0-1fc12b3dea2e" width=50% height=50%>

## Using the Uno 4u board as a UPDI programmer.
1. Select UPDI mode on the upload mode header using the upload mode jumper.
2. Remove the jumper from the UPDI header.
3. Connect the UPDI chip you desire to program or debug via UPDI, to the UPDI pin on the Uno 4u board.
   <br><i>Refer to the UPDI mode picture for the UPDI output pin.</i></br>
5. Wire your chip to the respective Power pin from the Uno 4u board and the GND pins.
   <br><i>Refer to the pinout for power and GND pins.</i></br>
7. Connect the Uno 4u board to your device via the USB B port.
8. Select the Uno 4u COM port as your programmer and program using UPDI as normal.

## Configuring your Uno 4u board to run in 3.3V mode.
1. Disconnect your board from any power source.
2. Cut the 5V trace as indicated in the photo below.
<img src="https://github.com/user-attachments/assets/057024a6-e163-4ba7-b37c-ae5c70908611" width=50% height=50%>
<br><i>Before soldering across the two pads in the blue box, measure the IOREF pin voltage.</i></br>
4. If the IOREF voltage is less then 5V then, solder across the two pads outlined by the blue box.
5. Reconnect the board to a power source, the IOREF voltage should measure close to 3.3V.
   <br><i>If the IOREF voltage is 5V or considerably less then 3.3V repeat the above steps.</i></br>
6. To return the board back to 5V solder across to the pad with the arrow underneath it, and remove the solder connecting to the 3.3V pad.
