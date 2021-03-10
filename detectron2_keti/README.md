# 객체, 분할 모델 

## Reference code

### Detectron2

* Detectron2는 최첨단 객체 감지 알고리즘을 구현하는 Facebook AI Research의 차세대 소프트웨어 시스템 

* 이전 버전인 [Detectron](https://github.com/facebookresearch/Detectron/)을 완전히 재작성한 것으로 [maskrcnn-benchmark](https://github.com/facebookresearch/maskrcnn-benchmark/)를 기반으로 모델을 구성함

### Detectron2 official code

Facebook AI Research에서 만든 Detectron2 공식 GitHub 주소

https://github.com/facebookresearch/detectron2

## 실행 환경 세팅

Docker 이미지를 이용하여 실행 환경 세팅
docker 실행 방법은 docker [README.md](https://github.com/swhan0329/KETI_NIA2/blob/master/detectron2_keti/docker/README.md) 파일을 참고

## Test 방법

1. 객체 검출, 분할 도커 컨테이너 실행 및 접속

```bash
docker start detectron2
docker attach detectron2
```


