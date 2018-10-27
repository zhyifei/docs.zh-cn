---
title: 在联合方案中混合信任协议
ms.date: 03/30/2017
ms.assetid: d7b5fee9-2246-4b09-b8d7-9e63cb817279
ms.openlocfilehash: ce5c3a1875d84d98068dcc78d8346a88bc0b28f3
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2018
ms.locfileid: "50182900"
---
# <a name="mixing-trust-protocols-in-federated-scenarios"></a><span data-ttu-id="c2e41-102">在联合方案中混合信任协议</span><span class="sxs-lookup"><span data-stu-id="c2e41-102">Mixing Trust Protocols in Federated Scenarios</span></span>
<span data-ttu-id="c2e41-103">联合客户端与服务进行通信时，有些服务的信任版本与安全令牌服务 (STS) 的信任版本不同。</span><span class="sxs-lookup"><span data-stu-id="c2e41-103">There may be scenarios in which federated clients communicate with a service and a Security Token Service (STS) that do not have the same trust version.</span></span> <span data-ttu-id="c2e41-104">服务 WSDL 包含的 `RequestSecurityTokenTemplate` 断言可能具有与 STS 不同版本的 WS-Trust 元素。</span><span class="sxs-lookup"><span data-stu-id="c2e41-104">The service WSDL can contain a `RequestSecurityTokenTemplate` assertion with WS-Trust elements that are of different versions than the STS.</span></span> <span data-ttu-id="c2e41-105">在这种情况下，Windows Communication Foundation (WCF) 客户端将从接收的 Ws-trust 元素`RequestSecurityTokenTemplate`以匹配 STS 信任版本。</span><span class="sxs-lookup"><span data-stu-id="c2e41-105">In such cases, a Windows Communication Foundation (WCF) client converts the WS-Trust elements received from the `RequestSecurityTokenTemplate` to match the STS trust version.</span></span> <span data-ttu-id="c2e41-106">WCF 处理标准绑定不匹配的信任版本。</span><span class="sxs-lookup"><span data-stu-id="c2e41-106">WCF handles mismatched trust versions only for standard bindings.</span></span> <span data-ttu-id="c2e41-107">由 WCF 识别的所有标准算法参数为标准绑定的一部分。</span><span class="sxs-lookup"><span data-stu-id="c2e41-107">All standard algorithm parameters that are recognized by WCF are part of the standard binding.</span></span> <span data-ttu-id="c2e41-108">本主题介绍 WCF 行为的各种服务和 STS 之间的信任设置。</span><span class="sxs-lookup"><span data-stu-id="c2e41-108">This topic describes the WCF behavior with various trust settings between the service and the STS.</span></span>  
  
## <a name="rp-feb-2005-and-sts-feb-2005"></a><span data-ttu-id="c2e41-109">RP Feb 2005 和 STS Feb 2005</span><span class="sxs-lookup"><span data-stu-id="c2e41-109">RP Feb 2005 and STS Feb 2005</span></span>  
 <span data-ttu-id="c2e41-110">依赖方 (RP) 的 WSDL 在 `RequestSecurityTokenTemplate` 节中包含以下元素：</span><span class="sxs-lookup"><span data-stu-id="c2e41-110">The WSDL for Relying Party (RP) contains the following elements within the `RequestSecurityTokenTemplate` section:</span></span>  
  
-   `CanonicalizationAlgorithm`  
  
-   `EncryptionAlgorithm`  
  
-   `EncryptWith`  
  
-   `SignWith`  
  
-   `KeySize`  
  
-   `KeyType`  
  
 <span data-ttu-id="c2e41-111">客户端配置文件包含一个参数列表。</span><span class="sxs-lookup"><span data-stu-id="c2e41-111">The client configuration file contains a list of parameters.</span></span>  
  
 <span data-ttu-id="c2e41-112">WCF 无法区分的客户端和服务的参数;它将添加所有参数并将它们发送`RequestSecurityTokenTemplate`(RST)。</span><span class="sxs-lookup"><span data-stu-id="c2e41-112">WCF cannot differentiate between the client and service parameters; it adds all the parameters and sends them in the `RequestSecurityTokenTemplate` (RST).</span></span>  
  
## <a name="rp-trust-13-and-sts-trust-13"></a><span data-ttu-id="c2e41-113">RP Trust 1.3 和 STS Trust 1.3</span><span class="sxs-lookup"><span data-stu-id="c2e41-113">RP Trust 1.3 and STS Trust 1.3</span></span>  
 <span data-ttu-id="c2e41-114">RP 的 WSDL 在 `RequestSecurityTokenTemplate` 节中包含以下元素：</span><span class="sxs-lookup"><span data-stu-id="c2e41-114">The WSDL for RP contains the following elements within the `RequestSecurityTokenTemplate` section:</span></span>  
  
-   `CanonicalizationAlgorithm`  
  
-   `EncryptionAlgorithm`  
  
-   `EncryptWith`  
  
-   `SignWith`  
  
-   `KeySize`  
  
-   `KeyType`  
  
