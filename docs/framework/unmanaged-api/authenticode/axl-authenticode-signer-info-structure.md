---
title: AXL_AUTHENTICODE_SIGNER_INFO 结构
ms.date: 03/30/2017
ms.assetid: 81c0f8b4-ce35-4716-8651-b642d40648a2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0c69be0de98e2996176e7360bae0bb0736c1a797
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/15/2019
ms.locfileid: "69038443"
---
# <a name="axl_authenticode_signer_info-structure"></a>AXL_AUTHENTICODE_SIGNER_INFO 结构
定义验证码签署人的信息。  
  
## <a name="syntax"></a>语法  
  
```cpp  
typedef struct _AXL_AUTHENTICODE_SIGNER_INFO {  
    DWORD cbSize;  
    HRESULT dwError;  
    ALG_ID algHash;  
    LPCWSTR pwszHash  
    LPCWSTR pwszDescription;  
    LPCWSTR pwszDescriptionUrl;  
    PCCERT_CHAIN_CONTEXT pChainContext  
} AXL_AUTHENTICODE_SIGNER_INFO, * PAXL_AUTHENTICODE_SIGNER_INFO;  
```  
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|`cbSize`|此结构的大小。|  
|`dwError`|错误代码。|  
|`algHash`|哈希算法。|  
|`pwszHash`|哈希。|  
|`pwszDescription`|说明。|  
|`pwszDescriptionUrl`|说明的 URL。|  
|`pChainContext`|签署人的链上下文。 请参阅[CERT_CONTEXT](/windows/win32/api/wincrypt/ns-wincrypt-cert_context)结构。|  
  
## <a name="see-also"></a>请参阅

- [验证码](../../../../docs/framework/unmanaged-api/authenticode/index.md)
