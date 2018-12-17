# RPi Card Scanner
An expandable IoT system that scans an RFID card, authenticates with a database, sends a value over a BLE serial connection, and then completes a designated task.

To run the Card Scanner program WITHOUT Bluetooth:

1.	Open the terminal. Type the following line by line
2.	cd ~
3.	cd Desktop/card_scanner
4.	python clean_no_ble.py


To run the Card Scanner program WITH Bluetooth:

1.	Supply power to the Arduino and make sure that the power light is blinking on the HC05 Bluetooth module
2.	Once the Arduino/HC05 has power, switch over to the Pi and connect to the HC05 through serial connection (see pictures below)
3.	Open the terminal. Type the following line by line
4.	cd ~
5.	cd Desktop/card_scanner
6.	python clean.py

Understanding the other files in the “card_scanner” folder

•	login_manager.csv

    o	This is the file that the main script writes to every time a card is scanned. Every scan is time-stamped and is also         logs the users name/unique identifier. If the user is new, just the time-stamp and unique identifier is logged.
•	stored_data.csv

    o	This file is the local database that stores the first/last name and the unique identifier of the user’s ID. In order        to add a user to the database, scan their ID and you will see a message on the LCD screen that reads: “New User .. ID:        _______”. Remember this ID number and input the value into a new row in the database. Proceed by entering that users          first and last name into the columns that follow “ID”.
•	Stored_data_backup.csv

    o	This is a backup of the original “stored_data.csv” file. Given that the python script is reading and writing to the csv     file, I wanted to have a backup incase the file unexpectedly corrupted.
