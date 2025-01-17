---
title: 部署独立的 Databend（对象存储）
sidebar_label: 部署独立的 Databend（对象存储）
description: 部署独立的 Databend
---

import FunctionDescription from '@site/src/components/FunctionDescription';

<FunctionDescription description="引入或更新：v1.2.168"/>

import EEFeature from '@site/src/components/EEFeature';

<EEFeature featureName='存储加密'/>

import GetLatest from '@site/src/components/GetLatest';
import DetailsWrap from '@site/src/components/DetailsWrap';

## 部署独立的 Databend

Databend 既支持自托管也支持云对象存储解决方案。本主题将解释如何利用对象存储部署 Databend 。有关支持的全部存储解决方案列表，请参见[了解部署模式](./00-understanding-deployment-modes.md)。

:::note
不推荐在生产环境或性能测试中在 MinIO 之上部署 Databend。
:::

### 设置您的对象存储

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';
import CommonDownloadDesc from '@site/docs/public/templates/deploying-databend-common.md';

<Tabs groupId="operating-systems">

<TabItem value="Amazon S3" label="Amazon S3">

在部署 Databend 之前，请确保您已在云中成功设置了对象存储环境，并完成了以下任务：

- 创建一个名为`databend`的存储桶或容器。
- 获取用于连接到您创建的存储桶或容器的端点 URL。
- 获取您账户的 Access Key ID 和 Secret Access Key。

有关如何为您的云对象存储管理存储桶和 Access Keys 的信息，请参考解决方案提供商的用户手册。以下是您可能需要的一些有用链接：

- <https://docs.aws.amazon.com/AmazonS3/latest/userguide/create-bucket-overview.html>
- <https://docs.aws.amazon.com/general/latest/gr/aws-sec-cred-types.html>

<CommonDownloadDesc />

</TabItem>

<TabItem value="Google GCS" label="Google GCS">

在部署 Databend 之前，请确保您已在云中成功设置了对象存储环境，并完成了以下任务：

- 创建一个名为`databend`的存储桶。
- 获取您账户的 Google Cloud Storage OAuth2 凭证。

有关如何在 Google Cloud Storage 中管理存储桶和 OAuth2 凭证的信息，请参考解决方案提供商的用户手册。以下是您可能需要的一些有用链接：

- <https://cloud.google.com/storage/docs/creating-buckets>
- <https://cloud.google.com/storage/docs/authentication#apiauth>

<CommonDownloadDesc />

</TabItem>

<TabItem value="Azure Blob" label="Azure Blob">

在部署 Databend 之前，请确保您已在云中成功设置了对象存储环境，并完成了以下任务：

- 创建一个名为`databend`的存储桶或容器。
- 获取用于连接到您创建的存储桶或容器的端点 URL。
- 获取您账户的 Access Key ID 和 Secret Access Key。

有关如何为您的云对象存储管理存储桶和 Access Keys 的信息，请参考解决方案提供商的用户手册。以下是您可能需要的一些有用链接：

- <https://docs.microsoft.com/en-us/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container>
- <https://docs.microsoft.com/en-us/azure/storage/common/storage-account-keys-manage?tabs=azure-portal#view-account-access-keys>

<CommonDownloadDesc />

</TabItem>

<TabItem value="Tencent COS" label="Tencent COS">

在部署 Databend 之前，请确保您已在云中成功设置了对象存储环境，并完成了以下任务：

- 创建一个名为`databend`的存储桶或容器。
- 获取用于连接到您创建的存储桶或容器的端点 URL。
- 获取您账户的 Access Key ID 和 Secret Access Key。

有关如何为您的云对象存储管理存储桶和 Access Keys 的信息，请参考解决方案提供商的用户手册。以下是您可能需要的一些有用链接：

- <https://cloud.tencent.com/document/product/436/13309>
- <https://cloud.tencent.com/document/product/436/68282>

<CommonDownloadDesc />

</TabItem>

<TabItem value="Alibaba OSS" label="Alibaba OSS">

在部署 Databend 之前，请确保您已在云中成功设置了对象存储环境，并完成了以下任务：

- 创建一个名为`databend`的存储桶或容器。
- 获取用于连接到您创建的存储桶或容器的端点 URL。
- 获取您账户的 Access Key ID 和 Secret Access Key。

有关如何为您的云对象存储管理存储桶和 Access Keys 的信息，请参考解决方案提供商的用户手册。以下是您可能需要的一些有用链接：

