---
title: "在联合方案中混合信任协议"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d7b5fee9-2246-4b09-b8d7-9e63cb817279
caps.latest.revision: "7"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 007dec81766423ea2826e98ae0b6b399a1508f11
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="mixing-trust-protocols-in-federated-scenarios"></a><span data-ttu-id="a3d26-102">在联合方案中混合信任协议</span><span class="sxs-lookup"><span data-stu-id="a3d26-102">Mixing Trust Protocols in Federated Scenarios</span></span>
<span data-ttu-id="a3d26-103">联合客户端与服务进行通信时，有些服务的信任版本与安全令牌服务 (STS) 的信任版本不同。</span><span class="sxs-lookup"><span data-stu-id="a3d26-103">There may be scenarios in which federated clients communicate with a service and a Security Token Service (STS) that do not have the same trust version.</span></span> <span data-ttu-id="a3d26-104">服务 WSDL 包含的 `RequestSecurityTokenTemplate` 断言可能具有与 STS 不同版本的 WS-Trust 元素。</span><span class="sxs-lookup"><span data-stu-id="a3d26-104">The service WSDL can contain a `RequestSecurityTokenTemplate` assertion with WS-Trust elements that are of different versions than the STS.</span></span> <span data-ttu-id="a3d26-105">在这些情况下，[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 客户端会转换从 `RequestSecurityTokenTemplate` 接收的 WS-Trust 元素以匹配 STS 信任版本。</span><span class="sxs-lookup"><span data-stu-id="a3d26-105">In such cases, a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] client converts the WS-Trust elements received from the `RequestSecurityTokenTemplate` to match the STS trust version.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="a3d26-106"> 只处理标准绑定的不匹配信任版本。</span><span class="sxs-lookup"><span data-stu-id="a3d26-106"> handles mismatched trust versions only for standard bindings.</span></span> <span data-ttu-id="a3d26-107">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 识别的所有标准算法参数都是标准绑定的一部份。</span><span class="sxs-lookup"><span data-stu-id="a3d26-107">All standard algorithm parameters that are recognized by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] are part of the standard binding.</span></span> <span data-ttu-id="a3d26-108">本主题介绍 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 在服务与 STS 分别具有各种信任设置时的行为。</span><span class="sxs-lookup"><span data-stu-id="a3d26-108">This topic describes the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] behavior with various trust settings between the service and the STS.</span></span>  
  
## <a name="rp-feb-2005-and-sts-feb-2005"></a><span data-ttu-id="a3d26-109">RP Feb 2005 和 STS Feb 2005</span><span class="sxs-lookup"><span data-stu-id="a3d26-109">RP Feb 2005 and STS Feb 2005</span></span>  
 <span data-ttu-id="a3d26-110">依赖方 (RP) 的 WSDL 在 `RequestSecurityTokenTemplate` 节中包含以下元素：</span><span class="sxs-lookup"><span data-stu-id="a3d26-110">The WSDL for Relying Party (RP) contains the following elements within the `RequestSecurityTokenTemplate` section:</span></span>  
  
-   `CanonicalizationAlgorithm`  
  
-   `EncryptionAlgorithm`  
  
-   `EncryptWith`  
  
-   `SignWith`  
  
-   `KeySize`  
  
-   `KeyType`  
  
 <span data-ttu-id="a3d26-111">客户端配置文件包含一个参数列表。</span><span class="sxs-lookup"><span data-stu-id="a3d26-111">The client configuration file contains a list of parameters.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="a3d26-112"> 无法区分客户端参数和服务参数；它添加所有参数并在 `RequestSecurityTokenTemplate` (RST) 中发送这些参数。</span><span class="sxs-lookup"><span data-stu-id="a3d26-112"> cannot differentiate between the client and service parameters; it adds all the parameters and sends them in the `RequestSecurityTokenTemplate` (RST).</span></span>  
  
## <a name="rp-trust-13-and-sts-trust-13"></a><span data-ttu-id="a3d26-113">RP Trust 1.3 和 STS Trust 1.3</span><span class="sxs-lookup"><span data-stu-id="a3d26-113">RP Trust 1.3 and STS Trust 1.3</span></span>  
 <span data-ttu-id="a3d26-114">RP 的 WSDL 在 `RequestSecurityTokenTemplate` 节中包含以下元素：</span><span class="sxs-lookup"><span data-stu-id="a3d26-114">The WSDL for RP contains the following elements within the `RequestSecurityTokenTemplate` section:</span></span>  
  
-   `CanonicalizationAlgorithm`  
  
-   `EncryptionAlgorithm`  
  
-   `EncryptWith`  
  
-   `SignWith`  
  
-   `KeySize`  
  
-   `KeyType`  
  
-   `KeyWrapAlgorithm`  
  
 <span data-ttu-id="a3d26-115">客户端配置文件包含一个 `secondaryParameters` 元素，该元素包装 RP 所指定的参数。</span><span class="sxs-lookup"><span data-stu-id="a3d26-115">The client configuration file contains a `secondaryParameters` element that wraps the parameters specified by the RP.</span></span>  
  
 <span data-ttu-id="a3d26-116">如果 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]、`EncryptionAlgorithm` 和 `CanonicalizationAlgorithm` 元素存在于 `KeyWrapAlgorithm` 元素内，则 `SecondaryParameters` 将从 RST 下的顶级元素移除这三个元素。</span><span class="sxs-lookup"><span data-stu-id="a3d26-116">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] removes the `EncryptionAlgorithm`, `CanonicalizationAlgorithm` and `KeyWrapAlgorithm` elements from the top-level element under the RST if these are present inside the `SecondaryParameters` element.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="a3d26-117"> 将 `SecondaryParameters` 元素不经修改地追加到传出 RST 中。</span><span class="sxs-lookup"><span data-stu-id="a3d26-117"> appends the `SecondaryParameters` element to the outgoing RST unmodified.</span></span>  
  
