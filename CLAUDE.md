# 模型强化后训练知识库

## 目标
读取verl文档和官方代码仓，写文档整理所有训练参数的用法，如涉及并行的参数，怎么和模型规模和数据结合，在不oom的情况下，尽可能提升训练速度
## 产物
github pages网页，入口为index.html
文档
## 准备
权限设置，文件读取和修改仅限于本文件所在路径
远程仓库https://github.com/oashua/verl_knowledge.git

## 网络与代理
本机直连 github.com 不通（TLS 中断），git 推拉需走代理 `http://202.120.40.209:7898`（已在 git 全局配置）。

代理由远程服务器 202.120.40.209（SSH 端口 22222，用户 hushaohua，密码不写入本文件）上的 v2raya 提供，偶发掉线。连接拒绝时登上去重启即可恢复：

```bash
sshpass -p '<密码>' ssh -o StrictHostKeyChecking=accept-new -p 22222 hushaohua@202.120.40.209 \
  "pgrep v2raya || (nohup v2raya -a 0.0.0.0:7899 -c /homeB/hushaohua/v2ray_config/v2raya --log-file ~/v2raya.log --lite >/dev/null 2>&1 & sleep 3; pgrep -a v2raya)"
```

注意：`-a 0.0.0.0:7899` 是 v2raya 面板端口，真正的代理端口是 **7898**。
克隆仓库备选：镜像站 `https://ghfast.top/<github-url>` 直连可用；readthedocs.org、gitee.com 可直连。

## 本地源码参考
`verl_src/` 为 verl 官方仓库浅克隆（已 gitignore，仅本地参考，不提交），文档撰写以其为一手依据。


## 参考链接
verl文档
https://verl.readthedocs.io/en/latest/
verl github
