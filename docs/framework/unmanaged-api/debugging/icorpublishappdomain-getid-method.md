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
ms.openlocfilehash: 36c5c674f3cdf867107b9ee85a5befadc9246d78
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396308"
---
# <a name="icorpublishappdomaingetid-method"></a><span data-ttu-id="1e31f-102">ICorPublishAppDomain::GetID 方法</span><span class="sxs-lookup"><span data-stu-id="1e31f-102">ICorPublishAppDomain::GetID Method</span></span>
<span data-ttu-id="1e31f-103">获取此[ICorPublishAppDomain](icorpublishappdomain-interface.md)的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="1e31f-103">Gets the unique identifier for this [ICorPublishAppDomain](icorpublishappdomain-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e31f-104">语法</span><span class="sxs-lookup"><span data-stu-id="1e31f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetID (  
    [out] ULONG32   *puId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1e31f-105">参数</span><span class="sxs-lookup"><span data-stu-id="1e31f-105">Parameters</span></span>  
 `puId`  
 <span data-ttu-id="1e31f-106">弄指向应用程序域的标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="1e31f-106">[out] A pointer to the identifier of the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1e31f-107">备注</span><span class="sxs-lookup"><span data-stu-id="1e31f-107">Remarks</span></span>  
 <span data-ttu-id="1e31f-108">标识符仅在包含进程的范围内是唯一的。</span><span class="sxs-lookup"><span data-stu-id="1e31f-108">The identifier is unique only in the scope of the containing process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1e31f-109">要求</span><span class="sxs-lookup"><span data-stu-id="1e31f-109">Requirements</span></span>  
 <span data-ttu-id="1e31f-110">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1e31f-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1e31f-111">**标头：** CorPub，CorPub</span><span class="sxs-lookup"><span data-stu-id="1e31f-111">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="1e31f-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1e31f-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1e31f-113">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1e31f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e31f-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="1e31f-114">See also</span></span>

- [<span data-ttu-id="1e31f-115">ICorPublishAppDomain 接口</span><span class="sxs-lookup"><span data-stu-id="1e31f-115">ICorPublishAppDomain Interface</span></span>](icorpublishappdomain-interface.md)
