# Real-Time UDP Connection with Simulink

This repository provides a framework for establishing a real-time UDP connection between two PCs on the same WiFi network using Simulink. The project aims to facilitate seamless communication and data exchange between remote systems, leveraging Simulink's capabilities for real-time simulation and control.

## UDP Send Setup

### 1. Add Blocks

- Drag the `UDP Send` block from the Simulink Real-Time library.
- Add the `Pulse Generator`, `Data Type Conversion`, and `Constant` blocks.

### 2. Configure Pulse Generator

- Connect the `Pulse Generator` block to the `Data Type Conversion` block.
- Connect the `Data Type Conversion` block to the data input branch of the `UDP Send` block.
- Set the `Constant` block to a value of 1 and connect it to the length input branch of the `UDP Send` block.
- Open the parameters window for the `Pulse Generator` block:
  - Set `Pulse Type` to `Time-based`.
  - Set `Time(t)` to `Use simulation time`.
  - Set the `Period (secs)` to 5 (for example).
  - Set `Pulse Width (% of period)` to 50.
  - Click `Apply`, then `OK`.

### 3. Configure Data Type Conversion

- Open the parameters window for the `Data Type Conversion` block:
  - Set `Output Data Type` to `uint8`.

### 4. Configure UDP Send Block

- Open the parameters window for the `UDP Send` block:
  - Enter your local IP address and the IP address of the receiver device.
  - For finding your IP address:
    - On Windows, open Command Prompt and type `ipconfig`.
    - On Linux, open Terminal and type `hostname -I`.
  - Specify the UDP port for transmitting data:
    - Ports 1 through 1023 and 5500 through 5560 are reserved for Simulink Real-Time communications.
    - The value `−1` allows the block to use any available port.

## Notes

- Ensure that both PCs are on the same WiFi network.
- Verify that the specified ports are open and not used by other applications.
- Check that both devices can communicate over the network by testing with simple network utilities.

For further assistance, refer to the documentation provided in this repository.
