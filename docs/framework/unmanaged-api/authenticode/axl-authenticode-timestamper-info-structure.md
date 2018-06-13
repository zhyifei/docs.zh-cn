---
title: AXL_AUTHENTICODE_TIMESTAMPER_INFO 结构
ms.date: 03/30/2017
ms.assetid: 89e41a81-0f41-45ad-8f20-a120e4ff24fb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c89845008307e4cfb00d0f9b9a168a43ba5378c0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402358"
---
# <a name="axlauthenticodetimestamperinfo-structure"></a><span data-ttu-id="656bd-102">AXL_AUTHENTICODE_TIMESTAMPER_INFO 结构</span><span class="sxs-lookup"><span data-stu-id="656bd-102">AXL_AUTHENTICODE_TIMESTAMPER_INFO Structure</span></span>
<span data-ttu-id="656bd-103">定义验证码时间戳签署人的信息。</span><span class="sxs-lookup"><span data-stu-id="656bd-103">Defines the Authenticode time stamper information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="656bd-104">语法</span><span class="sxs-lookup"><span data-stu-id="656bd-104">Syntax</span></span>  
  
```  
typedef struct _AXL_AUTHENTICODE_SIGNER_INFO {  
    DWORD cbSize;  
    HRESULT dwError;  
    ALG_ID algHash;  
    FILETIME ftTimestamp  
    PCCERT_CHAIN_CONTEXT pChainContext;  
} AXL_AUTHENTICODE_TIMESTAMPER_INFO, * PAXL_AUTHENTICODE_TIMESTAMPER_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="656bd-105">成员</span><span class="sxs-lookup"><span data-stu-id="656bd-105">Members</span></span>  
  
|<span data-ttu-id="656bd-106">成员</span><span class="sxs-lookup"><span data-stu-id="656bd-106">Member</span></span>|<span data-ttu-id="656bd-107">描述</span><span class="sxs-lookup"><span data-stu-id="656bd-107">Description</span></span>|  
|------------|-----------------|  
|`cbSize`|<span data-ttu-id="656bd-108">此结构的大小。</span><span class="sxs-lookup"><span data-stu-id="656bd-108">The size of this structure.</span></span>|  
|`dwError`|<span data-ttu-id="656bd-109">错误代码。</span><span class="sxs-lookup"><span data-stu-id="656bd-109">The error code.</span></span>|  
|`algHash`|<span data-ttu-id="656bd-110">哈希算法。</span><span class="sxs-lookup"><span data-stu-id="656bd-110">The hash algorithm.</span></span>|  
|`ftTimestamp`|<span data-ttu-id="656bd-111">时间戳的时间。</span><span class="sxs-lookup"><span data-stu-id="656bd-111">The time of the time stamp.</span></span>|  
|`pChainContext`|<span data-ttu-id="656bd-112">时间戳签署人的链上下文。</span><span class="sxs-lookup"><span data-stu-id="656bd-112">The time stamper’s chain context.</span></span>  <span data-ttu-id="656bd-113">请参阅[CERT_CONTEXT](http://msdn.microsoft.com/library/windows/desktop/aa377189.aspx)结构。</span><span class="sxs-lookup"><span data-stu-id="656bd-113">See the [CERT_CONTEXT](http://msdn.microsoft.com/library/windows/desktop/aa377189.aspx) structure.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="656bd-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="656bd-114">See Also</span></span>  
 [<span data-ttu-id="656bd-115">验证码</span><span class="sxs-lookup"><span data-stu-id="656bd-115">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
