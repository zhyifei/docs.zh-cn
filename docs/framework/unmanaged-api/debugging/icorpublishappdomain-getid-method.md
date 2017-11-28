---
title: "ICorPublishAppDomain::GetID 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorPublishAppDomain.GetID
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorPublishAppDomain::GetID
helpviewer_keywords:
- GetID method, ICorPublishAppDomain interface [.NET Framework debugging]
- ICorPublishAppDomain::GetID method [.NET Framework debugging]
ms.assetid: 229437e3-1465-4bd8-8846-9804b2488133
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: bfbde806f409f2639b2468e0ba962b1659d1ffc3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icorpublishappdomaingetid-method"></a><span data-ttu-id="38341-102">ICorPublishAppDomain::GetID 方法</span><span class="sxs-lookup"><span data-stu-id="38341-102">ICorPublishAppDomain::GetID Method</span></span>
<span data-ttu-id="38341-103">获取此唯一标识符[ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)。</span><span class="sxs-lookup"><span data-stu-id="38341-103">Gets the unique identifier for this [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38341-104">语法</span><span class="sxs-lookup"><span data-stu-id="38341-104">Syntax</span></span>  
  
```  
HRESULT GetID (  
    [out] ULONG32   *puId  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="38341-105">参数</span><span class="sxs-lookup"><span data-stu-id="38341-105">Parameters</span></span>  
 `puId`  
 <span data-ttu-id="38341-106">[out]指向应用程序域的标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="38341-106">[out] A pointer to the identifier of the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="38341-107">备注</span><span class="sxs-lookup"><span data-stu-id="38341-107">Remarks</span></span>  
 <span data-ttu-id="38341-108">仅在包含进程的作用域中的标识符是唯一的。</span><span class="sxs-lookup"><span data-stu-id="38341-108">The identifier is unique only in the scope of the containing process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="38341-109">要求</span><span class="sxs-lookup"><span data-stu-id="38341-109">Requirements</span></span>  
 <span data-ttu-id="38341-110">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="38341-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38341-111">**标头：** CorPub.idl、 CorPub.h</span><span class="sxs-lookup"><span data-stu-id="38341-111">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="38341-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="38341-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="38341-113">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38341-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38341-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="38341-114">See Also</span></span>  
 [<span data-ttu-id="38341-115">ICorPublishAppDomain 接口</span><span class="sxs-lookup"><span data-stu-id="38341-115">ICorPublishAppDomain Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)
