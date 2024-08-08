# Projeto Yolo v8
Este projeto utiliza a rede neural Yolo v8 para realizar reconhecimento de imagens.

## Descrição
O objetivo deste projeto é utilizar a rede neural Yolo v8 para realizar reconhecimento de imagens. A rede neural foi treinada com dados próprios e é capaz de detectar objetos em imagens.

## Requisitos
1. Python 3.6 ou superior (até 3.9)
2. PyTorch instalado
3. Biblioteca Ultralytics instalada
4. Um dataset com as imagens que serão usadas
>pode ser elaborado usando o [Roboflow](https://roboflow.com/)

## Instalação
Para instalar a rede neural Yolo v8, siga os passos abaixo:

Instale a biblioteca Ultralytics utilizando pip:
```
pip install ultralytics
```
Instale o PyTorch utilizando pip:
```
pip install torch
```
>Se prefirir, siga os passos de instalação disponíveis em [Por onde começar](https://docs.ultralytics.com/#where-to-start)

## Uso
Para treinar com a base de dados coco8, da Ultralytics:
```python
from ultralytics import YOLO

# carrega o modelo
model = YOLO("yolov8n.yaml")  # constroi um modelo YAML
model = YOLO("yolov8n.pt")  # carrega um modelo pré-treinado (que é recomendado para o treinamento)
model = YOLO("yolov8n.yaml").load("yolov8n.pt")  # constrói a partir do YAML e gera os WHEIGHTS

# treina o modelo
results = model.train(data="coco8.yaml", epochs=100, imgsz=640)
```
Para realizar o reconhecimento de imagens com a rede Yolo:
```python
from ultralytics import YOLO

# carrrega o modelo pré-treinado
model = YOLO("yolov8n.pt")

results = model.train(data="meu_dataset.yaml", epochs=100, imgsz=640) # lembre-se de trocar o caminho "meu_dataset" para a sua base de dados
```
>O treinamento também pode ser feito utilizando o seu própio banco de dados

# Créditos
Os créditos pela programação da rede e pré-treinamento [Ultralytics](https://docs.ultralytics.com/)
