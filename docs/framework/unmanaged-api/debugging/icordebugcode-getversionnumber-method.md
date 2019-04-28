---
title: ICorDebugCode::GetVersionNumber 方法
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetVersionNumber
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetVersionNumber
helpviewer_keywords:
- GetVersionNumber method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetVersionNumber method [.NET Framework debugging]
ms.assetid: c8e02518-679f-4e9f-8a28-ba4a89a3876f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 003b29501e8f22ed9010a9f16a4f7ee67bce03a8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61750132"
---
# <a name="icordebugcodegetversionnumber-method"></a><span data-ttu-id="e35df-102">ICorDebugCode::GetVersionNumber 方法</span><span class="sxs-lookup"><span data-stu-id="e35df-102">ICorDebugCode::GetVersionNumber Method</span></span>
<span data-ttu-id="e35df-103">获取标识此"ICorDebugCode"表示的代码版本的基于 1 的数。</span><span class="sxs-lookup"><span data-stu-id="e35df-103">Gets the one-based number that identifies the version of the code that this "ICorDebugCode" represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e35df-104">语法</span><span class="sxs-lookup"><span data-stu-id="e35df-104">Syntax</span></span>  
  
```  
HRESULT GetVersionNumber (  
    [out] ULONG32    *nVersion  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e35df-105">参数</span><span class="sxs-lookup"><span data-stu-id="e35df-105">Parameters</span></span>  
 `nVersion`  
 <span data-ttu-id="e35df-106">[out]指向代码的版本号的指针。</span><span class="sxs-lookup"><span data-stu-id="e35df-106">[out] A pointer to the version number of the code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e35df-107">备注</span><span class="sxs-lookup"><span data-stu-id="e35df-107">Remarks</span></span>  
 <span data-ttu-id="e35df-108">编辑并继续 (EnC) 操作执行的代码每次都会递增的版本号。</span><span class="sxs-lookup"><span data-stu-id="e35df-108">The version number is incremented each time an edit-and-continue (EnC) operation is performed on the code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e35df-109">要求</span><span class="sxs-lookup"><span data-stu-id="e35df-109">Requirements</span></span>  
 <span data-ttu-id="e35df-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e35df-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e35df-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e35df-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e35df-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e35df-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e35df-113">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e35df-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e35df-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="e35df-114">See also</span></span>