## <a name="rp-trust-feb-2005-and-sts-trust-13"></a><span data-ttu-id="a3d26-118">RP Trust Feb 2005 和 STS Trust 1.3</span><span class="sxs-lookup"><span data-stu-id="a3d26-118">RP Trust Feb 2005 and STS Trust 1.3</span></span>  
 <span data-ttu-id="a3d26-119">RP 的 WSDL 在 `RequestSecurityTokenTemplate` 节中包含以下元素：</span><span class="sxs-lookup"><span data-stu-id="a3d26-119">The WSDL for RP contains the following elements in the `RequestSecurityTokenTemplate` section:</span></span>  
  
-   `CanonicalizationAlgorithm`  
  
-   `EncryptionAlgorithm`  
  
-   `EncryptWith`  
  
-   `SignWith`  
  
-   `KeySize`  
  
-   `KeyType`  
  
 <span data-ttu-id="a3d26-120">客户端配置文件包含一个参数列表。</span><span class="sxs-lookup"><span data-stu-id="a3d26-120">The client configuration file contains a list of parameters.</span></span>  
  
 <span data-ttu-id="a3d26-121">在客户端配置文件中，[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 无法区分服务参数与客户端参数。</span><span class="sxs-lookup"><span data-stu-id="a3d26-121">From the client configuration file, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] cannot differentiate between the service and client parameters.</span></span> <span data-ttu-id="a3d26-122">因此 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 将所有参数都转换为 Trust 1.3 版命名空间。</span><span class="sxs-lookup"><span data-stu-id="a3d26-122">Therefore [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] converts all the parameters to a Trust version 1.3 namespace.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="a3d26-123"> 按以下方式处理 `KeyType`、`KeySize` 和 `TokenType` 元素：</span><span class="sxs-lookup"><span data-stu-id="a3d26-123"> handles the `KeyType`, `KeySize`, and `TokenType` elements as follows:</span></span>  
  
-   <span data-ttu-id="a3d26-124">下载 WSDL，创建绑定，并从 RP 参数分配 `KeyType`、`KeySize` 和 `TokenType`。</span><span class="sxs-lookup"><span data-stu-id="a3d26-124">Download the WSDL, create the binding, and assign `KeyType`, `KeySize`, and `TokenType` from the RP parameters.</span></span> <span data-ttu-id="a3d26-125">随后会生成客户端配置文件。</span><span class="sxs-lookup"><span data-stu-id="a3d26-125">The client configuration file is then generated.</span></span>  
  
-   <span data-ttu-id="a3d26-126">客户端现在可以更改配置文件中的任何参数。</span><span class="sxs-lookup"><span data-stu-id="a3d26-126">The client can now change any parameter in the configuration file.</span></span>  
  
-   <span data-ttu-id="a3d26-127">在运行时，[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 将除 `AdditionalTokenParameters`、`KeyType` 和 `KeySize` 之外的所有指定参数复制到客户端配置文件的 `TokenType` 节中，因为这三个参数的版本问题在配置文件生成期间已得到解决。</span><span class="sxs-lookup"><span data-stu-id="a3d26-127">During runtime, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] copies all parameters specified into the `AdditionalTokenParameters` section of the client configuration file except `KeyType`, `KeySize` and `TokenType`, because these parameters are accounted for during the configuration file generation.</span></span>  
  
## <a name="rp-trust-13-and-sts-trust-feb-2005"></a><span data-ttu-id="a3d26-128">RP Trust 1.3 和 STS Trust Feb 2005</span><span class="sxs-lookup"><span data-stu-id="a3d26-128">RP Trust 1.3 and STS Trust Feb 2005</span></span>  
 <span data-ttu-id="a3d26-129">RP 的 WSDL 在 `RequestSecurityTokenTemplate` 节中包含以下元素：</span><span class="sxs-lookup"><span data-stu-id="a3d26-129">The WSDL for RP contains the following elements in the `RequestSecurityTokenTemplate` section:</span></span>  
  
-   `CanonicalizationAlgorithm`  
  
-   `EncryptionAlgorithm`  
  
-   `EncryptWith`  
  
-   `SignWith`  
  
-   `KeySize`  
  
-   `KeyType`  
  
-   `KeyWrapAlgorithm`  
  
 <span data-ttu-id="a3d26-130">客户端配置文件包含一个 `secondaryParamters` 元素，该元素包装 RP 所指定的参数。</span><span class="sxs-lookup"><span data-stu-id="a3d26-130">The client configuration file contains a `secondaryParamters` element that wraps the parameters specified by the RP.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="a3d26-131"> 将 `SecondaryParameters` 节中指定的所有参数复制到顶级 RST 元素中，但不会将这些参数转换为 2005 WS-Trust 命名空间。</span><span class="sxs-lookup"><span data-stu-id="a3d26-131"> copies all the parameters specified within the `SecondaryParameters` section to the top-level RST element, but does not convert them to the 2005 WS-Trust namespace.</span></span>
