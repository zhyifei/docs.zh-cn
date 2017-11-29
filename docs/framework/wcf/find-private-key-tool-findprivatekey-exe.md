---
title: "“查找私钥”工具 (FindPrivateKey.exe)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b8846a95-3fcc-4e8c-b9c0-128d975a6307
caps.latest.revision: "13"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 5e2110e129b293ffb04c8e3eb69a5c3bfe83c17b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="find-private-key-tool-findprivatekeyexe"></a><span data-ttu-id="3550f-102">“查找私钥”工具 (FindPrivateKey.exe)</span><span class="sxs-lookup"><span data-stu-id="3550f-102">Find Private Key Tool (FindPrivateKey.exe)</span></span>
<span data-ttu-id="3550f-103">可以使用此命令行工具从证书存储区中检索私钥。</span><span class="sxs-lookup"><span data-stu-id="3550f-103">This command-line tool can be used to retrieve a private key from a certificate store.</span></span> <span data-ttu-id="3550f-104">例如，可以使用 FindPrivateKey.exe 来查找与证书存储区中特定 X.509 证书关联的私钥文件的位置和名称。</span><span class="sxs-lookup"><span data-stu-id="3550f-104">For example, FindPrivateKey.exe can be used to find the location and name of the private key file associated with a specific X.509 certificate in the certificate store.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="3550f-105">FindPrivateKey 工具附带作为一个 WCF 示例。</span><span class="sxs-lookup"><span data-stu-id="3550f-105">The FindPrivateKey tool is shipped as a WCF sample.</span></span> <span data-ttu-id="3550f-106">有关在何处找到此示例以及如何构建此示例的更多信息，请参见</span><span class="sxs-lookup"><span data-stu-id="3550f-106">For more information about where to find the sample and how to build it, see</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3550f-107">语法</span><span class="sxs-lookup"><span data-stu-id="3550f-107">Syntax</span></span>  
  
```  
FindPrivateKey<storeName> <storeLocation> [{ {-n <subjectName>} | {-t <thumbprint>} } [-f | -d | -a]]  
```  
  
## <a name="remarks"></a><span data-ttu-id="3550f-108">备注</span><span class="sxs-lookup"><span data-stu-id="3550f-108">Remarks</span></span>  
 <span data-ttu-id="3550f-109">下表介绍了可用于“查找私钥”工具 (FindPrivateKey.exe) 的自变量和选项。</span><span class="sxs-lookup"><span data-stu-id="3550f-109">The following tables describe the arguments and the options that can be used with the Find Private Key tool (FindPrivateKey.exe).</span></span>  
  
|<span data-ttu-id="3550f-110">参数</span><span class="sxs-lookup"><span data-stu-id="3550f-110">Argument</span></span>|<span data-ttu-id="3550f-111">描述</span><span class="sxs-lookup"><span data-stu-id="3550f-111">Description</span></span>|  
|--------------|-----------------|  
|`storeName`|<span data-ttu-id="3550f-112">证书存储区的名称。</span><span class="sxs-lookup"><span data-stu-id="3550f-112">Name of the certificate store.</span></span>|  
|`storeLocation`|<span data-ttu-id="3550f-113">证书存储区的位置。</span><span class="sxs-lookup"><span data-stu-id="3550f-113">The location of the certificate store.</span></span>|  
  
|<span data-ttu-id="3550f-114">选项</span><span class="sxs-lookup"><span data-stu-id="3550f-114">Option</span></span>|<span data-ttu-id="3550f-115">描述</span><span class="sxs-lookup"><span data-stu-id="3550f-115">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="3550f-116">`/n <`*subjectName*`>`</span><span class="sxs-lookup"><span data-stu-id="3550f-116">`/n <` *subjectName* `>`</span></span>|<span data-ttu-id="3550f-117">指定证书的主题名称。</span><span class="sxs-lookup"><span data-stu-id="3550f-117">Specifies the subject name of the certificate.</span></span>|  
|<span data-ttu-id="3550f-118">`/t <`*指纹*`>`</span><span class="sxs-lookup"><span data-stu-id="3550f-118">`/t <` *thumbprint* `>`</span></span>|<span data-ttu-id="3550f-119">指定证书的指纹。</span><span class="sxs-lookup"><span data-stu-id="3550f-119">Specifies the thumbprint of the certificate.</span></span> <span data-ttu-id="3550f-120">使用 Certmgr.exe 来检索证书的指纹。</span><span class="sxs-lookup"><span data-stu-id="3550f-120">Use Certmgr.exe to retrieve the thumbprint of the certificate.</span></span>|  
|`/f`|<span data-ttu-id="3550f-121">只输出文件名。</span><span class="sxs-lookup"><span data-stu-id="3550f-121">Outputs the file name only.</span></span>|  
|`/d`|<span data-ttu-id="3550f-122">只输出目录。</span><span class="sxs-lookup"><span data-stu-id="3550f-122">Outputs the directory only.</span></span>|  
|`/a`|<span data-ttu-id="3550f-123">输出绝对文件名。</span><span class="sxs-lookup"><span data-stu-id="3550f-123">Outputs the absolute file name.</span></span>|  
  
## <a name="examples"></a><span data-ttu-id="3550f-124">示例</span><span class="sxs-lookup"><span data-stu-id="3550f-124">Examples</span></span>  
 <span data-ttu-id="3550f-125">下面的命令检索 John Doe 的私钥。</span><span class="sxs-lookup"><span data-stu-id="3550f-125">The following command retrieves the private key for John Doe.</span></span>  
  
```  
FindPrivateKey My CurrentUser -n "CN=John Doe"  
```  
  
 <span data-ttu-id="3550f-126">下面的命令检索本地计算机的私钥。</span><span class="sxs-lookup"><span data-stu-id="3550f-126">The following command retrieves the private key for the local machine.</span></span>  
  
```  
FindPrivateKey My LocalMachine -t "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52" –a  
```
