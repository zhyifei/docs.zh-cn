---
title: ICorDebugThread3::CreateStackWalk 方法
ms.date: 03/30/2017
api_name:
- ICorDebugThread3.CreateStackWalk Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread3::CreateStackWalk
helpviewer_keywords:
- CreateStackWalk method [.NET Framework debugging]
- ICorDebugThread3::CreateStackWalk method [.NET Framework debugging]
ms.assetid: c55e35d9-f9aa-4268-94b5-dce44c61acf2
topic_type:
- apiref
ms.openlocfilehash: f2850e6c9cbb2250a08ab4a0e34c69e377d3a23d
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "83375854"
---
# <a name="icordebugthread3createstackwalk-method"></a><span data-ttu-id="c8c46-102">ICorDebugThread3::CreateStackWalk 方法</span><span class="sxs-lookup"><span data-stu-id="c8c46-102">ICorDebugThread3::CreateStackWalk Method</span></span>
<span data-ttu-id="c8c46-103">为要展开其堆栈的线程创建[ICorDebugStackWalk](icordebugstackwalk-interface.md)对象。</span><span class="sxs-lookup"><span data-stu-id="c8c46-103">Creates an [ICorDebugStackWalk](icordebugstackwalk-interface.md) object for the thread whose stack you want to unwind.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8c46-104">语法</span><span class="sxs-lookup"><span data-stu-id="c8c46-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateStackWalk([out] ICorDebugStackWalk **ppStackWalk);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c8c46-105">参数</span><span class="sxs-lookup"><span data-stu-id="c8c46-105">Parameters</span></span>  
 `ppStackWalk`  
 <span data-ttu-id="c8c46-106">弄指向要展开其堆栈的线程的[ICorDebugStackWalk](icordebugstackwalk-interface.md)对象地址的指针。</span><span class="sxs-lookup"><span data-stu-id="c8c46-106">[out] A pointer to address of the [ICorDebugStackWalk](icordebugstackwalk-interface.md) object for the thread whose stack you want to unwind.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c8c46-107">返回值</span><span class="sxs-lookup"><span data-stu-id="c8c46-107">Return Value</span></span>  
 <span data-ttu-id="c8c46-108">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="c8c46-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="c8c46-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c8c46-109">HRESULT</span></span>|<span data-ttu-id="c8c46-110">描述</span><span class="sxs-lookup"><span data-stu-id="c8c46-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c8c46-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="c8c46-111">S_OK</span></span>|<span data-ttu-id="c8c46-112">已 `ICorDebugStackWalk` 成功创建对象。</span><span class="sxs-lookup"><span data-stu-id="c8c46-112">The `ICorDebugStackWalk` object was successfully created.</span></span>|  
|<span data-ttu-id="c8c46-113">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c8c46-113">E_FAIL</span></span>|<span data-ttu-id="c8c46-114">`ICorDebugStackWalk`未创建对象。</span><span class="sxs-lookup"><span data-stu-id="c8c46-114">The `ICorDebugStackWalk` object was not created.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="c8c46-115">例外</span><span class="sxs-lookup"><span data-stu-id="c8c46-115">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c8c46-116">备注</span><span class="sxs-lookup"><span data-stu-id="c8c46-116">Remarks</span></span>  
 <span data-ttu-id="c8c46-117">如果该 `CreateStackWalk` 方法成功，则返回的 `ICorDebugStackWalk` 对象的上下文将设置为线程的当前上下文。</span><span class="sxs-lookup"><span data-stu-id="c8c46-117">If the `CreateStackWalk` method succeeds, the returned `ICorDebugStackWalk` object's context is set to the thread's current context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8c46-118">要求</span><span class="sxs-lookup"><span data-stu-id="c8c46-118">Requirements</span></span>  
 <span data-ttu-id="c8c46-119">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c8c46-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8c46-120">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c8c46-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c8c46-121">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c8c46-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c8c46-122">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c8c46-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8c46-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="c8c46-123">See also</span></span>

- [<span data-ttu-id="c8c46-124">调试接口</span><span class="sxs-lookup"><span data-stu-id="c8c46-124">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="c8c46-125">调试</span><span class="sxs-lookup"><span data-stu-id="c8c46-125">Debugging</span></span>](index.md)
