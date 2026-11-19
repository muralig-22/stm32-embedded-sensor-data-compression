
# STM32 Embedded Sensor Data Compression

### Delta Encoding, Bit-Width Reduction & UART Telemetry

## Overview

An STM32-based embedded data compression and serial communication pipeline designed to reduce sensor telemetry payload size using delta encoding and bit-width reduction.

The system processes simulated 24-bit and 16-bit sensor signals, converts encoded differences into 8-bit representations, batches ten samples per packet, and transmits the resulting data through USART2.

## Problem Statement

Embedded systems frequently operate with limited communication bandwidth, memory, and processing resources.

Transmitting raw high-resolution sensor measurements can increase communication overhead and reduce telemetry efficiency.

## Proposed Solution

Implemented a lightweight compression pipeline using delta encoding to represent changes between consecutive sensor samples.

The pipeline includes:

- Simulated 24-bit and 16-bit sensor signals.
- Delta calculation between consecutive samples.
- 8-bit representation of encoded differences.
- Ten-sample packet batching.
- USART2-based serial transmission.

## System Architecture

```text
Simulated Sensor Data
        |
        v
16-bit / 24-bit Samples
        |
        v
Delta Encoding
        |
        v
8-bit Data Representation
        |
        v
10-Sample Packet Formation
        |
        v
USART2 Transmission
```

## Key Features

- Delta-based data compression.
- Processing of simulated 16-bit and 24-bit signals.
- 8-bit encoded representation.
- Packet-based telemetry.
- Ten samples per transmission packet.
- USART2 communication.
- Lightweight embedded implementation.

## Hardware and Software Stack

| Category | Technology |
|---|---|
| Microcontroller | STM32F446RE |
| Language | Embedded C |
| Communication | USART2 |
| Compression | Delta Encoding |
| Data Processing | Bit-width Reduction |
| Development | STM32 development environment |

## Technical Implementation

### 1. Signal Generation

Generated simulated 16-bit and 24-bit sensor signals for testing the compression pipeline.

### 2. Delta Encoding

Calculated differences between consecutive sensor samples instead of transmitting complete raw values.

### 3. Bit-Width Reduction

Represented encoded differences using 8-bit values where the difference range permits.

### 4. Packet Formation

Grouped ten encoded samples into each transmission packet.

### 5. UART Transmission

Transmitted the encoded packets through USART2.

## Engineering Considerations

- Data representation.
- Integer arithmetic.
- Signed difference handling.
- Quantization and reconstruction.
- Packet framing.
- UART throughput.
- Compression efficiency versus reconstruction error.

## Project Outcome

Implemented a lightweight embedded telemetry pipeline demonstrating delta encoding, reduced-width data representation, packet batching, and UART communication.

## Future Enhancements

- Packet sequence numbering.
- CRC-based error detection.
- Adaptive encoding.
- Run-length encoding.
- Lossless reconstruction.
- Compression ratio measurement.
- UART DMA transmission.
- Real sensor integration.

## Applications

- Embedded telemetry.
- Sensor networks.
- Low-bandwidth communication.
- Industrial monitoring.
- Resource-constrained embedded systems.

## Important Note

An 8-bit representation is valid only when the encoded delta fits the supported range or an appropriate escape, scaling, or overflow mechanism is implemented. Compression performance and reconstruction accuracy should be measured against the original signal.

---

**Project Category:** STM32 | Embedded C | Data Compression | UART

**Status:** Firmware Prototype
