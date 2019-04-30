---
title: 在联合方案中混合信任协议
ms.date: 03/30/2017
ms.assetid: d7b5fee9-2246-4b09-b8d7-9e63cb817279
ms.openlocfilehash: ce5c3a1875d84d98068dcc78d8346a88bc0b28f3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62046679"
---
# <a name="mixing-trust-protocols-in-federated-scenarios"></a>在联合方案中混合信任协议
联合客户端与服务进行通信时，有些服务的信任版本与安全令牌服务 (STS) 的信任版本不同。 服务 WSDL 包含的 `RequestSecurityTokenTemplate` 断言可能具有与 STS 不同版本的 WS-Trust 元素。 在这种情况下，Windows Communication Foundation (WCF) 客户端将从接收的 Ws-trust 元素`RequestSecurityTokenTemplate`以匹配 STS 信任版本。 WCF 处理标准绑定不匹配的信任版本。 由 WCF 识别的所有标准算法参数为标准绑定的一部分。 本主题介绍 WCF 行为的各种服务和 STS 之间的信任设置。  
  
## <a name="rp-feb-2005-and-sts-feb-2005"></a>RP Feb 2005 和 STS Feb 2005  
 依赖方 (RP) 的 WSDL 在 `RequestSecurityTokenTemplate` 节中包含以下元素：  
  
- `CanonicalizationAlgorithm`  
  
- `EncryptionAlgorithm`  
  
- `EncryptWith`  
  
- `SignWith`  
  
- `KeySize`  
  
- `KeyType`  
  
 客户端配置文件包含一个参数列表。  
  
 WCF 无法区分的客户端和服务的参数;它将添加所有参数并将它们发送`RequestSecurityTokenTemplate`(RST)。  
  
## <a name="rp-trust-13-and-sts-trust-13"></a>RP Trust 1.3 和 STS Trust 1.3  
 RP 的 WSDL 在 `RequestSecurityTokenTemplate` 节中包含以下元素：  
  
- `CanonicalizationAlgorithm`  
  
- `EncryptionAlgorithm`  
  
- `EncryptWith`  
  
- `SignWith`  
  
- `KeySize`  
  
- `KeyType`  
  
- `KeyWrapAlgorithm`  
  
 客户端配置文件包含一个 `secondaryParameters` 元素，该元素包装 RP 所指定的参数。  
  
 WCF 中移除`EncryptionAlgorithm`，`CanonicalizationAlgorithm`并`KeyWrapAlgorithm`如果它们存在内部 RST 下的顶级元素中的元素`SecondaryParameters`元素。 WCF 将追加`SecondaryParameters`到传出 RST 未修改的元素。  
  
## <a name="rp-trust-feb-2005-and-sts-trust-13"></a>RP Trust Feb 2005 和 STS Trust 1.3  
 RP 的 WSDL 在 `RequestSecurityTokenTemplate` 节中包含以下元素：  
  
- `CanonicalizationAlgorithm`  
  
- `EncryptionAlgorithm`  
  
- `EncryptWith`  
  
- `SignWith`  
  
- `KeySize`  
  
- `KeyType`  
  
 客户端配置文件包含一个参数列表。  
  
 从客户端配置文件中，WCF 不能区分服务和客户端参数。 因此 WCF 将转换为信任 1.3 版命名空间的所有参数。  
  
 WCF 句柄`KeyType`， `KeySize`，和`TokenType`元素，如下所示：  
  
- 下载 WSDL，创建绑定，并从 RP 参数分配 `KeyType`、`KeySize` 和 `TokenType`。 随后会生成客户端配置文件。  
  
- 客户端现在可以更改配置文件中的任何参数。  
  
- 在运行时，WCF 将复制到指定的所有参数`AdditionalTokenParameters`除客户端配置文件节`KeyType`，`KeySize`和`TokenType`，因为这些参数在配置文件期间都考虑在内生成。  
  
## <a name="rp-trust-13-and-sts-trust-feb-2005"></a>RP Trust 1.3 和 STS Trust Feb 2005  
 RP 的 WSDL 在 `RequestSecurityTokenTemplate` 节中包含以下元素：  
  
- `CanonicalizationAlgorithm`  
  
- `EncryptionAlgorithm`  
  
- `EncryptWith`  
  
- `SignWith`  
  
- `KeySize`  
  
- `KeyType`  
  
- `KeyWrapAlgorithm`  
  
 客户端配置文件包含一个 `secondaryParamters` 元素，该元素包装 RP 所指定的参数。  
  
 WCF 将复制内指定的所有参数`SecondaryParameters`部分到顶级 RST 元素，但不会将它们转换为 2005 Ws-trust 命名空间。
