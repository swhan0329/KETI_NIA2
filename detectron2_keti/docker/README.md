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
│   ├── test_BB  
│   ├── train_PS.json  
│   ├── test_PS.json  
│   ├── train_PS  
│   ├── test_PS  
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
docker run --runtime=nvidia -i -t --name=detectron2 --mount type=bind,source=/home/super/Desktop/yh/detectron2,target=/home/appuser detectron2:v0
```

4. 테스트 스크립트 실행

* 경로는 detectron2로 변경
```bash
cd detectron2
```

* 객체 검출 테스트 스크립트

```bash
python test_BB.py
```

* 객체 분할 테스트 스크립트

```bash
python test_PS.py
```
