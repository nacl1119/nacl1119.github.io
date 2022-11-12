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

First Commnad word is comprised of  
 1. **RT address** - RT address is destination of the command or status word. **The address 31** is used for broadcast only
 2. **Transmit and Receive** bit - **zero(0)** indicates RT is to receive, **one(1)** indicates RT is to transmit
 3. **Subaddress/mode** - subaddress is used as RT subaddress or mode control. 0 and 31 are reserved for 
 4. **Data Word Count Mode Code**


### Sync pattern
It shall be three bit times. Command word and Status word has same pattern and Data word has reversed pattern than command and status.

1553B supports synchronous and asynchronous transmission.

<br><br>
# Reference
https://www.milstd1553.com/wp-content/uploads/2012/12/MIL-STD-1553B.pdf