- <https://www.alibabacloud.com/help/zh/object-storage-service/latest/create-buckets-2>
- <https://help.aliyun.com/document_detail/53045.htm>

<CommonDownloadDesc />

</TabItem>

<TabItem value="QingCloud QingStor" label="QingCloud QingStor">

在部署 Databend 之前，请确保您已在云中成功设置了对象存储环境，并完成了以下任务：

- 创建一个名为`databend`的存储桶或容器。
- 获取用于连接到您创建的存储桶或容器的端点 URL。
- 获取您账户的 Access Key ID 和 Secret Access Key。

有关如何为您的云对象存储管理存储桶和 Access Keys 的信息，请参考解决方案提供商的用户手册。以下是您可能需要的一些有用链接：

- <https://docsv3.qingcloud.com/storage/object-storage/manual/console/bucket_manage/basic_opt/>
- <https://docsv3.qingcloud.com/development_docs/api/overview/>

<CommonDownloadDesc />

</TabItem>

<TabItem value="Wasabi" label="Wasabi">

在部署 Databend 之前，请确保您已在云中成功设置了对象存储环境，并完成了以下任务：

- 创建一个名为`databend`的存储桶或容器。
- 获取用于连接到您创建的存储桶或容器的端点 URL。
- 获取您账户的 Access Key ID 和 Secret Access Key。

有关如何为您的云对象存储管理存储桶和 Access Keys 的信息，请参考解决方案提供商的用户手册。以下是您可能需要的一些有用链接：

- <https://docs.wasabi.com/docs/creating-a-bucket>
- <https://docs.wasabi.com/docs/access-keys-1>

<CommonDownloadDesc />

</TabItem>

<TabItem value="MinIO" label="MinIO">

