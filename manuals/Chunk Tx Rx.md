
#  Chunk Tx Rx

**Summary** Explains the procedure though which chunk data is transmitted when processes are seperated and require communcations using UDP or TCP.

``` mermaid

flowchart TD
  A[Wait For Chunk]  --> B[Get Transmitable Bytes]
  B --> D{Transmitted \n All Bytes}

  D -->  |No| E[Calculate Transmission Size]
  E --> F[Transmit Bytes]
  F --> G[Increment Bytes Transmitted]
  G --> H[Incresement Session Number]
  H ---> D

  D --> |yes| C[Increment Sequence Number]
  C --> A
```
TCP Transmissions

{ | DataHeaderSize [2] | DatagramHeader [23] | Data | }

Data Storage (example)

{ | BaseChunk | JSONChunk | }  

==> BaseChunk = { [ 2 ] [ 1 * (n_source_identifier)] }
				
==> JSONChunk = { [ 2 ] [x] }
