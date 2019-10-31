---
title: AXL_AUTHENTICODE_TIMESTAMPER_INFO 结构
ms.date: 03/30/2017
ms.assetid: 89e41a81-0f41-45ad-8f20-a120e4ff24fb
ms.openlocfilehash: 036397928703aea6199a59ae9c1e66153c30ec7b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132493"
---
# <a name="axl_authenticode_timestamper_info-structure"></a><span data-ttu-id="ac361-102">AXL_AUTHENTICODE_TIMESTAMPER_INFO 结构</span><span class="sxs-lookup"><span data-stu-id="ac361-102">AXL_AUTHENTICODE_TIMESTAMPER_INFO Structure</span></span>
<span data-ttu-id="ac361-103">定义验证码时间戳签署人的信息。</span><span class="sxs-lookup"><span data-stu-id="ac361-103">Defines the Authenticode time stamper information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac361-104">语法</span><span class="sxs-lookup"><span data-stu-id="ac361-104">Syntax</span></span>  
  
```cpp  
typedef struct _AXL_AUTHENTICODE_SIGNER_INFO {  
    DWORD cbSize;  
    HRESULT dwError;  
    ALG_ID algHash;  
    FILETIME ftTimestamp  
    PCCERT_CHAIN_CONTEXT pChainContext;  
} AXL_AUTHENTICODE_TIMESTAMPER_INFO, * PAXL_AUTHENTICODE_TIMESTAMPER_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="ac361-105">Members</span><span class="sxs-lookup"><span data-stu-id="ac361-105">Members</span></span>  
  
|<span data-ttu-id="ac361-106">成员</span><span class="sxs-lookup"><span data-stu-id="ac361-106">Member</span></span>|<span data-ttu-id="ac361-107">描述</span><span class="sxs-lookup"><span data-stu-id="ac361-107">Description</span></span>|  
|------------|-----------------|  
|`cbSize`|<span data-ttu-id="ac361-108">此结构的大小。</span><span class="sxs-lookup"><span data-stu-id="ac361-108">The size of this structure.</span></span>|  
|`dwError`|<span data-ttu-id="ac361-109">错误代码。</span><span class="sxs-lookup"><span data-stu-id="ac361-109">The error code.</span></span>|  
|`algHash`|<span data-ttu-id="ac361-110">哈希算法。</span><span class="sxs-lookup"><span data-stu-id="ac361-110">The hash algorithm.</span></span>|  
|`ftTimestamp`|<span data-ttu-id="ac361-111">时间戳的时间。</span><span class="sxs-lookup"><span data-stu-id="ac361-111">The time of the time stamp.</span></span>|  
|`pChainContext`|<span data-ttu-id="ac361-112">时间戳签署人的链上下文。</span><span class="sxs-lookup"><span data-stu-id="ac361-112">The time stamper’s chain context.</span></span>  <span data-ttu-id="ac361-113">请参阅[CERT_CONTEXT](/windows/win32/api/wincrypt/ns-wincrypt-cert_context)结构。</span><span class="sxs-lookup"><span data-stu-id="ac361-113">See the [CERT_CONTEXT](/windows/win32/api/wincrypt/ns-wincrypt-cert_context) structure.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ac361-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="ac361-114">See also</span></span>

- [<span data-ttu-id="ac361-115">验证码</span><span class="sxs-lookup"><span data-stu-id="ac361-115">Authenticode</span></span>](index.md)
