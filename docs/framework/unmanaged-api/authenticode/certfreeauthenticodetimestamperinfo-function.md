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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 27c16cb5d85ddffc1646bee893c5644682812025
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54560576"
---
# <a name="certfreeauthenticodetimestamperinfo-function"></a><span data-ttu-id="03974-102">CertFreeAuthenticodeTimestamperInfo 函数</span><span class="sxs-lookup"><span data-stu-id="03974-102">CertFreeAuthenticodeTimestamperInfo Function</span></span>
<span data-ttu-id="03974-103">为分配的资源将释放[AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md)结构。</span><span class="sxs-lookup"><span data-stu-id="03974-103">Frees resources allocated for the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03974-104">语法</span><span class="sxs-lookup"><span data-stu-id="03974-104">Syntax</span></span>  
  
```  
HRESULT CertFreeAuthenticodeTimestamperInfo (  
    [in, out]  PAXL_AUTHENTICODE_TIMESTAMPER_INFO   pTimestamperInfo  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="03974-105">参数</span><span class="sxs-lookup"><span data-stu-id="03974-105">Parameters</span></span>  
 `pTimestamperInfo`  
 <span data-ttu-id="03974-106">[in, out] 要释放的时间戳签署人的信息。</span><span class="sxs-lookup"><span data-stu-id="03974-106">[in, out] The time stamper information to be released.</span></span> <span data-ttu-id="03974-107">请参阅[AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md)结构。</span><span class="sxs-lookup"><span data-stu-id="03974-107">See the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) structure.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="03974-108">返回值</span><span class="sxs-lookup"><span data-stu-id="03974-108">Return Value</span></span>  
 <span data-ttu-id="03974-109">如果此函数成功，则返回 `S_OK`。</span><span class="sxs-lookup"><span data-stu-id="03974-109">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="03974-110">否则，返回错误代码。</span><span class="sxs-lookup"><span data-stu-id="03974-110">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03974-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="03974-111">See also</span></span>
- [<span data-ttu-id="03974-112">验证码</span><span class="sxs-lookup"><span data-stu-id="03974-112">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
