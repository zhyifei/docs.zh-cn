---
title: AXL_AUTHENTICODE_TIMESTAMPER_INFO 结构
ms.date: 03/30/2017
ms.assetid: 89e41a81-0f41-45ad-8f20-a120e4ff24fb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3d82ed3299f967457fe967d096a238da6143751a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59219156"
---
# <a name="axlauthenticodetimestamperinfo-structure"></a><span data-ttu-id="c0fea-102">AXL_AUTHENTICODE_TIMESTAMPER_INFO 结构</span><span class="sxs-lookup"><span data-stu-id="c0fea-102">AXL_AUTHENTICODE_TIMESTAMPER_INFO Structure</span></span>
<span data-ttu-id="c0fea-103">定义验证码时间戳签署人的信息。</span><span class="sxs-lookup"><span data-stu-id="c0fea-103">Defines the Authenticode time stamper information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0fea-104">语法</span><span class="sxs-lookup"><span data-stu-id="c0fea-104">Syntax</span></span>  
  
```  
typedef struct _AXL_AUTHENTICODE_SIGNER_INFO {  
    DWORD cbSize;  
    HRESULT dwError;  
    ALG_ID algHash;  
    FILETIME ftTimestamp  
    PCCERT_CHAIN_CONTEXT pChainContext;  
} AXL_AUTHENTICODE_TIMESTAMPER_INFO, * PAXL_AUTHENTICODE_TIMESTAMPER_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="c0fea-105">成员</span><span class="sxs-lookup"><span data-stu-id="c0fea-105">Members</span></span>  
  
|<span data-ttu-id="c0fea-106">成员</span><span class="sxs-lookup"><span data-stu-id="c0fea-106">Member</span></span>|<span data-ttu-id="c0fea-107">描述</span><span class="sxs-lookup"><span data-stu-id="c0fea-107">Description</span></span>|  
|------------|-----------------|  
|`cbSize`|<span data-ttu-id="c0fea-108">此结构的大小。</span><span class="sxs-lookup"><span data-stu-id="c0fea-108">The size of this structure.</span></span>|  
|`dwError`|<span data-ttu-id="c0fea-109">错误代码。</span><span class="sxs-lookup"><span data-stu-id="c0fea-109">The error code.</span></span>|  
|`algHash`|<span data-ttu-id="c0fea-110">哈希算法。</span><span class="sxs-lookup"><span data-stu-id="c0fea-110">The hash algorithm.</span></span>|  
|`ftTimestamp`|<span data-ttu-id="c0fea-111">时间戳的时间。</span><span class="sxs-lookup"><span data-stu-id="c0fea-111">The time of the time stamp.</span></span>|  
|`pChainContext`|<span data-ttu-id="c0fea-112">时间戳签署人的链上下文。</span><span class="sxs-lookup"><span data-stu-id="c0fea-112">The time stamper’s chain context.</span></span>  <span data-ttu-id="c0fea-113">请参阅[CERT_CONTEXT](/windows/desktop/api/wincrypt/ns-wincrypt-_cert_context)结构。</span><span class="sxs-lookup"><span data-stu-id="c0fea-113">See the [CERT_CONTEXT](/windows/desktop/api/wincrypt/ns-wincrypt-_cert_context) structure.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c0fea-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="c0fea-114">See also</span></span>

- [<span data-ttu-id="c0fea-115">验证码</span><span class="sxs-lookup"><span data-stu-id="c0fea-115">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
