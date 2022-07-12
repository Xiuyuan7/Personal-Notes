# Connecting to a Network

**Subnetwork Layer**
![image-20220301155027222](C:\Users\11151\AppData\Roaming\Typora\typora-user-images\image-20220301155027222.png)

**Network performance**

- **Bandwidth**
  - Definition: the number of bits that can be transmitted over the network in a certain period of time.
  - 100 Mbps: transfer 100 M bits per second.
  - Can be defined for **a single link** or **end-end channel**.
  - ![image-20220301155432520](C:\Users\11151\AppData\Roaming\Typora\typora-user-images\image-20220301155432520.png)
  - ![image-20220301155450142](C:\Users\11151\AppData\Roaming\Typora\typora-user-images\image-20220301155450142.png)

- **Throughput**

  - Definition: the **measured performance** of a system.
  - The throughtput is smaller than the bandwidth of a link due to **efficiency problems**.
    - Intervals between packets.
    - Packets collision.
    - Network congestion.
    - ...

- **Latency (delay)**

  - Definition: describe how long it takes a message to travel from one end of the network to the other.
  - Can be defined for **a single link** or **end-end channel**.
  - Measured strictly in terms of time.
  - **Round trip time (RTT)** is more important sometime.

  - **Latency = Propagation + Transmit + Queue**
    - Propagation = Distance / Speed of Light
    - Transmit = Size / Bandwidth

- **Latency * Bandwidth**
  - Definition: the volume of the **maximum number of bits** that could be in transit at any given isntant.
  - **Most of time, RTT is used in the product.**

- **Common Units**
  - B: bytes
  - b: bits
  - K (Kilo): 2^10 = 10^3
  - M (Mega): 2^20 = 10^6
  - Bandwidth: 1 Mbps = 10^6 bits/s
  - Message size: 1 MB = 10^6 bytes
  - Rough RTT values: 100 ms for cross-country and 1 ms for local network

- **Transfer Time**
  - TransferTime = RTT + TransferSize/Bandwidth

- **Throughput**
  - Throughput = TransferSize/TransferTime

# Encoding

**Classes of Links**

- Copper Wire (e.g., Digital Subscriber Line (DSL))

![image-20220301232147996](C:\Users\11151\AppData\Roaming\Typora\typora-user-images\image-20220301232147996.png)

![image-20220301232213426](C:\Users\11151\AppData\Roaming\Typora\typora-user-images\image-20220301232213426.png)

- Coaxial Cable (e.g., Cable TV)

![image-20220301232245708](C:\Users\11151\AppData\Roaming\Typora\typora-user-images\image-20220301232245708.png)

- Optical Fiber (e.g., Fiber-to-the-Home)

![image-20220301232304460](C:\Users\11151\AppData\Roaming\Typora\typora-user-images\image-20220301232304460.png)

- Air/Free Space (e.g., WiFi, 4G/5G) 

![image-20220301232322100](C:\Users\11151\AppData\Roaming\Typora\typora-user-images\image-20220301232322100.png)

![image-20220301232326155](C:\Users\11151\AppData\Roaming\Typora\typora-user-images\image-20220301232326155.png)

**Electromagnetic Wave**

- Wavelength = SpeedOfLight / Frequency
- ![image-20220301232447963](C:\Users\11151\AppData\Roaming\Typora\typora-user-images\image-20220301232447963.png)

- ![image-20220301232455951](C:\Users\11151\AppData\Roaming\Typora\typora-user-images\image-20220301232455951.png)

**Modulation**

- **Varying amplitude, frequency, or phase of the signal to effect the transmitted data.**
- Amplitude modulation: high power -> 1, lower power-> 0.
- Frequency modulation: frequency 1 ->1, frequency 2 -> 0.
- Phase modulation: phase 1 -> 1; phase 2 -> 0.

![image-20220301232755142](C:\Users\11151\AppData\Roaming\Typora\typora-user-images\image-20220301232755142.png)

**Network Adapter**

- A piece of hardware that connects a node to a link.
- Embedded in the mother board or external Plug-ins.
- Two signaling components:
  - One encodes the bits into signals at the sending nodes
  - One decodes signals into bits at the receiving nodes

![image-20220301233029456](C:\Users\11151\AppData\Roaming\Typora\typora-user-images\image-20220301233029456.png)

**Non-return to Zero (NRZ)**

- Map data value 1 to high signal and map data value 0 to low signal.

![image-20220301233212841](C:\Users\11151\AppData\Roaming\Typora\typora-user-images\image-20220301233212841.png)

- Main problem: a sequence of several **consecutive 1s or 0s**
  - Signal stay unchanged (either high or low) for a long time.
  - **Baseline wander:** the receivers depends on average of signal it has seen so far to distinguish high and low signal.
  - **Synchronization:** the receiver depends on the transition of signals to synchronize its clock.

**Non-return to Zero Inverted (NRZI)**

- The sender makes a **transition from current signal** to encode **1** and **stays at current signal** to encode **0**.

**Manchester Encoding**

- Do an **exclusive OR** of NRZ-encoded data and the clock.
- Problem: It doubles the rate at which signal transitions are made on the link.
- It is only 50% efficient and transmits half of the bits as NRZ/NRZI.

![image-20220301233857640](C:\Users\11151\AppData\Roaming\Typora\typora-user-images\image-20220301233857640.png)

**4B/5B Encoding**

