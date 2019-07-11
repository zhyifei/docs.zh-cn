---
title: AXL_AUTHENTICODE_TIMESTAMPER_INFO 结构
ms.date: 03/30/2017
ms.assetid: 89e41a81-0f41-45ad-8f20-a120e4ff24fb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dce0e67479418cd8227c75fadd8872a41ae1a799
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67741351"
---
# <a name="axlauthenticodetimestamperinfo-structure"></a><span data-ttu-id="c8199-102">AXL_AUTHENTICODE_TIMESTAMPER_INFO 结构</span><span class="sxs-lookup"><span data-stu-id="c8199-102">AXL_AUTHENTICODE_TIMESTAMPER_INFO Structure</span></span>
<span data-ttu-id="c8199-103">定义验证码时间戳签署人的信息。</span><span class="sxs-lookup"><span data-stu-id="c8199-103">Defines the Authenticode time stamper information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8199-104">语法</span><span class="sxs-lookup"><span data-stu-id="c8199-104">Syntax</span></span>  
  
```cpp  
typedef struct _AXL_AUTHENTICODE_SIGNER_INFO {  
    DWORD cbSize;  
    HRESULT dwError;  
    ALG_ID algHash;  
    FILETIME ftTimestamp  
    PCCERT_CHAIN_CONTEXT pChainContext;  
} AXL_AUTHENTICODE_TIMESTAMPER_INFO, * PAXL_AUTHENTICODE_TIMESTAMPER_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="c8199-105">成员</span><span class="sxs-lookup"><span data-stu-id="c8199-105">Members</span></span>  
  
|<span data-ttu-id="c8199-106">成员</span><span class="sxs-lookup"><span data-stu-id="c8199-106">Member</span></span>|<span data-ttu-id="c8199-107">描述</span><span class="sxs-lookup"><span data-stu-id="c8199-107">Description</span></span>|  
|------------|-----------------|  
|`cbSize`|<span data-ttu-id="c8199-108">此结构的大小。</span><span class="sxs-lookup"><span data-stu-id="c8199-108">The size of this structure.</span></span>|  
|`dwError`|<span data-ttu-id="c8199-109">错误代码。</span><span class="sxs-lookup"><span data-stu-id="c8199-109">The error code.</span></span>|  
|`algHash`|<span data-ttu-id="c8199-110">哈希算法。</span><span class="sxs-lookup"><span data-stu-id="c8199-110">The hash algorithm.</span></span>|  
|`ftTimestamp`|<span data-ttu-id="c8199-111">时间戳的时间。</span><span class="sxs-lookup"><span data-stu-id="c8199-111">The time of the time stamp.</span></span>|  
|`pChainContext`|<span data-ttu-id="c8199-112">时间戳签署人的链上下文。</span><span class="sxs-lookup"><span data-stu-id="c8199-112">The time stamper’s chain context.</span></span>  <span data-ttu-id="c8199-113">请参阅[CERT_CONTEXT](/windows/desktop/api/wincrypt/ns-wincrypt-_cert_context)结构。</span><span class="sxs-lookup"><span data-stu-id="c8199-113">See the [CERT_CONTEXT](/windows/desktop/api/wincrypt/ns-wincrypt-_cert_context) structure.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c8199-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="c8199-114">See also</span></span>

- [<span data-ttu-id="c8199-115">验证码</span><span class="sxs-lookup"><span data-stu-id="c8199-115">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
