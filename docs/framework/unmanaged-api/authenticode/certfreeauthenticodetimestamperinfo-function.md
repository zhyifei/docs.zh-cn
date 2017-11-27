---
title: "CertFreeAuthenticodeTimestamperInfo 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CertFreeAuthenticodeTimestamperInfo
api_location: clr.dll
api_type: DLLExport
ms.assetid: 3eb14c49-68c2-4516-ac89-e5bd7473831c
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b8b6392e57e641d25d07580fcb6bf630f8d983be
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="certfreeauthenticodetimestamperinfo-function"></a><span data-ttu-id="7e2cc-102">CertFreeAuthenticodeTimestamperInfo 函数</span><span class="sxs-lookup"><span data-stu-id="7e2cc-102">CertFreeAuthenticodeTimestamperInfo Function</span></span>
<span data-ttu-id="7e2cc-103">释放为分配的资源[AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md)结构。</span><span class="sxs-lookup"><span data-stu-id="7e2cc-103">Frees resources allocated for the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e2cc-104">语法</span><span class="sxs-lookup"><span data-stu-id="7e2cc-104">Syntax</span></span>  
  
```  
HRESULT CertFreeAuthenticodeTimestamperInfo (  
    [in, out]  PAXL_AUTHENTICODE_TIMESTAMPER_INFO   pTimestamperInfo  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7e2cc-105">参数</span><span class="sxs-lookup"><span data-stu-id="7e2cc-105">Parameters</span></span>  
 `pTimestamperInfo`  
 <span data-ttu-id="7e2cc-106">[in, out] 要释放的时间戳签署人的信息。</span><span class="sxs-lookup"><span data-stu-id="7e2cc-106">[in, out] The time stamper information to be released.</span></span> <span data-ttu-id="7e2cc-107">请参阅[AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md)结构。</span><span class="sxs-lookup"><span data-stu-id="7e2cc-107">See the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) structure.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7e2cc-108">返回值</span><span class="sxs-lookup"><span data-stu-id="7e2cc-108">Return Value</span></span>  
 <span data-ttu-id="7e2cc-109">如果此函数成功，则返回 `S_OK`。</span><span class="sxs-lookup"><span data-stu-id="7e2cc-109">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="7e2cc-110">否则，返回错误代码。</span><span class="sxs-lookup"><span data-stu-id="7e2cc-110">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e2cc-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7e2cc-111">See Also</span></span>  
 [<span data-ttu-id="7e2cc-112">验证码</span><span class="sxs-lookup"><span data-stu-id="7e2cc-112">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
