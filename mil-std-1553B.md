What is MIL-STD-1553B
=============
## Concept
MIL-STD-1553B is one of standard protocolsdata for data bus.
There are three types of terminal in the protocol. Bus Controller(BC), Bus Monitor(BM), Remote Terminal(RT). I will call these as BC, BM, RT.
Basically, BC controls all data transmission as its name. All transmission should be processed in Command mode or Response mode. BM receives bus traffic and extracts selected information. It is used only for test. RT is all terminals that is not BC and BM. User can use 32 RT maximum. 
1553B supports synchronous and asynchronous transmission.