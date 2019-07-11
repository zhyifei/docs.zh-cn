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
ms.openlocfilehash: 680d9c959c57620ff38f8e785c670b451e5805b0
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67741232"
---
# <a name="certfreeauthenticodetimestamperinfo-function"></a><span data-ttu-id="a7590-102">CertFreeAuthenticodeTimestamperInfo 函数</span><span class="sxs-lookup"><span data-stu-id="a7590-102">CertFreeAuthenticodeTimestamperInfo Function</span></span>
<span data-ttu-id="a7590-103">为分配的资源将释放[AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md)结构。</span><span class="sxs-lookup"><span data-stu-id="a7590-103">Frees resources allocated for the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7590-104">语法</span><span class="sxs-lookup"><span data-stu-id="a7590-104">Syntax</span></span>  
  
```cpp  
HRESULT CertFreeAuthenticodeTimestamperInfo (  
    [in, out]  PAXL_AUTHENTICODE_TIMESTAMPER_INFO   pTimestamperInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a7590-105">参数</span><span class="sxs-lookup"><span data-stu-id="a7590-105">Parameters</span></span>  
 `pTimestamperInfo`  
 <span data-ttu-id="a7590-106">[in, out] 要释放的时间戳签署人的信息。</span><span class="sxs-lookup"><span data-stu-id="a7590-106">[in, out] The time stamper information to be released.</span></span> <span data-ttu-id="a7590-107">请参阅[AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md)结构。</span><span class="sxs-lookup"><span data-stu-id="a7590-107">See the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) structure.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a7590-108">返回值</span><span class="sxs-lookup"><span data-stu-id="a7590-108">Return Value</span></span>  
 <span data-ttu-id="a7590-109">如果此函数成功，则返回 `S_OK`。</span><span class="sxs-lookup"><span data-stu-id="a7590-109">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="a7590-110">否则，返回错误代码。</span><span class="sxs-lookup"><span data-stu-id="a7590-110">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7590-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="a7590-111">See also</span></span>

- [<span data-ttu-id="a7590-112">验证码</span><span class="sxs-lookup"><span data-stu-id="a7590-112">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