- Insert extra bits into the bit stream so as to break up long sequences of 0s and 1s.
- Every 4 bits are encoded in a 5-bit code.
- The 5 bit-code has **no more than one leading 0 and no more than two trailing 0s**.
- When sent back-to-back, no pair of 5-bit codes result in more than 3 consecutive 0s.
- The resulting 5-bit codes are transmitted using NRZI encoding (NRZI takes care of consecutive 1s).

![4B/5B Substitution Block Encoding Step 4.In this step the conversions of data into 4B/5B will be converted back into numbers using number conversions. This is reverse process of Step 2 Conversion back to binary will be give different encrypted word because of the usage of 4B/5B line encoding. The solution will be 10205099. Here also the conversion can be any one of the following binary/octal/hexadecimal. Step 5.In this step the above obtained number in step 4 10205099 will be considered as the X Value. This will be substituted in the Mathematical Series. Here in the example the sine series is being used. Formulae: -sin(x) = X-X^3/3! + X^5/5! - .........Here X is the encrypted value 10205099. The series is used defined say N=3 then the series will be till X^7/7! Then the final result will be 10205099 -1771333826010.833333+ 246018586945945274.37 = 176887364014124447176.45856481478. Use the round off function to get the final encrypted word as 176887364014124447176.  ](https://www.researchgate.net/profile/Bhargav-Balakishnan/publication/51936991/figure/fig4/AS:440164100120579@1481954707641/B-5B-Substitution-Block-Encoding-Step-4In-this-step-the-conversions-of-data-into-4B-5B.png)

- Note that: 5 bit can encode 32 codes:
  - 16 are used for coding
  - 9 are reserved for control signals
  - 7 are not valid based on 4B/5B rule

# Framing

- Definition: the process of breaking sequence of bits into pieces so that both the sender and the receiver know when a piece of data starts and ends.

- Implemented by the network adaptor.

  ![image-20220302135132635](C:\Users\11151\AppData\Roaming\Typora\typora-user-images\image-20220302135132635.png)

**Sentinel Based Approach**

- Binary synchronous communication protocol: BISYNC Protocol

  ![image-20220302135605158](C:\Users\11151\AppData\Roaming\Typora\typora-user-images\image-20220302135605158.png)

  - SYN: synchronization
  - SOH: start of header
  - STX: start of text
  - ETX: end of text
  - CRC: cyclic redundancy check

- Problem: "ETX" may appear in the Body field

- Solutions: Character Stuffing

  - Escape the ETX character by preceding it with a DLE (data-link-escape) character**. DLE is escaped by another DLE.**

**Byte Counting Approach**

![image-20220302140259369](C:\Users\11151\AppData\Roaming\Typora\typora-user-images\image-20220302140259369.png)

- Count field specifies how many bytes are contained in the frame’s body.

- Problem: the transmission error may corrupt the Count field

  - the receiver will accumulate as many bytes as the bad COUNT field indicates

    and then use the error detection field to determine that the frame is bad.

    This is sometimes called a framing error. The receiver will then wait until

    it sees the next SYN character to start collecting the bytes that make up

    the next frame. It is therefore possible that a framing error will cause

    back-to-back frames to be incorrectly received.

**High Level Data Link Control (HLDLC)**

![image-20220302145740677](C:\Users\11151\AppData\Roaming\Typora\typora-user-images\image-20220302145740677.png)

- It views the frame as **a collection of bits** instead of bytes.
- It denotes the beginning and the end of a frame with the distinguished bit sequence 01111110.
- It uses bit stuffing to escape the “01111110” sequence in the body of the frame.
  - Sender: any time 5 consecutive 1s are transmitted, insert a 0 before transmitting the next bit.
  - Receiver: should 5 consecutive 1s arrive, if the current bit is 0, remove it. If it is 1, watch next bit, if it is 0, it is end-of-frame. Otherwise it is a bad frame.

- 100111110001111010011111010
- 10011111**0**0001111010011111**0**010

# Error

**Error Detection**

- Goal: provide a **high probability** of detecting errors combined with a relatively **low number of redundant** bits.

- Send only k error correction bits for an n-bit messages, where k<<n.
  - On Ethernet, for a frame up to 12000 bits (1500 bytes), it only requires a 32 bit CRC code (CRC-32). Redundancy < 0.5%.

- Both sender and receiver knows exactly the same error detection algorithm. 

**Two-Dimensional Parity**

- Add one extra bit to 7-bit code to balance the number of 1s in the frame.
- For each bit position across each of the bytes in the frame, add one extra bit to balance the number of 1s.

![image-20220302152430439](C:\Users\11151\AppData\Roaming\Typora\typora-user-images\image-20220302152430439.png)

- For 42-bit messages, we added 14 bits of redundant messages -> **75% efficiency!** 

- Error detection ability: it detects all 1-, 2-, and 3-bit errors and most 4-bit errors.
  - If there is a single parity bit or single bit in parity byte gets corrupted, it can be detected and corrected.
  - If there are two parity bit error, you will be able to identify it but you can not distinguish whether it is a parity bit error or information bit error (e.g., first two parity bit errors and the first bit of the first two rows are in error).
  - If there is one parity bit error and one bit in parity byte in error, you will be able to detect it, but you cannot distinguish if it is parity bit error or a single bit error (e.g., the first bit of the first row is in error).
  - If there are a combination of parity bit/byte error with information bit error:
    - 2-bits (1 parity bit/byte-bit, 1 information bit): can be founded
    - 3-bits (1 parity bit, 1 bit in parity byte, 1 information bit): can go undetected
    - 4-bits: if they form a rectangular, it can go un-detected.

