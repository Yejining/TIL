## Pytorch Lightning
[Pytorch Lightning documentation](https://pytorch-lightning.readthedocs.io/en/latest/), [설명 link](https://towardsdatascience.com/from-pytorch-to-pytorch-lightning-a-gentle-introduction-b371b7caaf09)
```
Pytorch lightning은 기존 pytorch와 기본적으로 같지만 research code에 대한 structure를 제공한다는 점에서 다르다.
그렇기 때문에 모델을 만든다든가, 사용할 대의 코드는 pytorch를 사용할 때와 대부분 동일하다.
```

### 코드 작업 시 Pytorch와 다른 점 (functions)
1. prepare_data()
  - 이 함수에서는 데이터를 다운로드하거나 처리한다.
  - 다중 GPU를 이용하는 경우 데이터를 중복해서 다운로드하거나, double manipulations 하는 것을 막아준다.
  - Pytorch Lightning에서는 이 함수를 이용해 오직 하나의 GPU에서만 critical part를 호출하게 한다.
2. train_dataloader()
  - (optional)
  - DataModule 아래에서 이 함수가 불러지며, DataModule은 사용자의 데이터를 재사용하고 공유하기 쉽게 만들어준다.
3. val_dataloader()
  - train_dataloader()과 같음
4. test_dataloader()
  - train_dataloader()과 같음

### 코드 작업 시 Pytorch와 다른 점 (optimizer)
- Pytorch에서는 모델 외부에서 optimizer를 생성하지만, Pytorch Lightning에서는 모델 내부에서 optimizer를 정의하고 생성한다.
- 한 개의 모델에서 여러개의 optimizer를 사용하고 싶다면, configure_optimizers()에서 리턴값으로 원하는 만큼의 optimizers를 리턴하면 된다.

### 코드 작업 시 Pytorch와 다른 점 (loss)
- Pytorch에서는 모델 외부에서 loss를 생성하지만, Pytorch Lightning에서는 모델 내부에서 loss를 정의하고 생성한다.

### LightningModule
- Lightning에서는 모델을 pass하지 않고 self.parameters()를 패스한다. 이것은 LightningModule 자체가 모델이기 때문이다.

### Pytorch와 강력하게 다른 점
- Validation and training loop
  ![validation and training loop](./images/Pytorch_Lightning_1.png)
- The Lightning Trainer
  ![The Lightning Trainer](./images/Pytorch_Lightning_2.jpeg)
