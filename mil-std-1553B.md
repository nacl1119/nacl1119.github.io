What is MIL-STD-1553B
=============
<p style="width:800px;">

## Concept
MIL-STD-1553B is one of standard protocolsdata for data bus.

## Terminal Type
There are three types of terminal in the protocol. Bus Controller(BC), Bus Monitor(BM), Remote Terminal(RT). I will call these as BC, BM, RT.

Basically, <b>BC</b> controls all data transmission as its name. All data transmission should be processed in Command mode or Response mode. <b>BM</b> receives bus traffic and extracts selected information. It is used only for test. <b>RT</b> is all terminals that are not BC and BM. User can use 31 RT maximum. 

</p>

## Word Type
1553B has three types of word. <b>Command, Status, Data word</b> Command and Status words are used for management and data word is used to transmit real data between terminals.

<img src='./images/1553B word format.PNG' width='600'>

A 1553B word is consist of some formats of 20 bits. Every words have 3bit of sync and 1bit parity and each's own format.
### Sync pattern
It shall be three bit times. Command word and Status word has same pattern and Data word has reversed pattern than command and status.

### Command Word
Commnad word is used to control other RT in a bus. this word is comprised of  5 elelemets.
 1. **RT address(5b)** - RT address is destination of the command or status word. **The address 31** is used for broadcast only
 2. **Transmit and Receive(1b)** bit - **0** indicates RT is to receive, **1** indicates RT is to transmit
 3. **Subaddress/mode(5b)** - subaddress is used as RT subaddress or mode control. **0 and 31** are reserved for **mode control**.
 4. **Data Word Count/Mode code(5)** - This word is defiend by third word subaddress and mode word. If third word is **subaddress**, this word is **data count**. If third word is **mode**, this word is **mode code**.
 5. **Parity** - we used odd parity.

### Status Word
Status word is response of Command word to BC. This word is comprise of 11 elements.
1. **RT address** - is address of RT which received Command. BC can know it is right response and other RT can know received word is not command for itself.
2. **Message Error** - indicates message Error like wrong command, wrong data transmission, etc.
3. **Instrumentation** - 
4. **Service Request** - 
5. **Reserved(3b)** - 
6. **Broadcast Command Received** - 
7. **Busy** - 
8. **Subsystem Flag** - 
9. **Dynamic Bus Control Acceptance** - indicates that the RT will be **backup BC**.
10. **Terminal Flag** - means RT is broken.
11. **Parity** - 
### Data Word

## TBD
1553B supports synchronous and asynchronous transmission.

<br><br>
# Reference
## MIL-STD-1553B docs
 - https://www.milstd1553.com/wp-content/uploads/2012/12/MIL-STD-1553B.pdf
### Parity bit
odd parity makes sure sending 1553B word contains odd number of 1
even parity makes sure sending 1553B word contains even number of 1
https://blog.naver.com/PostView.naver?isHttpsRedirect=true&blogId=ansdbtls4067&logNo=220886661657

