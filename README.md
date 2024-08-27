---
base_model: FacebookAI/roberta-base
library_name: peft
license: mit
metrics:
- accuracy
tags:
- generated_from_trainer
model-index:
- name: spam_not_spam
  results: []
---

<!-- This model card has been generated automatically according to the information the Trainer had access to. You
should probably proofread and complete it, then remove this comment. -->

# RoBERTa-PEFT-ForSequenceClassification

This model is a fine-tuned version of [FacebookAI/roberta-base](https://huggingface.co/FacebookAI/roberta-base) on `spam_not_spam` dataset.
It achieves the following results on the evaluation set: \
*- Loss: 0.0414* \
*- Accuracy: 0.9839*

## Model description

### Performing Parameter-Efficient Fine-Tuning 
We used low rank adaptation (LoRA) from PEFT library in HuggineFace. \
Base-model is finetuned using LoRA config below: \
`peft_config = LoraConfig(task_type=TaskType.SEQ_CLS, inference_mode=False, r=8, lora_alpha=32, lora_dropout=0.1)`

### Training
Use script below for model fine-tuning:

```
def compute_metrics(eval_pred):
    predictions, labels = eval_pred
    predictions = np.argmax(predictions, axis=1)
    return {"accuracy": (predictions == labels).mean()}

trainer = Trainer(
    model=lora_model,
    args=TrainingArguments(
        output_dir="./data/spam_not_spam",
        # Set the learning rate
        learning_rate = 2e-5,
        # Set the per device train batch size and eval batch size
        per_device_train_batch_size=16,
        per_device_eval_batch_size=64,
        # Evaluate and save the model after each epoch
        evaluation_strategy = "epoch",
        save_strategy = "epoch",
        num_train_epochs=5,
        weight_decay=0.01,
        load_best_model_at_end=True,
    ),
    train_dataset= tokenized_dataset_train,
    eval_dataset= tokenized_dataset_test,
    tokenizer=tokenizer,
    data_collator=DataCollatorWithPadding(tokenizer=tokenizer),
    compute_metrics=compute_metrics,
)
```




## Intended uses & limitations

More information needed

## Training and evaluation data

More information needed

## Training procedure

### Training hyperparameters

The following hyperparameters were used during training:
- learning_rate: 2e-05
- train_batch_size: 16
- eval_batch_size: 64
- seed: 42
- optimizer: Adam with betas=(0.9,0.999) and epsilon=1e-08
- lr_scheduler_type: linear
- num_epochs: 5

### Training results

| Training Loss | Epoch | Step | Validation Loss | Accuracy |
|:-------------:|:-----:|:----:|:---------------:|:--------:|
| No log        | 1.0   | 279  | 0.0414          | 0.9839   |
| 0.1982        | 2.0   | 558  | 0.0433          | 0.9865   |
| 0.1982        | 3.0   | 837  | 0.0465          | 0.9892   |
| 0.0415        | 4.0   | 1116 | 0.0426          | 0.9874   |
| 0.0415        | 5.0   | 1395 | 0.0415          | 0.9883   |


### Framework versions

- PEFT 0.12.0
- Transformers 4.42.4
- Pytorch 2.4.0+cu121
- Datasets 2.15.0
- Tokenizers 0.19.1