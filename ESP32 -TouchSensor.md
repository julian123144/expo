# ESP32 - Sensor táctil


Esta Práctica explica cómo utilizar el Sensor Táctil en el ESP32
## Hardware utilizado en esta práctica

- 1 módulo de desarrollo ESP-WROOM-32
- 1 cable micro USB.
- 1 × LED
- 1 × placa de pruebas
- 5 × cables de puente
- 1 x KY-036 Touch
- 1 resistencia de 220 ohmios

## Especificacion tecnicas
- Emite una señal si se tocó la pica de metal del sensor.
- Salida digital: en el momento de la detección de contacto, se emitirá una señal.
- Salida analógica: valor de medición directa de la unidad del sensor.
- LED1: muestra que el sensor se suministra con voltaje
- LED2: muestra que el sensor detecta un campo magnético
- Voltaje de funcionamiento: 3.3V – 5V
- interruptor digital salida (0 / 1)

## Usos
El sensor de metal es útil para detectar cuando alguna persona lo toca y diferenciarla de muchas otras cosas, pero también es sensible a la carga de cualquier otro tipo, motivo por el cual no es recomendable su uso en aplicaciones donde se puedan presentar cargas que puedan hacer del error una variable importante.


## KY-036 Sensor Touch
![figura](https://uelectronics.com/wp-content/uploads/2017/06/1.jpg)

## Diagrama de cableado entrel el sensor touch, el esp32 y el led
![cablead](https://scontent.fmty1-1.fna.fbcdn.net/v/t1.15752-9/292282727_764544584997446_661742652498529030_n.png?_nc_cat=107&ccb=1-7&_nc_sid=ae9488&_nc_eui2=AeG3uYXTrorzL-5oAH9WWxWPaPCgFavXXNpo8KAVq9dc2omv_oTOlj6EYnOm-PLlCzAnGnKkczY_Ol5pJ2YwkMdS&_nc_ohc=x8hCjjwtdEkAX-k-_6Q&tn=u49ECc4-MnUvMHJl&_nc_ht=scontent.fmty1-1.fna&oh=03_AVKwqN7o8t57aO8VjNvEkADHb8rjr3CQrNmso_Y61l7oDQ&oe=62F2ABD1)


## ESP32 CODE
```c++
[int Pin_Led=2;
int Pin_Sensor = 5;
#define LED_PINuwu 18  // ESP32 pin GIOP18, which connected to led

void setup() {
  //pinMode(Pin_Led, OUTPUT);
  pinMode(LED_PINuwu, OUTPUT);
  Serial.begin(115200);
  pinMode(Pin_Sensor, INPUT);
}

void loop() {
  int sensor = digitalRead(Pin_Sensor);
   if(sensor==HIGH){
    //digitalWrite(Pin_Led, HIGH);
    digitalWrite(LED_PINuwu, HIGH); // turn on LED
    Serial.print("Me estas tocando \n");
    delay(1000);
   }
   else{
    digitalWrite(LED_PINuwu,LOW);
   }
   digitalWrite(LED_PINuwu, LOW);
}

```

