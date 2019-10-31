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
ms.openlocfilehash: 3611684a17d51fc4fdba31dd4049540039b43e8b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73110519"
---
# <a name="icordebugappdomainenumeratebreakpoints-method"></a><span data-ttu-id="8b1c6-102">ICorDebugAppDomain::EnumerateBreakpoints 方法</span><span class="sxs-lookup"><span data-stu-id="8b1c6-102">ICorDebugAppDomain::EnumerateBreakpoints Method</span></span>
<span data-ttu-id="8b1c6-103">获取应用程序域中所有活动断点的枚举器。</span><span class="sxs-lookup"><span data-stu-id="8b1c6-103">Gets an enumerator for all active breakpoints in the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b1c6-104">语法</span><span class="sxs-lookup"><span data-stu-id="8b1c6-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateBreakpoints (  
    [out] ICorDebugBreakpointEnum   **ppBreakpoints  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8b1c6-105">参数</span><span class="sxs-lookup"><span data-stu-id="8b1c6-105">Parameters</span></span>  
 `ppBreakpoints`  
 <span data-ttu-id="8b1c6-106">弄指向 ICorDebugBreakpointEnum 对象地址的指针，该对象是应用程序域中所有活动断点的枚举器。</span><span class="sxs-lookup"><span data-stu-id="8b1c6-106">[out] A pointer to the address of an ICorDebugBreakpointEnum object that is the enumerator for all active breakpoints in the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8b1c6-107">备注</span><span class="sxs-lookup"><span data-stu-id="8b1c6-107">Remarks</span></span>  
 <span data-ttu-id="8b1c6-108">枚举器包含所有类型的断点，包括函数断点和数据断点。</span><span class="sxs-lookup"><span data-stu-id="8b1c6-108">The enumerator includes all types of breakpoints, including function breakpoints and data breakpoints.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8b1c6-109">要求</span><span class="sxs-lookup"><span data-stu-id="8b1c6-109">Requirements</span></span>  
 <span data-ttu-id="8b1c6-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8b1c6-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b1c6-111">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8b1c6-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8b1c6-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8b1c6-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8b1c6-113">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8b1c6-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
