#Electronic Voting Machine (EVM) Using ATMega32 Microcontroller
Welcome to our Electronic Voting Machine (EVM) project, built using the ATMega32 microcontroller! This project was developed by Team 11 as a secure and efficient voting system with a user-friendly interface, candidate selection, vote counting, and result display. It’s designed to enhance the voting process for elections, ensuring accuracy and ease of use.


#Project Overview
The EVM allows voters to cast their votes securely using a keypad and displays results on an LCD. It features:

PIN Authentication: Ensures only authorized voters can cast votes.
Candidate Selection: Supports four candidates (BJP, INC, AAP, JDS) with a confirmation step.
Vote Counting: Tracks votes and displays results for authorized users (via master key).
Winner Display: Shows the candidate with the most votes or indicates a tie.

This project was developed as part of our coursework by:

Amith A (01FE22BCS116)
Ganesh N (01FE22BCS194)
Gautam N (01FE22BCS219)
Appu S C (01FE22BCS274)

#Features

Secure voting with a 4-digit voter PIN and master key for result access.
4x4 keypad for input and 16x2 LCD for output.
Real-time vote counting and winner determination.
User-friendly interface with clear prompts and feedback.

#Hardware Requirements

ATMega32 microcontroller
16x2 LCD display
4x4 keypad
Crystal oscillator (8 MHz)
Basic components (resistors, capacitors, etc.)
AVR programmer (e.g., USBasp)

#Software Requirements

AVR-GCC compiler
AVRDude for programming the ATMega32
IDE like AVR Studio or PlatformIO

#Setup Instructions

(1)Hardware Setup:

Connect the 16x2 LCD to PORTD (data) and PORTB (control pins: RS, RW, EN).
Connect the 4x4 keypad to PORTA.
Ensure the ATMega32 is powered and connected to an 8 MHz crystal oscillator.
Refer to the circuit diagram (add your diagram to the images/ folder and update the link).


(2)Software Setup:

Install AVR-GCC and AVRDude on your system.
Clone this repository:git clone https://github.com/your-username/EVM-ATMega32.git


Navigate to the src/ folder and compile evm.c:avr-gcc -mmcu=atmega32 -DF_CPU=8000000UL -Os -o evm.elf evm.c
avr-objcopy -O ihex evm.elf evm.hex


Flash the .hex file to the ATMega32 using AVRDude:avrdude -c usbasp -p m32 -U flash:w:evm.hex




(3)Usage:

Power on the EVM.
Enter the initial security key (7676) to start the system.
Voters enter their 4-digit PIN (4016) to vote or the master key (1234) to view results.
Select a candidate (1-4) and confirm with the = key.
Master users can choose to display total votes or the winner.



#Project Structure
EVM-ATMega32/
├── src/
│   └── evm.c             # Main source code
├── docs/
│   └── project_report.md # Detailed project report
├── images/
│   └── evm_photo.jpg     # Photos or diagrams (optional)
├── README.md             # This file
├── LICENSE               # MIT License
└── .gitignore            # Git ignore file

#Code Explanation
The code (src/evm.c) implements:

LCD Functions: Initialize and display text on a 16x2 LCD.
Keypad Input: Reads input from a 4x4 keypad for PINs and votes.
PIN Authentication: Validates voter and master PINs.
Voting Logic: Records votes and confirms selections.
Result Display: Shows vote counts or the winner for master users.


Happy voting! 🗳️
