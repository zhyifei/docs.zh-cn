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
ms.openlocfilehash: a233e0b8d17b9ee61b1991086f794c9fb20f89e1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73099839"
---
# <a name="certfreeauthenticodesignerinfo-function"></a><span data-ttu-id="e6440-102">CertFreeAuthenticodeSignerInfo 函数</span><span class="sxs-lookup"><span data-stu-id="e6440-102">CertFreeAuthenticodeSignerInfo Function</span></span>
<span data-ttu-id="e6440-103">释放为[AXL_AUTHENTICODE_SIGNER_INFO](axl-authenticode-signer-info-structure.md)结构分配的资源。</span><span class="sxs-lookup"><span data-stu-id="e6440-103">Frees resources allocated for the [AXL_AUTHENTICODE_SIGNER_INFO](axl-authenticode-signer-info-structure.md) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6440-104">语法</span><span class="sxs-lookup"><span data-stu-id="e6440-104">Syntax</span></span>  
  
```cpp  
HRESULT CertFreeAuthenticodeSignerInfo (  
    [in, out]  PAXL_AUTHENTICODE_SIGNER_INFO   pSignerInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e6440-105">参数</span><span class="sxs-lookup"><span data-stu-id="e6440-105">Parameters</span></span>  
 `pSignerInfo`  
 <span data-ttu-id="e6440-106">[in, out] 要释放的签署人信息。</span><span class="sxs-lookup"><span data-stu-id="e6440-106">[in, out] Signer information to be released.</span></span> <span data-ttu-id="e6440-107">请参阅[AXL_AUTHENTICODE_SIGNER_INFO](axl-authenticode-signer-info-structure.md)结构。</span><span class="sxs-lookup"><span data-stu-id="e6440-107">See the [AXL_AUTHENTICODE_SIGNER_INFO](axl-authenticode-signer-info-structure.md) structure.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e6440-108">返回值</span><span class="sxs-lookup"><span data-stu-id="e6440-108">Return Value</span></span>  
 <span data-ttu-id="e6440-109">如果此函数成功，则返回 `S_OK`。</span><span class="sxs-lookup"><span data-stu-id="e6440-109">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="e6440-110">否则，返回错误代码。</span><span class="sxs-lookup"><span data-stu-id="e6440-110">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6440-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="e6440-111">See also</span></span>

- [<span data-ttu-id="e6440-112">验证码</span><span class="sxs-lookup"><span data-stu-id="e6440-112">Authenticode</span></span>](index.md)
