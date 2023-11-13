
**Disciplina**: UCP1 - Tecnologia e Voo com Drones
**Profs**.: Camilo Barreto e Thiago Cappareli
**IFTM - Campus Uberlândia Centro**


## Voo Simples:

1. Decolar;
2. Subir 100cm;
3. Rotacionar 180 graus no sentido horário;
4. Descer 50cm;
5. Rotacionar 180 graus no sentido anti-horário;
6. Pousar;

```protobuf
from djitellopy import Tello

tello = Tello()

tello.connect()
tello.takeoff()

tello.move_up(100)
tello.rotate_clockwise(180)
tello.move_down(50)
tello.rotate_counter_clockwise(180)

tello.land()
tello.end()
```

## Voo em Quadrado:

```protobuf
from djitellopy import Tello
import time

lado_do_quadrado = 50

tello = Tello()

tello.connect()
tello.takeoff()

tello.move_up(100)

for i in range(4):
    tello.move_forward(lado_do_quadrado)
    time.sleep(2)
    tello.rotate_clockwise(90)
    time.sleep(2)

tello.land()
tello.end()
```

## Streaming de Vídeo:

```protobuf
from djitellopy import Tello
import cv2

# Inicializa o Tello
tello = Tello()
tello.connect()

# Inicializa o OpenCV
cv2.namedWindow("Tello Video Stream", cv2.WINDOW_NORMAL)

# Começa o streaming de vídeo
tello.streamon()

# Loop principal para receber e exibir o vídeo
while True:
    # Captura o quadro de vídeo do Tello
    frame = tello.get_frame_read().frame

    # Exibe o quadro
    cv2.imshow("Tello Video Stream", frame)

    # Se a tecla 'q' for pressionada, sai do loop
    if cv2.waitKey(1) & 0xFF == ord('q'):
        break

# Encerra o streaming de vídeo e desconecta o Tello
tello.streamoff()
tello.end()
cv2.destroyAllWindows()
```
