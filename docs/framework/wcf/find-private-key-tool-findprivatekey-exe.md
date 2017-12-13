---
title: "“查找私钥”工具 (FindPrivateKey.exe)"
ms.date: 09/11/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
ms.assetid: b8846a95-3fcc-4e8c-b9c0-128d975a6307
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2d515077106b8f0527d045d5ef7fb6d7c0c7aa62
ms.sourcegitcommit: 9bee08539b1886c9d57fa3d5bd8a58dfdd7cad94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/12/2017
---
# <a name="find-private-key-tool-findprivatekeyexe"></a><span data-ttu-id="c1cae-102">“查找私钥”工具 (FindPrivateKey.exe)</span><span class="sxs-lookup"><span data-stu-id="c1cae-102">Find Private Key Tool (FindPrivateKey.exe)</span></span>

<span data-ttu-id="c1cae-103">可以使用此命令行工具从证书存储区中检索私钥。</span><span class="sxs-lookup"><span data-stu-id="c1cae-103">This command-line tool can be used to retrieve a private key from a certificate store.</span></span> <span data-ttu-id="c1cae-104">例如， *FindPrivateKey.exe*可用于查找的位置和关联的证书存储中的特定 X.509 证书的私钥文件的名称。</span><span class="sxs-lookup"><span data-stu-id="c1cae-104">For example, *FindPrivateKey.exe* can be used to find the location and name of the private key file associated with a specific X.509 certificate in the certificate store.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c1cae-105">FindPrivateKey 工具附带作为一个 WCF 示例。</span><span class="sxs-lookup"><span data-stu-id="c1cae-105">The FindPrivateKey tool is shipped as a WCF sample.</span></span> <span data-ttu-id="c1cae-106">有关在何处可以找到示例以及如何生成它的详细信息，请参阅[FindPrivateKey](./samples/findprivatekey.md)。</span><span class="sxs-lookup"><span data-stu-id="c1cae-106">For more information about where to find the sample and how to build it, see [FindPrivateKey](./samples/findprivatekey.md).</span></span>

## <a name="syntax"></a><span data-ttu-id="c1cae-107">语法</span><span class="sxs-lookup"><span data-stu-id="c1cae-107">Syntax</span></span>

```
FindPrivateKey<storeName> <storeLocation> [{ {-n <subjectName>} | {-t <thumbprint>} } [-f | -d | -a]]
```

## <a name="remarks"></a><span data-ttu-id="c1cae-108">备注</span><span class="sxs-lookup"><span data-stu-id="c1cae-108">Remarks</span></span>

<span data-ttu-id="c1cae-109">下表介绍了可用于“查找私钥”工具 (FindPrivateKey.exe) 的自变量和选项。</span><span class="sxs-lookup"><span data-stu-id="c1cae-109">The following tables describe the arguments and the options that can be used with the Find Private Key tool (FindPrivateKey.exe).</span></span>

|<span data-ttu-id="c1cae-110">参数</span><span class="sxs-lookup"><span data-stu-id="c1cae-110">Argument</span></span>|<span data-ttu-id="c1cae-111">描述</span><span class="sxs-lookup"><span data-stu-id="c1cae-111">Description</span></span>|
|--------------|-----------------|
|`storeName`|<span data-ttu-id="c1cae-112">证书存储区的名称。</span><span class="sxs-lookup"><span data-stu-id="c1cae-112">Name of the certificate store.</span></span>|
|`storeLocation`|<span data-ttu-id="c1cae-113">证书存储区的位置。</span><span class="sxs-lookup"><span data-stu-id="c1cae-113">The location of the certificate store.</span></span>|

|<span data-ttu-id="c1cae-114">选项</span><span class="sxs-lookup"><span data-stu-id="c1cae-114">Option</span></span>|<span data-ttu-id="c1cae-115">描述</span><span class="sxs-lookup"><span data-stu-id="c1cae-115">Description</span></span>|
|------------|-----------------|
|<span data-ttu-id="c1cae-116">`/n <`*subjectName*`>`</span><span class="sxs-lookup"><span data-stu-id="c1cae-116">`/n <` *subjectName* `>`</span></span>|<span data-ttu-id="c1cae-117">指定证书的主题名称。</span><span class="sxs-lookup"><span data-stu-id="c1cae-117">Specifies the subject name of the certificate.</span></span>|
|<span data-ttu-id="c1cae-118">`/t <`*指纹*`>`</span><span class="sxs-lookup"><span data-stu-id="c1cae-118">`/t <` *thumbprint* `>`</span></span>|<span data-ttu-id="c1cae-119">指定证书的指纹。</span><span class="sxs-lookup"><span data-stu-id="c1cae-119">Specifies the thumbprint of the certificate.</span></span> <span data-ttu-id="c1cae-120">使用 Certmgr.exe 来检索证书的指纹。</span><span class="sxs-lookup"><span data-stu-id="c1cae-120">Use Certmgr.exe to retrieve the thumbprint of the certificate.</span></span>|
|`/f`|<span data-ttu-id="c1cae-121">只输出文件名。</span><span class="sxs-lookup"><span data-stu-id="c1cae-121">Outputs the file name only.</span></span>|
|`/d`|<span data-ttu-id="c1cae-122">只输出目录。</span><span class="sxs-lookup"><span data-stu-id="c1cae-122">Outputs the directory only.</span></span>|
|`/a`|<span data-ttu-id="c1cae-123">输出绝对文件名。</span><span class="sxs-lookup"><span data-stu-id="c1cae-123">Outputs the absolute file name.</span></span>|

## <a name="examples"></a><span data-ttu-id="c1cae-124">示例</span><span class="sxs-lookup"><span data-stu-id="c1cae-124">Examples</span></span>

<span data-ttu-id="c1cae-125">以下命令检索 John doe 的私钥：</span><span class="sxs-lookup"><span data-stu-id="c1cae-125">The following command retrieves the private key for John Doe:</span></span>

```
FindPrivateKey My CurrentUser -n "CN=John Doe"
```

<span data-ttu-id="c1cae-126">以下命令将检索本地计算机的私钥：</span><span class="sxs-lookup"><span data-stu-id="c1cae-126">The following command retrieves the private key for the local machine:</span></span>

```
FindPrivateKey My LocalMachine -t "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52" –a
```