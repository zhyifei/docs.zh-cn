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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c5e8dd4a9dbf301b0910eda220513e9a3ffdc1cb
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778636"
---
# <a name="getidentityauthority-function"></a><span data-ttu-id="35cbc-102">GetIdentityAuthority 函数</span><span class="sxs-lookup"><span data-stu-id="35cbc-102">GetIdentityAuthority Function</span></span>
<span data-ttu-id="35cbc-103">获取一个指向[IIdentityAuthority](../../../../docs/framework/unmanaged-api/fusion/iidentityauthority-interface.md)管理密钥的代码对象的实例。</span><span class="sxs-lookup"><span data-stu-id="35cbc-103">Gets a pointer to an [IIdentityAuthority](../../../../docs/framework/unmanaged-api/fusion/iidentityauthority-interface.md) instance that manages keys for code objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35cbc-104">语法</span><span class="sxs-lookup"><span data-stu-id="35cbc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetIdentityAuthority (  
    [out] IIdentityAuthority   **ppIIdentityAuthority  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="35cbc-105">参数</span><span class="sxs-lookup"><span data-stu-id="35cbc-105">Parameters</span></span>  
 `ppIIdentityAuthority`  
 <span data-ttu-id="35cbc-106">[out]返回`IIdentityAuthority`指针。</span><span class="sxs-lookup"><span data-stu-id="35cbc-106">[out] The returned `IIdentityAuthority` pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="35cbc-107">要求</span><span class="sxs-lookup"><span data-stu-id="35cbc-107">Requirements</span></span>  
 <span data-ttu-id="35cbc-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="35cbc-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35cbc-109">**标头：** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="35cbc-109">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="35cbc-110">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35cbc-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35cbc-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="35cbc-111">See also</span></span>

- [<span data-ttu-id="35cbc-112">IIdentityAuthority 接口</span><span class="sxs-lookup"><span data-stu-id="35cbc-112">IIdentityAuthority Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iidentityauthority-interface.md)
- [<span data-ttu-id="35cbc-113">合成全局静态函数</span><span class="sxs-lookup"><span data-stu-id="35cbc-113">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
