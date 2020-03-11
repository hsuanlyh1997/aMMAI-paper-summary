# Rethinking ImageNet Pre-training

ICCV2019
Authors: Kaiming He, Ross Girshick, Piotr Dollár

## Summary

在target task的資料量夠多（>10k coco images）且training iterations足夠的情況下，train from scratch的結果不會比imagenet pre-training+fine-tuning差，也沒辦法靠fine-tuning解決overfitting，不過pre-training可以加速收斂速度。另外，ImageNet pre-train(classification based)對localization-sensitive target tasks比較沒幫助。

