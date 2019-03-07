---
title: CertFreeAuthenticodeSignerInfo 函数
ms.date: 03/30/2017
api_name:
- CertFreeAuthenticodeSignerInfo
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: 8029633c-b6e4-4665-a7c2-89607c3247ef
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cbed2ece8b10c6385341c0af44a81dfa16b6f60c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57497478"
---
# <a name="certfreeauthenticodesignerinfo-function"></a><span data-ttu-id="111ef-102">CertFreeAuthenticodeSignerInfo 函数</span><span class="sxs-lookup"><span data-stu-id="111ef-102">CertFreeAuthenticodeSignerInfo Function</span></span>
<span data-ttu-id="111ef-103">为分配的资源将释放[AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md)结构。</span><span class="sxs-lookup"><span data-stu-id="111ef-103">Frees resources allocated for the [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="111ef-104">语法</span><span class="sxs-lookup"><span data-stu-id="111ef-104">Syntax</span></span>  
  
```  
HRESULT CertFreeAuthenticodeSignerInfo (  
    [in, out]  PAXL_AUTHENTICODE_SIGNER_INFO   pSignerInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="111ef-105">参数</span><span class="sxs-lookup"><span data-stu-id="111ef-105">Parameters</span></span>  
 `pSignerInfo`  
 <span data-ttu-id="111ef-106">[in, out] 要释放的签署人信息。</span><span class="sxs-lookup"><span data-stu-id="111ef-106">[in, out] Signer information to be released.</span></span> <span data-ttu-id="111ef-107">请参阅[AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md)结构。</span><span class="sxs-lookup"><span data-stu-id="111ef-107">See the [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md) structure.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="111ef-108">返回值</span><span class="sxs-lookup"><span data-stu-id="111ef-108">Return Value</span></span>  
 <span data-ttu-id="111ef-109">如果此函数成功，则返回 `S_OK`。</span><span class="sxs-lookup"><span data-stu-id="111ef-109">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="111ef-110">否则，返回错误代码。</span><span class="sxs-lookup"><span data-stu-id="111ef-110">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="111ef-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="111ef-111">See also</span></span>
- [<span data-ttu-id="111ef-112">验证码</span><span class="sxs-lookup"><span data-stu-id="111ef-112">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
