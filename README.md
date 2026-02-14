# 🚀 Bare-Metal ILI9341 Library Port (HAL-Free)
**A high-performance, register-level port of the ILI9341 library for STM32F446RE.**

---

## 🛠️ The Evolution: From HAL to Bare-Metal
This is a comprehensive refactor of [martnak's STM32-ILI9341 library](https://github.com/martnak/STM32-ILI9341). While the original library relied on the ST HAL, this port represents a complete **"HAL Purge,"** replacing heavy abstractions with direct register manipulation for maximum throughput and minimum CPU overhead.

### 🧠 Technical Conquests: "Brain Surgery" V2.0
To achieve a zero-dependency architecture, the following engineering was performed:

*   **⚡ Bare-Metal SPI Pipeline:** Replaced `HAL_SPI_Transmit` with a custom, high-speed SPI driver. This utilizes direct `DR` (Data Register) writes and precise `TXE` (Transmit Empty) and `BSY` (Busy) flag monitoring to ensure perfect signal integrity at high frequencies.
*   **🔌 Direct GPIO Control:** Replaced all `HAL_GPIO_WritePin` calls with my custom `gpiox.c` driver, utilizing the `BSRR` registers for atomic, single-cycle pin toggling.
*   **🧩 Generic Data Handling:** Implemented a `void*` pointer strategy for `SPI2_TransmitBuffer`, allowing the library to handle `uint8_t`, `unsigned char`, and `uint16_t` pixel data seamlessly without compiler warnings or unnecessary stack usage.
*   **🛠️ Hardware Optimization:** The library is now tuned for the **STM32F446RE** running at **180MHz**, with optimized SPI prescalers to handle the increased bus speeds.

---

## 📂 Repository Structure
*   📂 **`ILI9341_STM32_Driver.c/h`**: The low-level transport layer. All HAL code has been stripped and replaced with register-level logic.
*   📂 **`ILI9341_GFX.c/h`**: The graphics engine (lines, shapes, text), now calling my custom bare-metal transport functions.
*   📦 **Dependencies**: This library is designed to work with my [stm32-baremetal-drivers-F446RE](https://github.com/YOUR_USERNAME/stm32-baremetal-drivers-F446RE) library.

---

## 🚀 How to Use

1.  Include the `ILI9341` folders in your project.
2.  Ensure your **SPI2** and **GPIO** pins (CS, DC, RST) are initialized using the bare-metal drivers.
3.  Configure your "USER DEFINITIONS" in `ILI9341_STM32_Driver.h`.
4.  **Crucial:** The library uses high-speed SPI. If using long jumper wires on a breadboard, ensure you set your SPI prescaler to a stable value (e.g., `/4` or `/8` on a 45MHz APB1 bus).

### Example Initialization
```c
// 1. Init SPI and GPIO
Usart2_init(115200); // For printf debugging
ILI9341_Init();      // Calls my bare-metal SPI & GPIO logic

// 2. Start Drawing
ILI9341_Fill_Screen(BLACK);
ILI9341_Draw_Text("BAVREX ENGINEERING", 40, 100, BLUE, 2, BLACK);
