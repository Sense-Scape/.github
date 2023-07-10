\# System Outline

## Block Diagram

Note: press `ctrl` + `click` to open repositories

``` mermaid
  graph TD;
  Windows_Simulator-->Windows_Processing_Server;
  ESP32_Acoustic_Semsor-->Windows_Processing_Server;
  Windows_Processing_Server-->Python_Development_UI;

  click Windows_Simulator "https://github.com/Sense-Scape/Windows_Sensor_Sim" "Go to";
  click ESP32_Acoustic_Semsor "https://github.com/Sense-Scape/Acoustic_Sensor_ESP32" "Go to";
  click Windows_Processing_Server "https://github.com/Sense-Scape/Windows_Proc_Serv" "Go to";
  click Python_Development_UI "https://github.com/Sense-Scape/Py_Dev_UI" "Go to";
```