-   `KeyWrapAlgorithm`  
  
 <span data-ttu-id="c2e41-115">客户端配置文件包含一个 `secondaryParameters` 元素，该元素包装 RP 所指定的参数。</span><span class="sxs-lookup"><span data-stu-id="c2e41-115">The client configuration file contains a `secondaryParameters` element that wraps the parameters specified by the RP.</span></span>  
  
 <span data-ttu-id="c2e41-116">WCF 中移除`EncryptionAlgorithm`，`CanonicalizationAlgorithm`并`KeyWrapAlgorithm`如果它们存在内部 RST 下的顶级元素中的元素`SecondaryParameters`元素。</span><span class="sxs-lookup"><span data-stu-id="c2e41-116">WCF removes the `EncryptionAlgorithm`, `CanonicalizationAlgorithm` and `KeyWrapAlgorithm` elements from the top-level element under the RST if these are present inside the `SecondaryParameters` element.</span></span> <span data-ttu-id="c2e41-117">WCF 将追加`SecondaryParameters`到传出 RST 未修改的元素。</span><span class="sxs-lookup"><span data-stu-id="c2e41-117">WCF appends the `SecondaryParameters` element to the outgoing RST unmodified.</span></span>  
  
## <a name="rp-trust-feb-2005-and-sts-trust-13"></a><span data-ttu-id="c2e41-118">RP Trust Feb 2005 和 STS Trust 1.3</span><span class="sxs-lookup"><span data-stu-id="c2e41-118">RP Trust Feb 2005 and STS Trust 1.3</span></span>  
 <span data-ttu-id="c2e41-119">RP 的 WSDL 在 `RequestSecurityTokenTemplate` 节中包含以下元素：</span><span class="sxs-lookup"><span data-stu-id="c2e41-119">The WSDL for RP contains the following elements in the `RequestSecurityTokenTemplate` section:</span></span>  
  
-   `CanonicalizationAlgorithm`  
  
-   `EncryptionAlgorithm`  
  
-   `EncryptWith`  
  
-   `SignWith`  
  
-   `KeySize`  
  
-   `KeyType`  
  
 <span data-ttu-id="c2e41-120">客户端配置文件包含一个参数列表。</span><span class="sxs-lookup"><span data-stu-id="c2e41-120">The client configuration file contains a list of parameters.</span></span>  
  
 <span data-ttu-id="c2e41-121">从客户端配置文件中，WCF 不能区分服务和客户端参数。</span><span class="sxs-lookup"><span data-stu-id="c2e41-121">From the client configuration file, WCF cannot differentiate between the service and client parameters.</span></span> <span data-ttu-id="c2e41-122">因此 WCF 将转换为信任 1.3 版命名空间的所有参数。</span><span class="sxs-lookup"><span data-stu-id="c2e41-122">Therefore WCF converts all the parameters to a Trust version 1.3 namespace.</span></span>  
  
 <span data-ttu-id="c2e41-123">WCF 句柄`KeyType`， `KeySize`，和`TokenType`元素，如下所示：</span><span class="sxs-lookup"><span data-stu-id="c2e41-123">WCF handles the `KeyType`, `KeySize`, and `TokenType` elements as follows:</span></span>  
  
-   <span data-ttu-id="c2e41-124">下载 WSDL，创建绑定，并从 RP 参数分配 `KeyType`、`KeySize` 和 `TokenType`。</span><span class="sxs-lookup"><span data-stu-id="c2e41-124">Download the WSDL, create the binding, and assign `KeyType`, `KeySize`, and `TokenType` from the RP parameters.</span></span> <span data-ttu-id="c2e41-125">随后会生成客户端配置文件。</span><span class="sxs-lookup"><span data-stu-id="c2e41-125">The client configuration file is then generated.</span></span>  
  
-   <span data-ttu-id="c2e41-126">客户端现在可以更改配置文件中的任何参数。</span><span class="sxs-lookup"><span data-stu-id="c2e41-126">The client can now change any parameter in the configuration file.</span></span>  
  
-   <span data-ttu-id="c2e41-127">在运行时，WCF 将复制到指定的所有参数`AdditionalTokenParameters`除客户端配置文件节`KeyType`，`KeySize`和`TokenType`，因为这些参数在配置文件期间都考虑在内生成。</span><span class="sxs-lookup"><span data-stu-id="c2e41-127">During runtime, WCF copies all parameters specified into the `AdditionalTokenParameters` section of the client configuration file except `KeyType`, `KeySize` and `TokenType`, because these parameters are accounted for during the configuration file generation.</span></span>  
  
## <a name="rp-trust-13-and-sts-trust-feb-2005"></a><span data-ttu-id="c2e41-128">RP Trust 1.3 和 STS Trust Feb 2005</span><span class="sxs-lookup"><span data-stu-id="c2e41-128">RP Trust 1.3 and STS Trust Feb 2005</span></span>  
 <span data-ttu-id="c2e41-129">RP 的 WSDL 在 `RequestSecurityTokenTemplate` 节中包含以下元素：</span><span class="sxs-lookup"><span data-stu-id="c2e41-129">The WSDL for RP contains the following elements in the `RequestSecurityTokenTemplate` section:</span></span>  
  
-   `CanonicalizationAlgorithm`  
  
-   `EncryptionAlgorithm`  
  
-   `EncryptWith`  
  
-   `SignWith`  
  
-   `KeySize`  
  
-   `KeyType`  
  
-   `KeyWrapAlgorithm`  
  
 <span data-ttu-id="c2e41-130">客户端配置文件包含一个 `secondaryParamters` 元素，该元素包装 RP 所指定的参数。</span><span class="sxs-lookup"><span data-stu-id="c2e41-130">The client configuration file contains a `secondaryParamters` element that wraps the parameters specified by the RP.</span></span>  
  
 <span data-ttu-id="c2e41-131">WCF 将复制内指定的所有参数`SecondaryParameters`部分到顶级 RST 元素，但不会将它们转换为 2005 Ws-trust 命名空间。</span><span class="sxs-lookup"><span data-stu-id="c2e41-131">WCF copies all the parameters specified within the `SecondaryParameters` section to the top-level RST element, but does not convert them to the 2005 WS-Trust namespace.</span></span>
