
**Disciplina**: UCP1 - Tecnologia e Voo com Drones
**Profs**.: Camilo Barreto e Thiago Cappareli
**IFTM - Campus Uberlândia Centro**

## Comandos de Configuração:

- **Importando a Biblioteca:**

```python
from djitellopy import Tello
```

- **Conectar-se ao Tello:**

```python
from djitellopy import Tello

tello = Tello()
tello.connect()
```

- **Definir a Velocidade Máxima do Drone:**

```python
# Defina a velocidade para 50 cm/s
tello.send_command("speed 50")  
```

- **Definir a Altitude Máxima:**

```python
# Defina a altitude para 100 cm
tello.send_command("altitude 100")  
```

- **Definir o Tempo de Voo Máximo:**

```python
# Defina o tempo de voo para 300 segundos
tello.send_command("time 300")  
```

- **Alterar a Taxa de Transmissão de Vídeo:**

```python
# Defina a taxa de bits do vídeo para 2 Mbps (ajuste conforme necessário)
tello.send_command("video bit_rate 2")  
```

---

## Comandos Básicos de Voo:

- **Decolar:**

```python
tello.takeoff()
```

- **Pousar:**

```python
tello.land()
```

- **Subir/Descer:**

```python
tello.move_up(altura_em_cm)  # Subir
tello.move_down(altura_em_cm) # Descer
```

- **Mover para Frente/Trás/Esquerda/Direita:**

```python
tello.move_forward(distancia_em_cm) # Frente
tello.move_back(distancia_em_cm)    # Trás
tello.move_left(distancia_em_cm)    # Esquerda
tello.move_right(distancia_em_cm)   # Direita
```

- **Rotacionar:**

```python
tello.rotate_clockwise(angulo_em_graus)         # Sentido horário
tello.rotate_counter_clockwise(angulo_em_graus) # Sentido anti-horário
```

## Comandos de Foto e Vídeo:

- **Tirar Foto:**

```python
tello.take_picture()
```

- **Iniciar/Parar Gravação de Vídeo:**

```python
tello.start_video()
tello.stop_video()
```
