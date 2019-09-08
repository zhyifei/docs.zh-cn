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
ms.openlocfilehash: 357a2ca0ffc733adb14a21624cbe28fb754c8240
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70776728"
---
# <a name="certfreeauthenticodesignerinfo-function"></a><span data-ttu-id="5f82d-102">CertFreeAuthenticodeSignerInfo 函数</span><span class="sxs-lookup"><span data-stu-id="5f82d-102">CertFreeAuthenticodeSignerInfo Function</span></span>
<span data-ttu-id="5f82d-103">释放为[AXL_AUTHENTICODE_SIGNER_INFO](axl-authenticode-signer-info-structure.md)结构分配的资源。</span><span class="sxs-lookup"><span data-stu-id="5f82d-103">Frees resources allocated for the [AXL_AUTHENTICODE_SIGNER_INFO](axl-authenticode-signer-info-structure.md) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f82d-104">语法</span><span class="sxs-lookup"><span data-stu-id="5f82d-104">Syntax</span></span>  
  
```cpp  
HRESULT CertFreeAuthenticodeSignerInfo (  
    [in, out]  PAXL_AUTHENTICODE_SIGNER_INFO   pSignerInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5f82d-105">参数</span><span class="sxs-lookup"><span data-stu-id="5f82d-105">Parameters</span></span>  
 `pSignerInfo`  
 <span data-ttu-id="5f82d-106">[in, out] 要释放的签署人信息。</span><span class="sxs-lookup"><span data-stu-id="5f82d-106">[in, out] Signer information to be released.</span></span> <span data-ttu-id="5f82d-107">请参阅[AXL_AUTHENTICODE_SIGNER_INFO](axl-authenticode-signer-info-structure.md)结构。</span><span class="sxs-lookup"><span data-stu-id="5f82d-107">See the [AXL_AUTHENTICODE_SIGNER_INFO](axl-authenticode-signer-info-structure.md) structure.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5f82d-108">返回值</span><span class="sxs-lookup"><span data-stu-id="5f82d-108">Return Value</span></span>  
 <span data-ttu-id="5f82d-109">如果此函数成功，则返回 `S_OK`。</span><span class="sxs-lookup"><span data-stu-id="5f82d-109">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="5f82d-110">否则，返回错误代码。</span><span class="sxs-lookup"><span data-stu-id="5f82d-110">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f82d-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="5f82d-111">See also</span></span>

- [<span data-ttu-id="5f82d-112">验证码</span><span class="sxs-lookup"><span data-stu-id="5f82d-112">Authenticode</span></span>](index.md)
