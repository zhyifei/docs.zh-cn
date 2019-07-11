---
title: GetAppIdAuthority 函数
ms.date: 03/30/2017
api_name:
- GetAppIdAuthority
api_location:
- fusion.dll
- clr.dll
api_type:
- COM
f1_keywords:
- GetAppIdAuthority
helpviewer_keywords:
- GetAppIdAuthority function [.NET Framework fusion]
ms.assetid: 9f968dad-0d09-47fb-bebc-94c39a0d16ad
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 536f3249593333234f7f09921007b483fb80cf79
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778588"
---
# <a name="getappidauthority-function"></a><span data-ttu-id="efbc5-102">GetAppIdAuthority 函数</span><span class="sxs-lookup"><span data-stu-id="efbc5-102">GetAppIdAuthority Function</span></span>
<span data-ttu-id="efbc5-103">获取一个指向[IAppIdAuthority](../../../../docs/framework/unmanaged-api/fusion/iappidauthority-interface.md)管理密钥的应用程序标识和引用的实例。</span><span class="sxs-lookup"><span data-stu-id="efbc5-103">Gets a pointer to an [IAppIdAuthority](../../../../docs/framework/unmanaged-api/fusion/iappidauthority-interface.md) instance that manages keys for application identities and references.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="efbc5-104">语法</span><span class="sxs-lookup"><span data-stu-id="efbc5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAppIdAuthority (  
    [out] IAppIdAuthority **ppIAppIdAuthority  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="efbc5-105">参数</span><span class="sxs-lookup"><span data-stu-id="efbc5-105">Parameters</span></span>  
 `ppIAppIdAuthority`  
 <span data-ttu-id="efbc5-106">[out]返回`IAppIdAuthority`指针。</span><span class="sxs-lookup"><span data-stu-id="efbc5-106">[out] The returned `IAppIdAuthority` pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="efbc5-107">要求</span><span class="sxs-lookup"><span data-stu-id="efbc5-107">Requirements</span></span>  
 <span data-ttu-id="efbc5-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="efbc5-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="efbc5-109">**标头：** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="efbc5-109">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="efbc5-110">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="efbc5-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efbc5-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="efbc5-111">See also</span></span>

- [<span data-ttu-id="efbc5-112">IAppIdAuthority 接口</span><span class="sxs-lookup"><span data-stu-id="efbc5-112">IAppIdAuthority Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iappidauthority-interface.md)
- [<span data-ttu-id="efbc5-113">合成全局静态函数</span><span class="sxs-lookup"><span data-stu-id="efbc5-113">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
