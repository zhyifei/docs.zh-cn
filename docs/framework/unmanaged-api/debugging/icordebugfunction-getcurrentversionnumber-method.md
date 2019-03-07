---
title: ICorDebugFunction::GetCurrentVersionNumber 方法
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetCurrentVersionNumber
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetCurrentVersionNumber
helpviewer_keywords:
- GetCurrentVersionNumber method [.NET Framework debugging]
- ICorDebugFunction::GetCurrentVersionNumber method [.NET Framework debugging]
ms.assetid: c3af1575-cbe6-457a-bc08-c53460edcbc8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ea615eacb30fd4e7a0fd7d730094c2ab4f9dc285
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57478474"
---
# <a name="icordebugfunctiongetcurrentversionnumber-method"></a><span data-ttu-id="9f745-102">ICorDebugFunction::GetCurrentVersionNumber 方法</span><span class="sxs-lookup"><span data-stu-id="9f745-102">ICorDebugFunction::GetCurrentVersionNumber Method</span></span>
<span data-ttu-id="9f745-103">获取对此 ICorDebugFunction 对象所表示的函数所做的最新编辑的版本号。</span><span class="sxs-lookup"><span data-stu-id="9f745-103">Gets the version number of the latest edit made to the function represented by this ICorDebugFunction object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f745-104">语法</span><span class="sxs-lookup"><span data-stu-id="9f745-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentVersionNumber (  
    [out] ULONG32 *pnCurrentVersion  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9f745-105">参数</span><span class="sxs-lookup"><span data-stu-id="9f745-105">Parameters</span></span>  
 `pnCurrentVersion`  
 <span data-ttu-id="9f745-106">[out]指向一个整数值，是对此函数所做的最新编辑的版本号的指针。</span><span class="sxs-lookup"><span data-stu-id="9f745-106">[out] A pointer to an integer value that is the version number of the latest edit made to this function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9f745-107">备注</span><span class="sxs-lookup"><span data-stu-id="9f745-107">Remarks</span></span>  
 <span data-ttu-id="9f745-108">对此函数所做的最新编辑的版本号可能大于函数本身的版本号。</span><span class="sxs-lookup"><span data-stu-id="9f745-108">The version number of the latest edit made to this function may be greater than the version number of the function itself.</span></span> <span data-ttu-id="9f745-109">可以使用两种[ICorDebugFunction2::GetVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-getversionnumber-method.md)方法或[icordebugcode:: Getversionnumber](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md)方法来检索该函数的版本号。</span><span class="sxs-lookup"><span data-stu-id="9f745-109">Use either the [ICorDebugFunction2::GetVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-getversionnumber-method.md) method or the [ICorDebugCode::GetVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md) method to retrieve the version number of the function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9f745-110">要求</span><span class="sxs-lookup"><span data-stu-id="9f745-110">Requirements</span></span>  
 <span data-ttu-id="9f745-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9f745-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f745-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9f745-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9f745-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9f745-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9f745-114">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9f745-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
