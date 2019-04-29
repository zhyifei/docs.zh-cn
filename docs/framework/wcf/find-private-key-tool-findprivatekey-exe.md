---
title: “查找私钥”工具 (FindPrivateKey.exe)
ms.date: 09/11/2017
ms.assetid: b8846a95-3fcc-4e8c-b9c0-128d975a6307
ms.openlocfilehash: 8f156cbb2f4fad8d51e356bd4dee2d72d9397ffb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61929579"
---
# <a name="find-private-key-tool-findprivatekeyexe"></a>“查找私钥”工具 (FindPrivateKey.exe)

可以使用此命令行工具从证书存储区中检索私钥。 例如， *FindPrivateKey.exe*可用于查找的位置和关联的证书存储中的特定 X.509 证书的私钥文件的名称。

> [!IMPORTANT]
> FindPrivateKey 工具附带作为一个 WCF 示例。 有关在何处可以找到示例以及如何生成它的详细信息，请参阅[FindPrivateKey](./samples/findprivatekey.md)。

## <a name="syntax"></a>语法

```
FindPrivateKey<storeName> <storeLocation> [{ {-n <subjectName>} | {-t <thumbprint>} } [-f | -d | -a]]
```

## <a name="remarks"></a>备注

下表介绍了可用于“查找私钥”工具 (FindPrivateKey.exe) 的自变量和选项。

|参数|描述|
|--------------|-----------------|
|`storeName`|证书存储区的名称。|
|`storeLocation`|证书存储区的位置。|

|选项|描述|
|------------|-----------------|
|`/n <` *subjectName* `>`|指定证书的主题名称。|
|`/t <` *指纹* `>`|指定证书的指纹。 使用 Certmgr.exe 来检索证书的指纹。|
|`/f`|只输出文件名。|
|`/d`|只输出目录。|
|`/a`|输出绝对文件名。|

## <a name="examples"></a>示例

以下命令检索 John doe 的私钥：

```
FindPrivateKey My CurrentUser -n "CN=John Doe"
```

以下命令将检索本地计算机的私钥：

```
FindPrivateKey My LocalMachine -t "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52" –a
```