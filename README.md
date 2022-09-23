# vertexai-pipeline-tutorial
Google Vertex AI Pipelines 튜토리얼 노트북 파일입니다.


# Vertex AI 들어가기
이 실습에서는 Google Cloud에서 제공되는 최신 AI 제품을 사용합니다. [`Vertex AI`](https://cloud.google.com/ai-platform-unified/docs?utm_source=codelabs&utm_medium=et&utm_campaign=CDR_sar_aiml_vertexio_&utm_content=-) 는 Google Cloud 전반의 ML 제품을 원활한 개발 환경으로 통합합니다. 이전에는 AutoML로 훈련된 모델과 커스텀 모델에 별도의 서비스를 통해 액세스할 수 있었습니다. 새로운 오퍼링은 다른 신제품과 함께 이 두 가지를 단일 API로 결합합니다. 기존 프로젝트를 Vertex AI로 마이그레이션할 수도 있습니다.  

Vertex AI에는 모델 교육 및 배포 서비스 외에도 Vertex Pipelines(이 실습의 초점), 모델 모니터링, 기능 저장소 등을 비롯한 다양한 MLOps 제품이 포함되어 있습니다. 아래 다이어그램에서 모든 Vertex AI 제품 오퍼링을 볼 수 있습니다.  

![](https://codelabs.developers.google.com/static/vertex-pipelines-intro/img/vertex-overview.png)

** ML 파이프라인이 유용한 이유는 무엇입니까? **
자세히 알아보기 전에 먼저 파이프라인을 사용하려는 이유를 이해하겠습니다. 데이터 처리, 모델 교육, 초매개변수 조정, 평가 및 모델 배포를 포함하는 ML 워크플로를 구축한다고 상상해 보십시오. 이러한 각 단계는 서로 다른 종속성을 가질 수 있으며 전체 워크플로를 단일체로 취급하면 다루기 어려워질 수 있습니다. ML 프로세스를 확장하기 시작할 때 팀의 다른 사람들과 ML 워크플로를 공유하여 그들이 실행하고 코드에 기여할 수 있도록 할 수 있습니다. 신뢰할 수 있고 재현 가능한 프로세스가 없으면 이 작업이 어려워질 수 있습니다. 파이프라인을 사용하면 ML 프로세스의 각 단계가 자체 컨테이너입니다. 이를 통해 단계를 독립적으로 개발하고 각 단계의 입력 및 출력을 재현 가능한 방식으로 추적할 수 있습니다. 클라우드 환경의 다른 이벤트를 기반으로 파이프라인 실행을 예약하거나 트리거할 수도 있습니다.

`tl;dr` : 파이프라인은 ML 워크플로 를 자동화 하고 재현 하는 데 도움이 됩니다.