## LAIDD
# LAIDD_3D-GCN
DILI(Drug-Induced Liver Injury) 예측을 위한 3D-GCN(3D Graph Convolutional Network) 모델을 구현하고 학습함. 

모델 학습은 PyTorch 기반으로 수행되었으며, GPU 가속 환경(CUDA)을 활용하여 효율적인 학습을 진행.
데이터는 DILIrank 공공 데이터셋을 사용하였으며, 약물의 3차원 구조 정보를 반영한 그래프 형태로 변환하여 입력으로 활용함.

훈련 결과, 모델은 그래프 구조의 3차원 공간 정보를 효과적으로 학습하여 독성 예측 성능을 개선함.
클래스 불균형 문제를 완화하기 위해 Focal Loss를 적용하였으며, 모델의 수렴 안정성이 향상됨.
ROC 커브 및 Confusion Matrix 분석 결과, ‘vNo-DILI-Concern’ 및 ‘vMost-DILI-Concern’ 클래스에서는 높은 정확도를 보였으나, ‘Ambiguous DILI-Concern’ 클래스에서는 상대적으로 낮은 재현율을 나타냄.
따라서, 2-class(No-DILI, DILI-Risk) 분류로 모델에 사용될 class 분류를 변경했으며, 해당 모델과 4-class 분류 모델을 비교함.

그 결과, 2-class 분류 모델이 기존 4-class 분류 모델 보다 성능이 높은 것을 확인, 2-class 분류 모델을 최종 3D-GCN 모델로 선정함.
