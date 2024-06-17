![LOGO IPSC-EM](../E.%20Assets/logo_ispc_em.png)

# **Palabra de configuración (__CONFIG)**  
Define la configuración de los fusibles, los cuales configuran el comportamiento del microcontrolador. El detalle de su implementación está en el capítulo 14 (pag. 97) del data sheet. 
## **Fusibles**  
**_CP_OFF (Code Protection)**  
En off desactiva la protección del código del programa, permitiendo que se pueda leer y escribir la memoria de programa.  
  
**_CPD_OFF (Data Code Protection)**  
En off desactiva la protección del código de datos, permitiendo que se pueda leer y escribir la EEPROM de datos.  
  
**_LVP_OFF (Low Voltage Programming)**  
En off desactiva la programación en bajo voltaje, lo que generalmente significa que se usará un voltaje más alto (normalmente alrededor de 12V) para la programación.  
  
**_BODEN_ON (Brown-Out Detect Enable)**  
En on activa la detección de brown-out, lo que reiniciará el microcontrolador si el voltaje cae por debajo de un cierto nivel seguro.  
  
**_MCLRE_OFF (Master Clear Enable)**  
En off desactiva el pin MCLR (Master Clear), permitiendo que se use como una entrada digital en lugar de como un pin de reinicio.  
  
**_PWRTE_ON (Power-up Timer Enable)** 
En on activa el temporizador de encendido, que introduce un retraso al inicio del microcontrolador para estabilizar el voltaje de alimentación antes de ejecutar el código.  
  
**_WDTE_OFF (Watchdog Timer Enable)**  
En off desactiva el temporizador watchdog, el cual reiniciar el microcontrolador si no se restablece periódicamente, esto ayuda a recuperar el control en caso de que el software falle.  
  
**_INTOSC_OSC_NOCLKOUT (Internal Oscillator, No Clock Out)**  
Selecciona el oscilador interno como la fuente de reloj y desactiva la salida del reloj (el reloj no se enviará a un pin externo). 
  
## **Resumen**  
```asm
__CONFIG _CP_OFF & _CPD_OFF & _LVP_OFF & _BODEN_ON & _MCLRE_OFF & _PWRTE_ON & _WDTE_OFF & _INTOSC_OSC_NOCLKOUT  
```
Esta configuración especifica que el microcontrolador se inicializará de la siguiente menera:  
 - Protección de código de programa desactivada.  
 - Protección del código de datos desactivada.  
 - Programación en bajo voltaje desactivada.  
 - Detección de brown-out activada.  
 - MCLR desactivado para poder ser usado como entrada digital.  
 - Temporizador de encendido activado.  
 - Temporizador watchdog desactivado.  
 - Oscilador interno como fuente de reloj sin salida de reloj externa.