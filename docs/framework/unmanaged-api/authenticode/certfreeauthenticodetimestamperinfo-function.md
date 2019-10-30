---
title: CertFreeAuthenticodeTimestamperInfo 函数
ms.date: 03/30/2017
api_name:
- CertFreeAuthenticodeTimestamperInfo
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: 3eb14c49-68c2-4516-ac89-e5bd7473831c
ms.openlocfilehash: 4f0806e0273b111e3398fb8f2884231b96cf1116
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73099775"
---
# <a name="certfreeauthenticodetimestamperinfo-function"></a><span data-ttu-id="3fc6c-102">CertFreeAuthenticodeTimestamperInfo 函数</span><span class="sxs-lookup"><span data-stu-id="3fc6c-102">CertFreeAuthenticodeTimestamperInfo Function</span></span>
<span data-ttu-id="3fc6c-103">释放为[AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md)结构分配的资源。</span><span class="sxs-lookup"><span data-stu-id="3fc6c-103">Frees resources allocated for the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3fc6c-104">语法</span><span class="sxs-lookup"><span data-stu-id="3fc6c-104">Syntax</span></span>  
  
```cpp  
HRESULT CertFreeAuthenticodeTimestamperInfo (  
    [in, out]  PAXL_AUTHENTICODE_TIMESTAMPER_INFO   pTimestamperInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3fc6c-105">参数</span><span class="sxs-lookup"><span data-stu-id="3fc6c-105">Parameters</span></span>  
 `pTimestamperInfo`  
 <span data-ttu-id="3fc6c-106">[in, out] 要释放的时间戳签署人的信息。</span><span class="sxs-lookup"><span data-stu-id="3fc6c-106">[in, out] The time stamper information to be released.</span></span> <span data-ttu-id="3fc6c-107">请参阅[AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md)结构。</span><span class="sxs-lookup"><span data-stu-id="3fc6c-107">See the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md) structure.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3fc6c-108">返回值</span><span class="sxs-lookup"><span data-stu-id="3fc6c-108">Return Value</span></span>  
 <span data-ttu-id="3fc6c-109">如果此函数成功，则返回 `S_OK`。</span><span class="sxs-lookup"><span data-stu-id="3fc6c-109">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="3fc6c-110">否则，返回错误代码。</span><span class="sxs-lookup"><span data-stu-id="3fc6c-110">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fc6c-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="3fc6c-111">See also</span></span>

- [<span data-ttu-id="3fc6c-112">验证码</span><span class="sxs-lookup"><span data-stu-id="3fc6c-112">Authenticode</span></span>](index.md)
