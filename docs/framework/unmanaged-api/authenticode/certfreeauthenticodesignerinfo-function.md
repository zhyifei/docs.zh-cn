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
ms.openlocfilehash: 42f5685a9a976be7a3a73badf286f77216e43106
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67741241"
---
# <a name="certfreeauthenticodesignerinfo-function"></a><span data-ttu-id="aee77-102">CertFreeAuthenticodeSignerInfo 函数</span><span class="sxs-lookup"><span data-stu-id="aee77-102">CertFreeAuthenticodeSignerInfo Function</span></span>
<span data-ttu-id="aee77-103">为分配的资源将释放[AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md)结构。</span><span class="sxs-lookup"><span data-stu-id="aee77-103">Frees resources allocated for the [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aee77-104">语法</span><span class="sxs-lookup"><span data-stu-id="aee77-104">Syntax</span></span>  
  
```cpp  
HRESULT CertFreeAuthenticodeSignerInfo (  
    [in, out]  PAXL_AUTHENTICODE_SIGNER_INFO   pSignerInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aee77-105">参数</span><span class="sxs-lookup"><span data-stu-id="aee77-105">Parameters</span></span>  
 `pSignerInfo`  
 <span data-ttu-id="aee77-106">[in, out] 要释放的签署人信息。</span><span class="sxs-lookup"><span data-stu-id="aee77-106">[in, out] Signer information to be released.</span></span> <span data-ttu-id="aee77-107">请参阅[AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md)结构。</span><span class="sxs-lookup"><span data-stu-id="aee77-107">See the [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md) structure.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="aee77-108">返回值</span><span class="sxs-lookup"><span data-stu-id="aee77-108">Return Value</span></span>  
 <span data-ttu-id="aee77-109">如果此函数成功，则返回 `S_OK`。</span><span class="sxs-lookup"><span data-stu-id="aee77-109">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="aee77-110">否则，返回错误代码。</span><span class="sxs-lookup"><span data-stu-id="aee77-110">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aee77-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="aee77-111">See also</span></span>

- [<span data-ttu-id="aee77-112">验证码</span><span class="sxs-lookup"><span data-stu-id="aee77-112">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
