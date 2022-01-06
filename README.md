# Automatic-Qcloud

使用 GitHub Actions 自动对腾讯云轻量云进行快照自动备份流量监控功能

## 变量

| 名称        | 内容            | 说明                                                                      |
|-------------|-----------------|--------------------------------------------------------------------------|
| `SecretId`  | 腾讯云SecretId  | 前往腾讯云控制台 https://console.cloud.tencent.com/cam/capi 获取SecretId  |
| `SecretKey` | 腾讯云SecretKey | 前往腾讯云控制台 https://console.cloud.tencent.com/cam/capi 获取SecretKey |
| `region`    | 实例地域        | `ap-beijing` 北京, `ap-chengdu` 成都, `ap-guangzhou` 广州, `ap-hongkong` 香港, `ap-nanjing` 南京, `ap-shanghai` 上海, `ap-singapore` 新加坡, `ap-tokyo`东京, `eu-moscow`莫斯科, `na-siliconvalley`硅谷。多实例请使用`#`相连，多实例同地区也请写两遍 例如：`ap-guangzhou#ap-guangzhou`|
| `InstanceIds` | 轻量云实例ID     | 轻量云实例ID,多实例请用`#`分割 例如：`lhins-asdd3z#lhins-oaseu3z`         |

- 说明：
  - 快照备份时间默认为每月的1日和16日的北京时间凌晨4时进行执行快照备份 如需修改请前往 [Snapshot.yml](./.github/workflows/Snapshot.yml#L8) 进行修改
  - 腾讯云流量监控默认轮询时间为每小时30分钟一次 如需修改请前往 [TrafficPackages.yml](./.github/workflows/TrafficPackages.yml#L8) 进行修改
  - 腾讯云流量监控默认红线关机为总流量的95% 如需修改请前往 [TrafficPackages.yml](./Qcloud_TrafficPackages.py#L107) 进行修改
 
## 使用方法

[见部署方法](./docs/deploy.md)

## 感谢

本项目基于 [@fungjcode](https://github.com/fungjcode) 的 [python_tools](https://github.com/fungjcode/python_tools) 项目修改而成
