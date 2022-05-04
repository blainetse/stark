# 不用修改 `VOT TOOLKIT` 源码也能阻止 `evaluate` 每次自动下载

> 那就是在当前 `workspace` 下创建一个软链接指向 `/data/VOTxxx`。

```shell
ln -s /data/VOT2020_LT sequences  # 注意：不要添加反斜杠！！！否则可能误删源文件
```
这里需要注意一点的就是，`config.yaml` 中对应的 `stack = vot2022/lt`，其余年份的为：`stack = votlt2021`

> 其实只有三个长时跟踪数据集：`votlt2018, votlt2019, votlt2020 --> vot2022/lt`，其余年份均引用最新的！


## TRAIN

数据集需要：`GOT-10k, coco, TrackingNet(重新指定 set_ids: 0-3), LaSOT`