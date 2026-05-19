# ESP32 RGB LED Circuit Diagram

This diagram uses **Mermaid.js** syntax. You can view it directly in VS Code (with Markdown Preview), GitHub, or by pasting it into the [Mermaid Live Editor](https://mermaid.live/).

## Schematic

```mermaid
graph TD
    subgraph ESP32_Board
        VCC[+3.3V]
        D2[GPIO D2]
        D4[GPIO D4]
        D5[GPIO D5]
    end

    subgraph RGB_LED_Common_Anode
        LED{RGB LED}
        R_Cathode[Red Cathode]
        G_Cathode[Green Cathode]
        B_Cathode[Blue Cathode]
    end

    subgraph Resistors
        R1[220Ω]
        R2[220Ω]
        R3[220Ω]
    end

    %% Connections
    VCC --- LED
    LED --- R_Cathode
    LED --- G_Cathode
    LED --- B_Cathode

    R_Cathode --- R1 --- D2
    G_Cathode --- R2 --- D4
    B_Cathode --- R3 --- D5

    %% Styling
    style LED fill:#f9f,stroke:#333,stroke-width:2px
    style ESP32_Board fill:#e1f5fe,stroke:#01579b
    style RGB_LED_Common_Anode fill:#fff9c4,stroke:#fbc02d
```

## Wiring Guide

| LED Pin | Component | ESP32 Pin |
| :--- | :--- | :--- |
| **Common Anode** (Longest Pin) | Direct Connection | **3.3V** |
| **Red Cathode** | 220Ω Resistor | **D2 (GPIO 2)** |
| **Green Cathode** | 220Ω Resistor | **D4 (GPIO 4)** |
| **Blue Cathode** | 220Ω Resistor | **D5 (GPIO 5)** |
