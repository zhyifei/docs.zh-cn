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
ms.openlocfilehash: b00afc900a27aea94389ee81065ea22ae359440d
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57498336"
---
# <a name="icordebugappdomainenumeratebreakpoints-method"></a><span data-ttu-id="4c1d9-102">ICorDebugAppDomain::EnumerateBreakpoints 方法</span><span class="sxs-lookup"><span data-stu-id="4c1d9-102">ICorDebugAppDomain::EnumerateBreakpoints Method</span></span>
<span data-ttu-id="4c1d9-103">获取应用程序域中所有活动断点的枚举数。</span><span class="sxs-lookup"><span data-stu-id="4c1d9-103">Gets an enumerator for all active breakpoints in the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c1d9-104">语法</span><span class="sxs-lookup"><span data-stu-id="4c1d9-104">Syntax</span></span>  
  
```  
HRESULT EnumerateBreakpoints (  
    [out] ICorDebugBreakpointEnum   **ppBreakpoints  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4c1d9-105">参数</span><span class="sxs-lookup"><span data-stu-id="4c1d9-105">Parameters</span></span>  
 `ppBreakpoints`  
 <span data-ttu-id="4c1d9-106">[out]指向一个 ICorDebugBreakpointEnum 对象，它的应用程序域中的所有活动断点的枚举器的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="4c1d9-106">[out] A pointer to the address of an ICorDebugBreakpointEnum object that is the enumerator for all active breakpoints in the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4c1d9-107">备注</span><span class="sxs-lookup"><span data-stu-id="4c1d9-107">Remarks</span></span>  
 <span data-ttu-id="4c1d9-108">枚举器包括所有类型的断点，包括函数断点和数据断点。</span><span class="sxs-lookup"><span data-stu-id="4c1d9-108">The enumerator includes all types of breakpoints, including function breakpoints and data breakpoints.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4c1d9-109">要求</span><span class="sxs-lookup"><span data-stu-id="4c1d9-109">Requirements</span></span>  
 <span data-ttu-id="4c1d9-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4c1d9-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4c1d9-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4c1d9-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4c1d9-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4c1d9-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4c1d9-113">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4c1d9-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
