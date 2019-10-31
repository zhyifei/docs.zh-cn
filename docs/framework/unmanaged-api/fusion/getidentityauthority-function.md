---
title: GetIdentityAuthority 函数
ms.date: 03/30/2017
api_name:
- GetIdentityAuthority
api_location:
- fusion.dll
- clr.dll
api_type:
- COM
f1_keywords:
- GetIdentityAuthority
helpviewer_keywords:
- GetIdentityAuthority function [.NET Framework fusion]
ms.assetid: 843cd5ab-d2b7-4ff6-86bd-e68c7a91c098
topic_type:
- apiref
ms.openlocfilehash: acb80f3cc199d4d9f774cb3898335d26fe44b807
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127143"
---
# <a name="getidentityauthority-function"></a><span data-ttu-id="6aa6c-102">GetIdentityAuthority 函数</span><span class="sxs-lookup"><span data-stu-id="6aa6c-102">GetIdentityAuthority Function</span></span>
<span data-ttu-id="6aa6c-103">获取一个指针，该指针指向管理代码对象的键的[IIdentityAuthority](iidentityauthority-interface.md)实例。</span><span class="sxs-lookup"><span data-stu-id="6aa6c-103">Gets a pointer to an [IIdentityAuthority](iidentityauthority-interface.md) instance that manages keys for code objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6aa6c-104">语法</span><span class="sxs-lookup"><span data-stu-id="6aa6c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetIdentityAuthority (  
    [out] IIdentityAuthority   **ppIIdentityAuthority  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="6aa6c-105">参数</span><span class="sxs-lookup"><span data-stu-id="6aa6c-105">Parameters</span></span>  
 `ppIIdentityAuthority`  
 <span data-ttu-id="6aa6c-106">弄返回的 `IIdentityAuthority` 指针。</span><span class="sxs-lookup"><span data-stu-id="6aa6c-106">[out] The returned `IIdentityAuthority` pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6aa6c-107">要求</span><span class="sxs-lookup"><span data-stu-id="6aa6c-107">Requirements</span></span>  
 <span data-ttu-id="6aa6c-108">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6aa6c-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6aa6c-109">**标头：** 隔离。h</span><span class="sxs-lookup"><span data-stu-id="6aa6c-109">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="6aa6c-110">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6aa6c-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6aa6c-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="6aa6c-111">See also</span></span>

- [<span data-ttu-id="6aa6c-112">IIdentityAuthority 接口</span><span class="sxs-lookup"><span data-stu-id="6aa6c-112">IIdentityAuthority Interface</span></span>](iidentityauthority-interface.md)
- [<span data-ttu-id="6aa6c-113">合成全局静态函数</span><span class="sxs-lookup"><span data-stu-id="6aa6c-113">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
