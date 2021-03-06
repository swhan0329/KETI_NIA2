# 객체 검출, 분할 모델

## 모델 및 데이터셋 다운로드

1. 소스코드 다운로드

```bash
git clone https://github.com/swhan0329/KETI_NIA2/
```

2. 데이터셋 다운로드

구글 드라이브 또는 AI HUB에 올라와있는 (detection, segmentation) test 데이터셋 다운

* 객체 검출 test 데이터셋

https://drive.google.com/drive/folders/1I2niZ6IKNSq1B6Gr6GS_Vfe-CIfwJ0fb?usp=sharing

* 객체 분할 test 데이터셋

https://drive.google.com/drive/folders/1wGSxuDJSgGs9Pa0rQgwfKxj8E2qw6vU1?usp=sharing


3. 데이터셋 경로 변경

데이터셋을 소스 코드 clone 한 폴더 내부의 detectron2/datasets 로 옮김

* 객체 검출/분할 코드 트리

```
detectron2  
├── configs  
├── datasets  
│   ├── train_BB.json  
│   ├── test_BB.json  
│   ├── train_BB  
│   ├── test_BB  
│   ├── train_PS.json  
│   ├── test_PS.json  
│   ├── train_PS  
│   ├── test_PS  
├── weights 
│   ├── model_final_PS.pth 
│   ├── model_final_BB.pth  
├── demo  
├── detectron2  
├── dev  
├── docs  
├── projects  
├── tests  
└── tools  
```

## 도커 이미지 사용 매뉴얼

1. Docker 이미지 다운로드(객체 검출, 분할 동일)

link: https://drive.google.com/drive/folders/1faCGuDeqO7noYwHAvniXVN7QmyZUX1-m?usp=sharing

2. Docker 이미지 로드

```bash
docker load -i detectron2-keti.tar
```

3. Docker 컨테이너 생성

* source: 코드 및 데이터셋이 있는 폴더

```bash
docker run --gpus all -it --name=detectron2 --ipc=host --mount type=bind,source=/home/super/sw/detectron2,target=/root/share detectron2:v0 
```

4. 테스트 스크립트 실행

```cd detectron2``` 구문을 사용하여 경로를 detectron2로 변경 후, 객체 검출, 분할 테스트를 


* 객체 검출 테스트 스크립트

```bash
python test_BB.py
```

* 객체 분할 테스트 스크립트

```bash
python test_PS.py
```
