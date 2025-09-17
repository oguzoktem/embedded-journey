\# Week 1 – GPIO Button + LED 🔘💡



This project demonstrates basic \*\*GPIO input/output\*\* and  

\*\*external interrupt (EXTI)\*\* usage on the \*\*STM32F411E-DISCO\*\* board.  

When the USER button is pressed, an onboard LED toggles its state.



\## 📂 Project Details

\- \*\*MCU:\*\* STM32F411VE (Discovery Board)  

\- \*\*IDE:\*\* STM32CubeIDE  

\- \*\*Language:\*\* C (HAL library)  

\- \*\*Files:\*\*

&nbsp; - `Core/Src/main.c` – button interrupt \& LED control code

&nbsp; - `Core/Inc/main.h` – function prototypes

&nbsp; - `.ioc` – pin \& clock configuration



\## 🔌 Hardware Mapping (Onboard)

\- \*\*USER Button\*\* → `PA0` (GPIO\_EXTI0)  

\- \*\*LED\*\* → `PD12` (Green LED) ← \*(can be changed to PD13/PD14/PD15 if desired)\*  



\## ▶️ How It Works

1\. The \*\*USER button\*\* is configured as GPIO input with EXTI interrupt.  

2\. When pressed, the `HAL\_GPIO\_EXTI\_Callback` function is triggered.  

3\. The selected LED pin (`PD12` by default) is toggled using `HAL\_GPIO\_TogglePin`.  



\## 📸 Demo

\- Each button press toggles the Green LED (PD12).  

\- (Later a photo or short demo GIF can be added here.)



\## 📝 Notes

\- Configure PA0 as \*\*No pull\*\* in CubeMX.  

\- \*\*Hardware note:\*\* On the STM32F411E-DISCO board the USER button (PA0) already has an \*\*external pull-down\*\* resistor on the PCB.  

&nbsp; Enabling internal pull resistors is unnecessary and may introduce a small static current draw or form an unintended divider with the onboard resistor.  

\- EXTI0 interrupt enabled in CubeMX.  

\- NVIC interrupt priority configured automatically by CubeIDE.