a. 按照[MinIO 快速入门指南](https://docs.min.io/docs/minio-quickstart-guide.html)下载并安装 MinIO 包到您的本地机器。

b. 打开一个终端窗口并导航到存储 MinIO 的文件夹。

c. 运行命令`vim server.sh`创建一个包含以下内容的文件：

```shell
~/minio$ cat server.sh
export MINIO_ROOT_USER=minioadmin
export MINIO_ROOT_PASSWORD=minioadmin
./minio server --address :9900 ./data
```

d. 运行以下命令启动 MinIO 服务器：

```shell
chmod +x server.sh
./server.sh
```

e. 在您的浏览器中，访问 <http://127.0.0.1:9900> 并输入凭据（`minioadmin` / `minioadmin`）登录 MinIO 控制台。

f. 在 MinIO 控制台中，创建一个名为`databend`的存储桶。

<CommonDownloadDesc />

</TabItem>
</Tabs>

### 部署元节点

a. 打开文件夹`/usr/local/databend/configs`中的文件`databend-meta.toml`，将文件中的`127.0.0.1`全部替换为`0.0.0.0`。

b. 打开一个终端窗口并导航到文件夹`/usr/local/databend/bin`。

c. 运行以下命令以启动元节点：

```shell
./databend-meta -c ../configs/databend-meta.toml > meta.log 2>&1 &
```

d. 运行以下命令以检查元节点是否成功启动：

```shell
curl -I  http://127.0.0.1:28101/v1/health
```

### 部署查询节点

a. 打开文件夹`/usr/local/databend/configs`中的文件`databend-query.toml`，将文件中的`127.0.0.1`全部替换为`0.0.0.0`。

b. 在文件`databend-query.toml`中，设置 `[storage]` 块中的参数 *type* ，并配置访问凭证和端点 URL 以连接到您的对象存储。

要配置您的存储设置，请通过在每行前添加 `'#'` 来注释掉 `[storage.fs]` 部分，然后通过移除 `'#'` 符号来取消注释适合您的对象存储提供商的相应部分，并填写必要的值。您也可以将下面的相应模板复制并粘贴到文件中，并相应地配置它。

<Tabs groupId="operating-systems">

<TabItem value="Amazon S3" label="Amazon S3">

```toml
[storage]
# s3
type = "s3"

[storage.s3]
# https://docs.aws.amazon.com/AmazonS3/latest/userguide/create-bucket-overview.html
bucket = "databend"
endpoint_url = "https://s3.amazonaws.com"

# 如何获取access_key_id和secret_access_key:
# https://docs.aws.amazon.com/general/latest/gr/aws-sec-cred-types.html
// highlight-next-line
access_key_id = "<your-key-id>"
// highlight-next-line
secret_access_key = "<your-access-key>"
```

</TabItem>

<TabItem value="Google GCS" label="Google GCS">

```toml
[storage]
# gcs
type = "gcs"

[storage.gcs]
# 如何创建一个存储桶:
# https://cloud.google.com/storage/docs/creating-buckets
// highlight-next-line
bucket = "databend"

# GCS也支持更改端点URL
# 但端点应与GCS的JSON API兼容
# 默认:
# endpoint_url = "https://storage.googleapis.com"

# GCS的工作目录
# 默认:
# root = "/"

// highlight-next-line
credential = "<your-credential>"
```

</TabItem>

<TabItem value="Azure Blob" label="Azure Blob">

```toml
[storage]
# azblob
type = "azblob"

[storage.azblob]
endpoint_url = "https://<your-storage-account-name>.blob.core.windows.net"

# https://docs.microsoft.com/en-us/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container
container = "<your-azure-storage-container-name>"
account_name = "<your-storage-account-name>"

# https://docs.microsoft.com/en-us/azure/storage/common/storage-account-keys-manage?tabs=azure-portal#view-account-access-keys
account_key = "<your-account-key>"
```

</TabItem>

<TabItem value="Tencent COS" label="Tencent COS">

```toml
[storage]
# s3
type = "cos"

[storage.cos]
# 您可以从存储桶详情页面获取URL。
# 以下是一个区域为北京(ap-beijing)的示例:
// highlight-next-line
endpoint_url = "https://cos.ap-beijing.myqcloud.com"

# 如何创建一个存储桶:
# https://cloud.tencent.com/document/product/436/13309
// highlight-next-line
bucket = "databend"

# 如何获取secret_id和secret_key:
# https://cloud.tencent.com/document/product/436/68282
// highlight-next-line
secret_id = "<your-secret-id>"
// highlight-next-line
secret_key = "<your-secret-key>"
root = "<your-root-path>"
```

Tencent COS 还支持从环境变量加载配置值。这意味着，您可以不在配置文件中直接指定配置值，而是通过设置相应的环境变量（TENCENTCLOUD_SECRETID、TENCENTCLOUD_SECRETKEY 和 USER_CODE_ROOT）来配置 COS 存储。

```toml
[storage]
# s3
type = "cos"

[storage.cos]
# 您可以从存储桶详情页面获取URL。
# 以下是一个区域为北京(ap-beijing)的示例:
// highlight-next-line
endpoint_url = "https://cos.ap-beijing.myqcloud.com"

# 如何创建一个存储桶:
# https://cloud.tencent.com/document/product/436/13309
// highlight-next-line
bucket = "databend"
```

</TabItem>

<TabItem value="Alibaba OSS" label="Alibaba OSS">

```toml
[storage]
type = "oss"

[storage.oss]
// highlight-next-line
bucket = "databend"

# 你可以从存储桶详情页面获取URL。
// highlight-next-line
# https://help.aliyun.com/document_detail/31837.htm
// highlight-next-line
# https://<bucket-name>.<region-id>[-internal].aliyuncs.com
// highlight-next-line
# 此示例使用的OSS区域ID为：oss-cn-beijing-internal。
endpoint_url = "https://oss-cn-beijing-internal.aliyuncs.com"
# enable_virtual_host_style = true

# 如何获取access_key_id和secret_access_key：
# https://help.aliyun.com/document_detail/53045.htm
// highlight-next-line
access_key_id = "<your-key-id>"
// highlight-next-line
secret_access_key = "<your-access-key>"
```

Databend 企业版支持在 OSS 中使用服务器端加密。此功能允许您通过激活 OSS 中存储数据的服务器端加密来增强数据安全性和隐私性。您可以选择最适合您需求的加密方法。请注意，您必须拥有有效的 Databend 企业版许可证才能使用此功能。要获取许可证，请参见[Databend 许可证](../00-overview/00-editions/01-dee/20-license.md)。

要在 Databend 中启用服务器端加密，请在[storage.oss]部分添加以下参数：

| 参数                          | 描述                                                                                                                                     | 可用值                             |
| ----------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------- |
| server_side_encryption        | 指定 OSS 数据的服务器端加密方法。"AES256"使用 OSS 管理的 AES256 密钥进行加密，而"KMS"则使用 server_side_encryption_key_id 中定义的密钥。 | "AES256" 或 "KMS"                  |
| server_side_encryption_key_id | 当 server_side_encryption 设置为"KMS"时，此参数用于指定 OSS 的服务器端加密密钥 ID。仅在使用 KMS 加密模式时适用。                         | 字符串，KMS 加密密钥的唯一标识符。 |

</TabItem>

<TabItem value="QingCloud QingStor" label="QingCloud QingStor">

```toml
[storage]
# s3
type = "s3"

[storage.s3]
bucket = "databend"

# 你可以从存储桶详情页面获取URL。
# https://docsv3.qingcloud.com/storage/object-storage/intro/object-storage/#zone
endpoint_url = "https://s3.pek3b.qingstor.com"

# 如何获取access_key_id和secret_access_key：
# https://docsv3.qingcloud.com/development_docs/api/overview/
access_key_id = "<your-key-id>"
secret_access_key = "<your-access-key>"
```

:::tip
在此示例中，QingStor 区域为`pek3b`。
:::

</TabItem>

<TabItem value="Wasabi" label="Wasabi">

```toml
[storage]
# s3
type = "s3"

[storage.s3]
# 如何创建存储桶：
// highlight-next-line
bucket = "<your-bucket>"

# 你可以从以下链接获取URL：
# https://wasabi-support.zendesk.com/hc/en-us/articles/360015106031-What-are-the-service-URLs-for-Wasabi-s-different-regions-
// highlight-next-line
endpoint_url = "https://s3.us-east-2.wasabisys.com"

# 如何获取access_key_id和secret_access_key：
// highlight-next-line
access_key_id = "<your-key-id>"
// highlight-next-line
secret_access_key = "<your-access-key>"
```

:::tip
在此示例中，Wasabi 区域为`us-east-2`。
:::

</TabItem>

<TabItem value="MinIO" label="MinIO">

```toml
[storage]
# s3
type = "s3"

[storage.s3]
bucket = "databend"
endpoint_url = "http://127.0.0.1:9900"
access_key_id = "minioadmin"
secret_access_key = "minioadmin"
```

</TabItem>

</Tabs>

c. 通过[query.users]部分配置管理员用户。有关更多信息，请参见[配置管理员用户](04-admin-users.md)。要使用默认的 root 用户和"no_password"认证类型继续，请确保在文件`databend-query.toml`中删除以下行前的'#'字符：

:::caution
在本教程中使用"no_password"认证类型为 root 用户仅为示例，不推荐用于生产环境，因为可能存在潜在的安全风险。
:::

```toml title='databend-query.toml'
...
[[query.users]]
name = "root"
auth_type = "no_password"
...
```

d. 打开终端窗口并导航到文件夹`/usr/local/databend/bin`。

e. 运行以下命令以启动查询节点：

```shell
./databend-query -c ../configs/databend-query.toml > query.log 2>&1 &
```

f. 运行以下命令以检查查询节点是否成功启动：

```shell
curl -I  http://127.0.0.1:8080/v1/health
```

### 验证部署

在本节中，我们将对 Databend 运行一些查询以验证部署。

a. 在您的本地机器上下载并安装 MySQL 客户端。

b. 从您的 SQL 客户端创建到 127.0.0.1 的连接。在连接中，将端口设置为 `3307`，并将用户名设置为 `root`。

c. 运行以下命令并检查查询是否成功：

```sql
CREATE TABLE t1(a int);

INSERT INTO t1 VALUES(1), (2);

SELECT * FROM t1;
```

### 启动和停止 Databend

每次启动和停止 Databend 时，只需运行 `/usr/local/databend/scripts` 文件夹中的脚本：

```shell
# 启动 Databend
./scripts/start.sh

# 停止 Databend
./scripts/stop.sh
```

<DetailsWrap>
<details>
  <summary>权限被拒绝？</summary>
  <div>
    如果在尝试启动 Databend 时遇到以下错误消息：

```shell
==> query.log <==
: No getcpu support: percpu_arena:percpu
: option background_thread currently supports pthread only
Databend Query 启动失败，原因：Code: 1104, Text = failed to create appender: Os { code: 13, kind: PermissionDenied, message: "Permission denied" }.
```

运行以下命令，然后再次尝试启动 Databend：

```shell
sudo mkdir /var/log/databend
sudo mkdir /var/lib/databend
sudo chown -R $USER /var/log/databend
sudo chown -R $USER /var/lib/databend
```

  </div>
</details>
</DetailsWrap>
<GetLatest/>

## 下一步

部署 Databend 后，您可能需要了解以下主题：

- [加载和卸载数据](/guides/load-data)：在 Databend 中管理数据导入/导出。
- [可视化](/guides/visualize)：将 Databend 与可视化工具集成以获得洞察。
