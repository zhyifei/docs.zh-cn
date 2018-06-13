---
title: ICorPublishAppDomain::GetID 方法
ms.date: 03/30/2017
api_name:
- ICorPublishAppDomain.GetID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishAppDomain::GetID
helpviewer_keywords:
- GetID method, ICorPublishAppDomain interface [.NET Framework debugging]
- ICorPublishAppDomain::GetID method [.NET Framework debugging]
ms.assetid: 229437e3-1465-4bd8-8846-9804b2488133
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 41b39597a5a438592d2ae07a16510f5406a91a43
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33422827"
---
# <a name="icorpublishappdomaingetid-method"></a><span data-ttu-id="15937-102">ICorPublishAppDomain::GetID 方法</span><span class="sxs-lookup"><span data-stu-id="15937-102">ICorPublishAppDomain::GetID Method</span></span>
<span data-ttu-id="15937-103">获取此唯一标识符[ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)。</span><span class="sxs-lookup"><span data-stu-id="15937-103">Gets the unique identifier for this [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15937-104">语法</span><span class="sxs-lookup"><span data-stu-id="15937-104">Syntax</span></span>  
  
```  
HRESULT GetID (  
    [out] ULONG32   *puId  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="15937-105">参数</span><span class="sxs-lookup"><span data-stu-id="15937-105">Parameters</span></span>  
 `puId`  
 <span data-ttu-id="15937-106">[out]指向应用程序域的标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="15937-106">[out] A pointer to the identifier of the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="15937-107">备注</span><span class="sxs-lookup"><span data-stu-id="15937-107">Remarks</span></span>  
 <span data-ttu-id="15937-108">仅在包含进程的作用域中的标识符是唯一的。</span><span class="sxs-lookup"><span data-stu-id="15937-108">The identifier is unique only in the scope of the containing process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15937-109">要求</span><span class="sxs-lookup"><span data-stu-id="15937-109">Requirements</span></span>  
 <span data-ttu-id="15937-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="15937-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15937-111">**标头：** CorPub.idl、 CorPub.h</span><span class="sxs-lookup"><span data-stu-id="15937-111">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="15937-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="15937-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="15937-113">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15937-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15937-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="15937-114">See Also</span></span>  
 [<span data-ttu-id="15937-115">ICorPublishAppDomain 接口</span><span class="sxs-lookup"><span data-stu-id="15937-115">ICorPublishAppDomain Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)
