---
title: "AXL_AUTHENTICODE_TIMESTAMPER_INFO 结构"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 89e41a81-0f41-45ad-8f20-a120e4ff24fb
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 46c0646cfff79888db2b6b37184dd97da21e71e3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="axlauthenticodetimestamperinfo-structure"></a><span data-ttu-id="89401-102">AXL_AUTHENTICODE_TIMESTAMPER_INFO 结构</span><span class="sxs-lookup"><span data-stu-id="89401-102">AXL_AUTHENTICODE_TIMESTAMPER_INFO Structure</span></span>
<span data-ttu-id="89401-103">定义验证码时间戳签署人的信息。</span><span class="sxs-lookup"><span data-stu-id="89401-103">Defines the Authenticode time stamper information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89401-104">语法</span><span class="sxs-lookup"><span data-stu-id="89401-104">Syntax</span></span>  
  
```  
typedef struct _AXL_AUTHENTICODE_SIGNER_INFO {  
    DWORD cbSize;  
    HRESULT dwError;  
    ALG_ID algHash;  
    FILETIME ftTimestamp  
    PCCERT_CHAIN_CONTEXT pChainContext;  
} AXL_AUTHENTICODE_TIMESTAMPER_INFO, * PAXL_AUTHENTICODE_TIMESTAMPER_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="89401-105">成员</span><span class="sxs-lookup"><span data-stu-id="89401-105">Members</span></span>  
  
|<span data-ttu-id="89401-106">成员</span><span class="sxs-lookup"><span data-stu-id="89401-106">Member</span></span>|<span data-ttu-id="89401-107">描述</span><span class="sxs-lookup"><span data-stu-id="89401-107">Description</span></span>|  
|------------|-----------------|  
|`cbSize`|<span data-ttu-id="89401-108">此结构的大小。</span><span class="sxs-lookup"><span data-stu-id="89401-108">The size of this structure.</span></span>|  
|`dwError`|<span data-ttu-id="89401-109">错误代码。</span><span class="sxs-lookup"><span data-stu-id="89401-109">The error code.</span></span>|  
|`algHash`|<span data-ttu-id="89401-110">哈希算法。</span><span class="sxs-lookup"><span data-stu-id="89401-110">The hash algorithm.</span></span>|  
|`ftTimestamp`|<span data-ttu-id="89401-111">时间戳的时间。</span><span class="sxs-lookup"><span data-stu-id="89401-111">The time of the time stamp.</span></span>|  
|`pChainContext`|<span data-ttu-id="89401-112">时间戳签署人的链上下文。</span><span class="sxs-lookup"><span data-stu-id="89401-112">The time stamper’s chain context.</span></span>  <span data-ttu-id="89401-113">请参阅[CERT_CONTEXT](http://msdn.microsoft.com/library/windows/desktop/aa377189.aspx)结构。</span><span class="sxs-lookup"><span data-stu-id="89401-113">See the [CERT_CONTEXT](http://msdn.microsoft.com/library/windows/desktop/aa377189.aspx) structure.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="89401-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="89401-114">See Also</span></span>  
 [<span data-ttu-id="89401-115">验证码</span><span class="sxs-lookup"><span data-stu-id="89401-115">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
