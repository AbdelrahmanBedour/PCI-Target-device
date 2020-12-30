# PCI-Target-device
-PCI target using Verilog, it receives commands from master and starts acting according to it.
-Target can identify if the master is calling it’s address or not.
-Target perform read/write operation with different scenarios for each operation
-An 8 words(32-bit) register is used as a memory in the target and another 8 words cache memory as storage in case of overflow in of registers memory.
-Target address is assigned as 32’h111111xxx with the last 3 bits determining which register to perform the operation on


### Target opreates as follows:
  1. When the PCI target device receives the command and recognize its address, the
    a. The DEVSEL should be configured properly (asserted low at certain time).
    b. The TRDY should be configured properly (asserted low at certain time).
  2. If the received command in PCI target device is a read operation.
    a. The target device should start sending out a frame upon having FRAME signal
    asserted to low.
    b. The target device should stop sending out a frame upon having FRAME signal
    asserted to high.
  3. If the received command in PCI target device is a write operation.
    a. The target device should start saving the received data in an internal storage
    with respect to byte enable (BE) bits upon having FRAME signal asserted to low.
    b. The target device should stop saving the received data in internal storage upon
    having FRAME signal asserted to high.
