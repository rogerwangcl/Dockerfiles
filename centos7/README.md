



##### Centos7

```
docker pull xjxiaolei/centos7:latest
```

- 基础镜像

  - Centos7

- 调整地方：

  - yum repo 替换为 ali 的源：

    | repo id          | repo name                                                    |
    | ---------------- | ------------------------------------------------------------ |
    | base/7/x86_64    | CentOS-7 - Base - mirrors.aliyun.com                         |
    | extras/7/x86_64  | CentOS-7 - Extras - mirrors.aliyun.com                       |
    | updates/7/x86_64 | CentOS-7 - Updates - mirrors.aliyun.com                      |
    | epel/x86_64      | Extra Packages for Enterprise Linux 7 - x86_64- mirrors.aliyun.com |

  - 时区：

    ```
    Asia/Shanghai
    ```

  - 编码：

    |          |             |
    | -------- | ----------- |
    | LANG     | en_US.UTF-8 |
    | LANGUAGE | en_US.UTF-8 |
    | LC_ALL   | en_US.UTF-8 |

    

    