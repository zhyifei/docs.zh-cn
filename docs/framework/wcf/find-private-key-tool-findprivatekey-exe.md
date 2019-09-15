---
title: “查找私钥”工具 (FindPrivateKey.exe)
ms.date: 09/11/2017
ms.assetid: b8846a95-3fcc-4e8c-b9c0-128d975a6307
ms.openlocfilehash: 316f55b93cf4d867b99878bf483b73cb3f09ad04
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/14/2019
ms.locfileid: "70990352"
---
# <a name="find-private-key-tool-findprivatekeyexe"></a><span data-ttu-id="079ba-102">“查找私钥”工具 (FindPrivateKey.exe)</span><span class="sxs-lookup"><span data-stu-id="079ba-102">Find Private Key Tool (FindPrivateKey.exe)</span></span>

<span data-ttu-id="079ba-103">可以使用此命令行工具从证书存储区中检索私钥。</span><span class="sxs-lookup"><span data-stu-id="079ba-103">This command-line tool can be used to retrieve a private key from a certificate store.</span></span> <span data-ttu-id="079ba-104">例如， *FindPrivateKey*可用于查找与证书存储区中的特定 x.509 证书关联的私钥文件的位置和名称。</span><span class="sxs-lookup"><span data-stu-id="079ba-104">For example, *FindPrivateKey.exe* can be used to find the location and name of the private key file associated with a specific X.509 certificate in the certificate store.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="079ba-105">FindPrivateKey 工具附带作为一个 WCF 示例。</span><span class="sxs-lookup"><span data-stu-id="079ba-105">The FindPrivateKey tool is shipped as a WCF sample.</span></span> <span data-ttu-id="079ba-106">有关在何处查找示例以及如何生成示例的详细信息，请参阅[FindPrivateKey](./samples/findprivatekey.md)。</span><span class="sxs-lookup"><span data-stu-id="079ba-106">For more information about where to find the sample and how to build it, see [FindPrivateKey](./samples/findprivatekey.md).</span></span>

## <a name="syntax"></a><span data-ttu-id="079ba-107">语法</span><span class="sxs-lookup"><span data-stu-id="079ba-107">Syntax</span></span>

```console
FindPrivateKey<storeName> <storeLocation> [{ {-n <subjectName>} | {-t <thumbprint>} } [-f | -d | -a]]
```

## <a name="remarks"></a><span data-ttu-id="079ba-108">备注</span><span class="sxs-lookup"><span data-stu-id="079ba-108">Remarks</span></span>

<span data-ttu-id="079ba-109">下表介绍了可用于“查找私钥”工具 (FindPrivateKey.exe) 的自变量和选项。</span><span class="sxs-lookup"><span data-stu-id="079ba-109">The following tables describe the arguments and the options that can be used with the Find Private Key tool (FindPrivateKey.exe).</span></span>

|<span data-ttu-id="079ba-110">参数</span><span class="sxs-lookup"><span data-stu-id="079ba-110">Argument</span></span>|<span data-ttu-id="079ba-111">描述</span><span class="sxs-lookup"><span data-stu-id="079ba-111">Description</span></span>|
|--------------|-----------------|
|`storeName`|<span data-ttu-id="079ba-112">证书存储区的名称。</span><span class="sxs-lookup"><span data-stu-id="079ba-112">Name of the certificate store.</span></span>|
|`storeLocation`|<span data-ttu-id="079ba-113">证书存储区的位置。</span><span class="sxs-lookup"><span data-stu-id="079ba-113">The location of the certificate store.</span></span>|

|<span data-ttu-id="079ba-114">选项</span><span class="sxs-lookup"><span data-stu-id="079ba-114">Option</span></span>|<span data-ttu-id="079ba-115">描述</span><span class="sxs-lookup"><span data-stu-id="079ba-115">Description</span></span>|
|------------|-----------------|
|<span data-ttu-id="079ba-116">`/n <`*subjectName*`>`</span><span class="sxs-lookup"><span data-stu-id="079ba-116">`/n <` *subjectName* `>`</span></span>|<span data-ttu-id="079ba-117">指定证书的主题名称。</span><span class="sxs-lookup"><span data-stu-id="079ba-117">Specifies the subject name of the certificate.</span></span>|
|<span data-ttu-id="079ba-118">`/t <`*指纹*`>`</span><span class="sxs-lookup"><span data-stu-id="079ba-118">`/t <` *thumbprint* `>`</span></span>|<span data-ttu-id="079ba-119">指定证书的指纹。</span><span class="sxs-lookup"><span data-stu-id="079ba-119">Specifies the thumbprint of the certificate.</span></span> <span data-ttu-id="079ba-120">使用 Certmgr.exe 来检索证书的指纹。</span><span class="sxs-lookup"><span data-stu-id="079ba-120">Use Certmgr.exe to retrieve the thumbprint of the certificate.</span></span>|
|`/f`|<span data-ttu-id="079ba-121">只输出文件名。</span><span class="sxs-lookup"><span data-stu-id="079ba-121">Outputs the file name only.</span></span>|
|`/d`|<span data-ttu-id="079ba-122">只输出目录。</span><span class="sxs-lookup"><span data-stu-id="079ba-122">Outputs the directory only.</span></span>|
|`/a`|<span data-ttu-id="079ba-123">输出绝对文件名。</span><span class="sxs-lookup"><span data-stu-id="079ba-123">Outputs the absolute file name.</span></span>|

## <a name="examples"></a><span data-ttu-id="079ba-124">示例</span><span class="sxs-lookup"><span data-stu-id="079ba-124">Examples</span></span>

<span data-ttu-id="079ba-125">以下命令检索 John Doe 的私钥：</span><span class="sxs-lookup"><span data-stu-id="079ba-125">The following command retrieves the private key for John Doe:</span></span>

```console
FindPrivateKey My CurrentUser -n "CN=John Doe"
```

<span data-ttu-id="079ba-126">以下命令检索本地计算机的私钥：</span><span class="sxs-lookup"><span data-stu-id="079ba-126">The following command retrieves the private key for the local machine:</span></span>

```console
FindPrivateKey My LocalMachine -t "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52" –a
```
