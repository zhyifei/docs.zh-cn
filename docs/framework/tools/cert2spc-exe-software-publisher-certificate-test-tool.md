---
title: "Cert2spc.exe（软件发行者证书测试工具）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- SPC
- Software Publisher Certificate Test tool
- Software Publisher Certificate
- Cert2spc.exe
- certificates, Software Publisher's Certificate
ms.assetid: be434d7d-9c0d-46e7-8392-58a9b542d11d
caps.latest.revision: 21
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 7109f96b6997670afa6ef7c362b9e1a142014fbe
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="cert2spcexe-software-publisher-certificate-test-tool"></a><span data-ttu-id="ab45e-102">Cert2spc.exe（软件发行者证书测试工具）</span><span class="sxs-lookup"><span data-stu-id="ab45e-102">Cert2spc.exe (Software Publisher Certificate Test Tool)</span></span>
<span data-ttu-id="ab45e-103">软件发行者证书测试工具从一个或多个 X.509 证书创建软件发行者证书 (SPC)。</span><span class="sxs-lookup"><span data-stu-id="ab45e-103">The Software Publisher Certificate Test tool creates a Software Publisher's Certificate (SPC) from one or more X.509 certificates.</span></span> <span data-ttu-id="ab45e-104">Cert2spc.exe 仅用于测试目的。</span><span class="sxs-lookup"><span data-stu-id="ab45e-104">Cert2spc.exe is for test purposes only.</span></span> <span data-ttu-id="ab45e-105">可以从证书颁发机构（如 VeriSign 或 Thawte）获得有效 SPC。</span><span class="sxs-lookup"><span data-stu-id="ab45e-105">You can obtain a valid SPC from a Certification Authority such as VeriSign or Thawte.</span></span> <span data-ttu-id="ab45e-106">有关创建 X.509 证书的详细信息，请参阅 [Makecert.exe（证书创建工具）](http://msdn.microsoft.com/library/b0343f8e-9c41-4852-a85c-f8a0c408cf0d)。</span><span class="sxs-lookup"><span data-stu-id="ab45e-106">For more information about creating X.509 certificates, see [Makecert.exe (Certificate Creation Tool)](http://msdn.microsoft.com/library/b0343f8e-9c41-4852-a85c-f8a0c408cf0d).</span></span>  
  
 <span data-ttu-id="ab45e-107">此工具会自动随 Visual Studio 一起安装。</span><span class="sxs-lookup"><span data-stu-id="ab45e-107">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="ab45e-108">若要运行此工具，请使用开发人员命令提示（或 Windows 7 中的 Visual Studio 命令提示）。</span><span class="sxs-lookup"><span data-stu-id="ab45e-108">To run the tool, use the Developer Command Prompt (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="ab45e-109">有关详细信息，请参阅[命令提示](../../../docs/framework/tools/developer-command-prompt-for-vs.md)。</span><span class="sxs-lookup"><span data-stu-id="ab45e-109">For more information, see [Command Prompts](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span></span>  
  
 <span data-ttu-id="ab45e-110">在命令提示符处，键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="ab45e-110">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab45e-111">语法</span><span class="sxs-lookup"><span data-stu-id="ab45e-111">Syntax</span></span>  
  
```  
cert2spc cert1.cer | crl1.crl [... certN.cer | crlN.crl] outputSPCfile.spc  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ab45e-112">参数</span><span class="sxs-lookup"><span data-stu-id="ab45e-112">Parameters</span></span>  
  
|<span data-ttu-id="ab45e-113">参数</span><span class="sxs-lookup"><span data-stu-id="ab45e-113">Argument</span></span>|<span data-ttu-id="ab45e-114">描述</span><span class="sxs-lookup"><span data-stu-id="ab45e-114">Description</span></span>|  
|--------------|-----------------|  
|`certN.cer`|<span data-ttu-id="ab45e-115">要包含在 SPC 文件中的 X.509 证书的名称。</span><span class="sxs-lookup"><span data-stu-id="ab45e-115">The name of an X.509 certificate to include in the SPC file.</span></span> <span data-ttu-id="ab45e-116">可以指定用空格分隔的多个名称。</span><span class="sxs-lookup"><span data-stu-id="ab45e-116">You can specify multiple names separated by spaces.</span></span>|  
|`crlN.crl`|<span data-ttu-id="ab45e-117">要包含在 SPC 文件中的证书吊销列表的名称。</span><span class="sxs-lookup"><span data-stu-id="ab45e-117">The name of a certificate revocation list to include in the SPC file.</span></span> <span data-ttu-id="ab45e-118">可以指定用空格分隔的多个名称。</span><span class="sxs-lookup"><span data-stu-id="ab45e-118">You can specify multiple names separated by spaces.</span></span>|  
|`outputSPCfile.spc`|<span data-ttu-id="ab45e-119">将包含 X.509 证书的 PKCS #7 对象的名称。</span><span class="sxs-lookup"><span data-stu-id="ab45e-119">The name of the PKCS #7 object that will contain the X.509 certificates.</span></span>|  
  
|<span data-ttu-id="ab45e-120">选项</span><span class="sxs-lookup"><span data-stu-id="ab45e-120">Option</span></span>|<span data-ttu-id="ab45e-121">描述</span><span class="sxs-lookup"><span data-stu-id="ab45e-121">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="ab45e-122">**/?**</span><span class="sxs-lookup"><span data-stu-id="ab45e-122">**/?**</span></span>|<span data-ttu-id="ab45e-123">显示该工具的命令语法和选项。</span><span class="sxs-lookup"><span data-stu-id="ab45e-123">Displays command syntax and options for the tool.</span></span>|  
  
## <a name="examples"></a><span data-ttu-id="ab45e-124">示例</span><span class="sxs-lookup"><span data-stu-id="ab45e-124">Examples</span></span>  
 <span data-ttu-id="ab45e-125">下面的命令从 `myCertificate.cer` 创建一个 SPC 并将其放入 `mySPCFile.spc`。</span><span class="sxs-lookup"><span data-stu-id="ab45e-125">The following command creates an SPC from `myCertificate.cer` and places it in `mySPCFile.spc`.</span></span>  
  
```  
cert2spc myCertificate.cer mySPCFile.spc  
```  
  
 <span data-ttu-id="ab45e-126">下面的命令从 `oneCertificate.cer` 和 `twoCertificate.cer` 创建一个 SPC，并将其放入 `mySPCFile.spc`。</span><span class="sxs-lookup"><span data-stu-id="ab45e-126">The following command creates an SPC from `oneCertificate.cer` and `twoCertificate.cer`, and places it in `mySPCFile.spc`.</span></span>  
  
```  
cert2spc oneCertificate.cer twoCertificate.cer mySPCFile.spc  
```  
  
## <a name="see-also"></a><span data-ttu-id="ab45e-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ab45e-127">See Also</span></span>  
 <span data-ttu-id="ab45e-128">[工具](../../../docs/framework/tools/index.md) </span><span class="sxs-lookup"><span data-stu-id="ab45e-128">[Tools](../../../docs/framework/tools/index.md) </span></span>  
 <span data-ttu-id="ab45e-129">[Makecert.exe（证书创建工具）](http://msdn.microsoft.com/library/b0343f8e-9c41-4852-a85c-f8a0c408cf0d) </span><span class="sxs-lookup"><span data-stu-id="ab45e-129">[Makecert.exe (Certificate Creation Tool)](http://msdn.microsoft.com/library/b0343f8e-9c41-4852-a85c-f8a0c408cf0d) </span></span>  
 [<span data-ttu-id="ab45e-130">命令提示</span><span class="sxs-lookup"><span data-stu-id="ab45e-130">Command Prompts</span></span>](../../../docs/framework/tools/developer-command-prompt-for-vs.md)

