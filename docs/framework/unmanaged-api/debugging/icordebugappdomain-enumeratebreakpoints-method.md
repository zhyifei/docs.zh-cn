---
title: ICorDebugAppDomain::EnumerateBreakpoints 方法
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.EnumerateBreakpoints
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::EnumerateBreakpoints
helpviewer_keywords:
- ICorDebugAppDomain::EnumerateBreakpoints method [.NET Framework debugging]
- EnumerateBreakpoints method [.NET Framework debugging]
ms.assetid: 206069c5-25cb-4794-9d69-67c5aa7ed0af
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a683f1531ed28fbd8ef085414bb7cb365762ffde
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67738037"
---
# <a name="icordebugappdomainenumeratebreakpoints-method"></a><span data-ttu-id="49a34-102">ICorDebugAppDomain::EnumerateBreakpoints 方法</span><span class="sxs-lookup"><span data-stu-id="49a34-102">ICorDebugAppDomain::EnumerateBreakpoints Method</span></span>
<span data-ttu-id="49a34-103">获取应用程序域中所有活动断点的枚举数。</span><span class="sxs-lookup"><span data-stu-id="49a34-103">Gets an enumerator for all active breakpoints in the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49a34-104">语法</span><span class="sxs-lookup"><span data-stu-id="49a34-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateBreakpoints (  
    [out] ICorDebugBreakpointEnum   **ppBreakpoints  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="49a34-105">参数</span><span class="sxs-lookup"><span data-stu-id="49a34-105">Parameters</span></span>  
 `ppBreakpoints`  
 <span data-ttu-id="49a34-106">[out]指向一个 ICorDebugBreakpointEnum 对象，它的应用程序域中的所有活动断点的枚举器的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="49a34-106">[out] A pointer to the address of an ICorDebugBreakpointEnum object that is the enumerator for all active breakpoints in the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="49a34-107">备注</span><span class="sxs-lookup"><span data-stu-id="49a34-107">Remarks</span></span>  
 <span data-ttu-id="49a34-108">枚举器包括所有类型的断点，包括函数断点和数据断点。</span><span class="sxs-lookup"><span data-stu-id="49a34-108">The enumerator includes all types of breakpoints, including function breakpoints and data breakpoints.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="49a34-109">要求</span><span class="sxs-lookup"><span data-stu-id="49a34-109">Requirements</span></span>  
 <span data-ttu-id="49a34-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="49a34-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49a34-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="49a34-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="49a34-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="49a34-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="49a34-113">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49a34-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
