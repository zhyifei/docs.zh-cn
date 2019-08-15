---
title: AXL_AUTHENTICODE_TIMESTAMPER_INFO 结构
ms.date: 03/30/2017
ms.assetid: 89e41a81-0f41-45ad-8f20-a120e4ff24fb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9eef89c9e560da65d670ffe59649b44a64f8da6a
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039609"
---
# <a name="axl_authenticode_timestamper_info-structure"></a><span data-ttu-id="07ea9-102">AXL_AUTHENTICODE_TIMESTAMPER_INFO 结构</span><span class="sxs-lookup"><span data-stu-id="07ea9-102">AXL_AUTHENTICODE_TIMESTAMPER_INFO Structure</span></span>
<span data-ttu-id="07ea9-103">定义验证码时间戳签署人的信息。</span><span class="sxs-lookup"><span data-stu-id="07ea9-103">Defines the Authenticode time stamper information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07ea9-104">语法</span><span class="sxs-lookup"><span data-stu-id="07ea9-104">Syntax</span></span>  
  
```cpp  
typedef struct _AXL_AUTHENTICODE_SIGNER_INFO {  
    DWORD cbSize;  
    HRESULT dwError;  
    ALG_ID algHash;  
    FILETIME ftTimestamp  
    PCCERT_CHAIN_CONTEXT pChainContext;  
} AXL_AUTHENTICODE_TIMESTAMPER_INFO, * PAXL_AUTHENTICODE_TIMESTAMPER_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="07ea9-105">成员</span><span class="sxs-lookup"><span data-stu-id="07ea9-105">Members</span></span>  
  
|<span data-ttu-id="07ea9-106">成员</span><span class="sxs-lookup"><span data-stu-id="07ea9-106">Member</span></span>|<span data-ttu-id="07ea9-107">描述</span><span class="sxs-lookup"><span data-stu-id="07ea9-107">Description</span></span>|  
|------------|-----------------|  
|`cbSize`|<span data-ttu-id="07ea9-108">此结构的大小。</span><span class="sxs-lookup"><span data-stu-id="07ea9-108">The size of this structure.</span></span>|  
|`dwError`|<span data-ttu-id="07ea9-109">错误代码。</span><span class="sxs-lookup"><span data-stu-id="07ea9-109">The error code.</span></span>|  
|`algHash`|<span data-ttu-id="07ea9-110">哈希算法。</span><span class="sxs-lookup"><span data-stu-id="07ea9-110">The hash algorithm.</span></span>|  
|`ftTimestamp`|<span data-ttu-id="07ea9-111">时间戳的时间。</span><span class="sxs-lookup"><span data-stu-id="07ea9-111">The time of the time stamp.</span></span>|  
|`pChainContext`|<span data-ttu-id="07ea9-112">时间戳签署人的链上下文。</span><span class="sxs-lookup"><span data-stu-id="07ea9-112">The time stamper’s chain context.</span></span>  <span data-ttu-id="07ea9-113">请参阅[CERT_CONTEXT](/windows/win32/api/wincrypt/ns-wincrypt-cert_context)结构。</span><span class="sxs-lookup"><span data-stu-id="07ea9-113">See the [CERT_CONTEXT](/windows/win32/api/wincrypt/ns-wincrypt-cert_context) structure.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="07ea9-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="07ea9-114">See also</span></span>

- [<span data-ttu-id="07ea9-115">验证码</span><span class="sxs-lookup"><span data-stu-id="07ea9-115">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
