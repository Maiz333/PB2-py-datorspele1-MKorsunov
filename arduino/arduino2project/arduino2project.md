# SPACHESHIP INTERFACE

Projekts SPACESHIP INTERFACE tika veidots, lai palīdzētu padziļināti iepazīties ar LED diožu un pogu izmantošanu Arduino projektos, radot interaktīvu simulāciju.

## Projektam ir nepieciešami:

 Vienas krāsas LED (x2)
 Citas krāsas LED (x1)
 Rezistors 220 ohm (1x)
 Rezistors 10k ohm (1x)
 Savienošanas vads (x5)
 Poga (1x)

Kad visi vadi ir salikti un kods ir augšupielādēts uz Arduino breadbordu, zaļā LED diode iedegas un paliek ieslēgta, līdz tiek nospiesta poga. Pēc pogas nospiešanas, pārējās divas LED diodes sāk mirgot pēc kārtas. Mirgošanas ātrumu var mainīt programmas kodā.
![1.attēls](arduino2.jpg)
![2.attēls](arduino2.1.jpg)
![3.attēls](arduino2.2.jpg)

### Programmas kods:

```cpp
int switchState = 0;
void setup(){
    pinMode(3, OUTPUT);
    pinMode(4, OUTPUT);
    pinMode(5, OUTPUT);
    pinMode(2, INPUT);
}
void loop(){
    switchState = digitalRead(2);
    if (switchState == LOW) {
        digitalWrite(3, HIGH);
        digitalWrite(4, LOW);
        digitalWrite(5, LOW);
    }
    else {
        digitalWrite(3, LOW);
        digitalWrite(4, LOW);
        digitalWrite(5, HIGH);
        delay(250);

        digitalWrite(4, HIGH);
        digitalWrite(5, LOW);
        delay(250);
    }
}

