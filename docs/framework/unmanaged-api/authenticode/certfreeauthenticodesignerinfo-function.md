---
title: "CertFreeAuthenticodeSignerInfo 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- CertFreeAuthenticodeSignerInfo
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: 8029633c-b6e4-4665-a7c2-89607c3247ef
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f8b38d30a1323d0d44330b8bb9a006c372ea7780
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="certfreeauthenticodesignerinfo-function"></a><span data-ttu-id="1fa0e-102">CertFreeAuthenticodeSignerInfo 函数</span><span class="sxs-lookup"><span data-stu-id="1fa0e-102">CertFreeAuthenticodeSignerInfo Function</span></span>
<span data-ttu-id="1fa0e-103">释放为分配的资源[AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md)结构。</span><span class="sxs-lookup"><span data-stu-id="1fa0e-103">Frees resources allocated for the [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1fa0e-104">语法</span><span class="sxs-lookup"><span data-stu-id="1fa0e-104">Syntax</span></span>  
  
```  
HRESULT CertFreeAuthenticodeSignerInfo (  
    [in, out]  PAXL_AUTHENTICODE_SIGNER_INFO   pSignerInfo);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1fa0e-105">参数</span><span class="sxs-lookup"><span data-stu-id="1fa0e-105">Parameters</span></span>  
 `pSignerInfo`  
 <span data-ttu-id="1fa0e-106">[in, out] 要释放的签署人信息。</span><span class="sxs-lookup"><span data-stu-id="1fa0e-106">[in, out] Signer information to be released.</span></span> <span data-ttu-id="1fa0e-107">请参阅[AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md)结构。</span><span class="sxs-lookup"><span data-stu-id="1fa0e-107">See the [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md) structure.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1fa0e-108">返回值</span><span class="sxs-lookup"><span data-stu-id="1fa0e-108">Return Value</span></span>  
 <span data-ttu-id="1fa0e-109">如果此函数成功，则返回 `S_OK`。</span><span class="sxs-lookup"><span data-stu-id="1fa0e-109">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="1fa0e-110">否则，返回错误代码。</span><span class="sxs-lookup"><span data-stu-id="1fa0e-110">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1fa0e-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="1fa0e-111">See Also</span></span>  
 [<span data-ttu-id="1fa0e-112">验证码</span><span class="sxs-lookup"><span data-stu-id="1fa0e-112">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
