# TCP Protocol 

## 1. Introduction to TCP

Transmission Control Protocol (TCP) is a Transport Layer protocol that provides reliable, connection-oriented communication between devices. It ensures ordered delivery, error detection, retransmission, and flow control.

---

## 2. TCP Header Structure

* Minimum header size: **20 bytes**
* Key fields:

  * **Source Port / Destination Port (16 bits each):** Identify sending and receiving applications.
  * **Sequence Number (32 bits):** Indicates the position of the first byte in the segment.
  * **Acknowledgement Number (32 bits):** Next byte expected by the receiver.
  * **Data Offset:** TCP header length.
  * **Window Size:** Controls flow by indicating available buffer space.
  * **Checksum:** Ensures header and data integrity.
  * **Urgent Pointer:** Used when URG flag is set.
  * **Options:** Such as MSS, Window Scale, SACK, and Timestamps.
 
  <img width="739" height="299" alt="image" src="https://github.com/user-attachments/assets/ed558e74-a9b5-406c-bd74-b5dd224f14e3" />


---

## 3. TCP Flags

* **SYN:** Initiates a TCP session.
* **ACK:** Acknowledges received data.
* **FIN:** Starts connection termination.
* **RST:** Abruptly resets the connection.
* **PSH:** Pushes buffered data to the application immediately.
* **URG:** Indicates urgent data with Urgent Pointer.

Flags can be combined (e.g., `SYN+ACK`, `FIN+ACK`).

---

## 4. TCP 3-Way Handshake

The handshake establishes a connection and synchronizes sequence numbers.

### Step 1: Client → Server

`SYN`, Seq = x

* Client requests session initiation.

### Step 2: Server → Client

`SYN+ACK`, Seq = y, Ack = x+1

* Server accepts and acknowledges client.

### Step 3: Client → Server

`ACK`, Ack = y+1

* Client confirms and the session becomes established.

<img width="782" height="347" alt="image" src="https://github.com/user-attachments/assets/9534ef33-f47b-4c90-9c7f-4b1ae7d110dd" />

---

## 5. Data Transfer

TCP ensures reliable and ordered data delivery using:

* **Segmentation:** Splits data into segments.
* **Sequence Numbers:** Track data ordering.
* **ACKs:** Confirm received data.
* **Sliding Window:** Controls how much data can be sent without waiting.
* **Selective Acknowledgements (SACK):** Efficient retransmission of missing data.

---

## 6. Error Control

* **Checksum:** Detects corrupt data.
* **Timeouts:** Retransmission if ACK not received.
* **Fast Retransmit:** Triggered by duplicate ACKs.
* **RTT/RTO:** Dynamic calculation of retransmission timeout.

---

## 7. TCP 4-Way Termination

A graceful session close normally uses 4 packets:

1. **Client → Server:** `FIN`
2. **Server → Client:** `ACK`
3. **Server → Client:** `FIN`
4. **Client → Server:** `ACK`

The client then enters **TIME_WAIT** to ensure no delayed packets interfere with new sessions.

<img width="489" height="265" alt="image" src="https://github.com/user-attachments/assets/2312d0bd-b1f6-4589-ac20-b9c7a393af90" />


---

## 8. Congestion Control

TCP adapts to network congestion using:

* **Slow Start:** Exponential increase in congestion window.
* **Congestion Avoidance:** Linear growth after threshold.
* **Fast Retransmit / Fast Recovery:** Avoids full slow start after packet loss.


