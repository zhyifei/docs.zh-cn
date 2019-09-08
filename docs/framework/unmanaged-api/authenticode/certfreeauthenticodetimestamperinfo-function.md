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
ms.openlocfilehash: a8ecada29528b065ddad0abc80a850ee0f347f6b
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787004"
---
# <a name="certfreeauthenticodetimestamperinfo-function"></a><span data-ttu-id="23dfa-102">CertFreeAuthenticodeTimestamperInfo 函数</span><span class="sxs-lookup"><span data-stu-id="23dfa-102">CertFreeAuthenticodeTimestamperInfo Function</span></span>
<span data-ttu-id="23dfa-103">释放为[AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md)结构分配的资源。</span><span class="sxs-lookup"><span data-stu-id="23dfa-103">Frees resources allocated for the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23dfa-104">语法</span><span class="sxs-lookup"><span data-stu-id="23dfa-104">Syntax</span></span>  
  
```cpp  
HRESULT CertFreeAuthenticodeTimestamperInfo (  
    [in, out]  PAXL_AUTHENTICODE_TIMESTAMPER_INFO   pTimestamperInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="23dfa-105">参数</span><span class="sxs-lookup"><span data-stu-id="23dfa-105">Parameters</span></span>  
 `pTimestamperInfo`  
 <span data-ttu-id="23dfa-106">[in, out] 要释放的时间戳签署人的信息。</span><span class="sxs-lookup"><span data-stu-id="23dfa-106">[in, out] The time stamper information to be released.</span></span> <span data-ttu-id="23dfa-107">请参阅[AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md)结构。</span><span class="sxs-lookup"><span data-stu-id="23dfa-107">See the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md) structure.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="23dfa-108">返回值</span><span class="sxs-lookup"><span data-stu-id="23dfa-108">Return Value</span></span>  
 <span data-ttu-id="23dfa-109">如果此函数成功，则返回 `S_OK`。</span><span class="sxs-lookup"><span data-stu-id="23dfa-109">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="23dfa-110">否则，返回错误代码。</span><span class="sxs-lookup"><span data-stu-id="23dfa-110">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23dfa-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="23dfa-111">See also</span></span>

- [<span data-ttu-id="23dfa-112">验证码</span><span class="sxs-lookup"><span data-stu-id="23dfa-112">Authenticode</span></span>](index.md)
