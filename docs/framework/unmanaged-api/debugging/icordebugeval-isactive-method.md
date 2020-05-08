---
title: ICorDebugEval::IsActive 方法
ms.date: 03/30/2017
api_name:
- ICorDebugEval.IsActive
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::IsActive
helpviewer_keywords:
- IsActive method, ICorDebugEval interface [.NET Framework debugging]
- ICorDebugEval::IsActive method [.NET Framework debugging]
ms.assetid: bf2bba24-d278-43bd-b1c5-35680e748d3e
topic_type:
- apiref
ms.openlocfilehash: 4ee055812eb8dce2dc86f834dde92d7de5e1fdf9
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976208"
---
# <a name="icordebugevalisactive-method"></a><span data-ttu-id="e1905-102">ICorDebugEval::IsActive 方法</span><span class="sxs-lookup"><span data-stu-id="e1905-102">ICorDebugEval::IsActive Method</span></span>
<span data-ttu-id="e1905-103">获取一个值，该值指示此 ICorDebugEval 对象当前是否正在执行。</span><span class="sxs-lookup"><span data-stu-id="e1905-103">Gets a value that indicates whether this ICorDebugEval object is currently executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1905-104">语法</span><span class="sxs-lookup"><span data-stu-id="e1905-104">Syntax</span></span>  
  
```cpp  
HRESULT IsActive (  
    [out] BOOL              *pbActive  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e1905-105">参数</span><span class="sxs-lookup"><span data-stu-id="e1905-105">Parameters</span></span>  
 `pbActive`  
 <span data-ttu-id="e1905-106">弄指向一个值的指针，该值指示此计算是否处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="e1905-106">[out] Pointer to a value that indicates whether this evaluation is active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e1905-107">要求</span><span class="sxs-lookup"><span data-stu-id="e1905-107">Requirements</span></span>  
 <span data-ttu-id="e1905-108">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e1905-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1905-109">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e1905-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e1905-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e1905-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e1905-111">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1905-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
