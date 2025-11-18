# Safe Vault – Arduino

A smart safe system built with Arduino, featuring RFID card authentication, PIN protection, and optional Bluetooth-based two-factor authentication.

## How It Works

### RFID Authentication
The system uses an MFRC522 RFID reader to scan access cards.  
Stored cards are compared against the scanned UID.  
- **Authorized card →** allows access  
- **Unknown card →** “Unauthorized card” message  

Cards can be added or removed from the configuration menu.

### PIN Security
A 4–6 digit PIN protects the configuration menu.  
The PIN is stored securely using **SHA-256 hashing**.  
Entering the correct PIN unlocks access to system settings.

### Configuration Menu
Accessible after a valid PIN entry.  
The menu allows you to:
- Add new RFID cards  
- View all stored cards  
- Remove selected cards  
- Configure Bluetooth 2FA  
- Set or change the PIN  
- Save and exit configuration mode  

### Normal Operation
When the system is locked:
1. The display prompts the user to **scan a card**.
2. The system checks if the card is stored.
3. If valid, the safe can proceed with PIN or 2FA validation.
4. If invalid, the display shows “Unauthorized card”.

### System Flow
1. **First run:** User must add the first RFID card.  
2. **Locked mode:** Waiting for a card.  
3. **Authorized card:** Optional PIN/2FA verification.  
4. **PIN entry:** Unlocks configuration settings.  
5. **Manage cards and security settings via LCD menu.**

## Hardware Used
- Arduino board  
- MFRC522 RFID reader  
- LCD display (16x2)  
- 3×4 keypad  
- Optional: Bluetooth module for 2FA  

