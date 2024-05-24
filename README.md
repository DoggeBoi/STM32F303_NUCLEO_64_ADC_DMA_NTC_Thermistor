# STM32F303_NUCLEO_64_ADC_DMA_NTC_Thermistor
This project continues the development of HAL-based DMA ADC voltage sensing using a STM32F303 NUCLEO-64 board, this time incorporating a 100k NTC B3950 thermistor (R2) in a simple voltage divider configuration.

While initial sensing was successful, it was inaccurate using the standard model of t = R0 * e^( T1^(-1) - T0^(-1) ) alongside the voltage divider equation to calculate the temperature. 
To improve accuracy, I used a kitchen thermometer and a glass of water at varying temperatures to gather data points. These data points were then fitted to a curve in Desmos.

The new model (black) showed a significantly reduced error of less than 10^-15. Practically, this translates to an error of approximately ±1°C when tested at 15°C and 85°C.

This approach mitigates the need to account for every hidden variable or inaccuracy within the system or mathematical conversion model. Moreover, switching between two different 
NTC thermistors of the same make resulted in negligible temperature differences, indicating that the code is reusable for future applications such as overtemperature warnings in other devices.


![curve](https://github.com/DoggeBoi/STM32F303_NUCLEO_64_ADC_DMA_NTC_Thermistor/assets/59169880/62b553f8-563f-4134-9bf4-a1e2c86cc860)

