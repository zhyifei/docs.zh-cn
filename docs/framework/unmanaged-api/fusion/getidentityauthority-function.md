---
title: "GetIdentityAuthority 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: GetIdentityAuthority
api_location:
- fusion.dll
- clr.dll
api_type: COM
f1_keywords: GetIdentityAuthority
helpviewer_keywords: GetIdentityAuthority function [.NET Framework fusion]
ms.assetid: 843cd5ab-d2b7-4ff6-86bd-e68c7a91c098
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1490efdc00c4f928d17bf172eecd5a3bed824193
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="getidentityauthority-function"></a><span data-ttu-id="53b17-102">GetIdentityAuthority 函数</span><span class="sxs-lookup"><span data-stu-id="53b17-102">GetIdentityAuthority Function</span></span>
<span data-ttu-id="53b17-103">获取一个指向[IIdentityAuthority](../../../../docs/framework/unmanaged-api/fusion/iidentityauthority-interface.md)管理代码对象的键的实例。</span><span class="sxs-lookup"><span data-stu-id="53b17-103">Gets a pointer to an [IIdentityAuthority](../../../../docs/framework/unmanaged-api/fusion/iidentityauthority-interface.md) instance that manages keys for code objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53b17-104">语法</span><span class="sxs-lookup"><span data-stu-id="53b17-104">Syntax</span></span>  
  
```  
HRESULT GetIdentityAuthority (  
    [out] IIdentityAuthority   **ppIIdentityAuthority  
 );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="53b17-105">参数</span><span class="sxs-lookup"><span data-stu-id="53b17-105">Parameters</span></span>  
 `ppIIdentityAuthority`  
 <span data-ttu-id="53b17-106">[out]返回`IIdentityAuthority`指针。</span><span class="sxs-lookup"><span data-stu-id="53b17-106">[out] The returned `IIdentityAuthority` pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="53b17-107">要求</span><span class="sxs-lookup"><span data-stu-id="53b17-107">Requirements</span></span>  
 <span data-ttu-id="53b17-108">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="53b17-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="53b17-109">**标头：** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="53b17-109">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="53b17-110">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="53b17-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53b17-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="53b17-111">See Also</span></span>  
 [<span data-ttu-id="53b17-112">IIdentityAuthority 接口</span><span class="sxs-lookup"><span data-stu-id="53b17-112">IIdentityAuthority Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iidentityauthority-interface.md)  
 [<span data-ttu-id="53b17-113">合成全局静态函数</span><span class="sxs-lookup"><span data-stu-id="53b17-113">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
