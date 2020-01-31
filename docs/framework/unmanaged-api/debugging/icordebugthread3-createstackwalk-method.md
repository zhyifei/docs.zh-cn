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
ms.openlocfilehash: 64f6bc9abb8105cdfa942c2aaca71994e8a91765
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791417"
---
# <a name="icordebugthread3createstackwalk-method"></a><span data-ttu-id="099d3-102">ICorDebugThread3::CreateStackWalk 方法</span><span class="sxs-lookup"><span data-stu-id="099d3-102">ICorDebugThread3::CreateStackWalk Method</span></span>
<span data-ttu-id="099d3-103">为要展开其堆栈的线程创建[ICorDebugStackWalk](icordebugstackwalk-interface.md)对象。</span><span class="sxs-lookup"><span data-stu-id="099d3-103">Creates an [ICorDebugStackWalk](icordebugstackwalk-interface.md) object for the thread whose stack you want to unwind.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="099d3-104">语法</span><span class="sxs-lookup"><span data-stu-id="099d3-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateStackWalk([out] ICorDebugStackWalk **ppStackWalk);  
```  
  
## <a name="parameters"></a><span data-ttu-id="099d3-105">参数</span><span class="sxs-lookup"><span data-stu-id="099d3-105">Parameters</span></span>  
 `ppStackWalk`  
 <span data-ttu-id="099d3-106">弄指向要展开其堆栈的线程的[ICorDebugStackWalk](icordebugstackwalk-interface.md)对象地址的指针。</span><span class="sxs-lookup"><span data-stu-id="099d3-106">[out] A pointer to address of the [ICorDebugStackWalk](icordebugstackwalk-interface.md) object for the thread whose stack you want to unwind.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="099d3-107">返回值</span><span class="sxs-lookup"><span data-stu-id="099d3-107">Return Value</span></span>  
 <span data-ttu-id="099d3-108">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="099d3-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="099d3-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="099d3-109">HRESULT</span></span>|<span data-ttu-id="099d3-110">描述</span><span class="sxs-lookup"><span data-stu-id="099d3-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="099d3-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="099d3-111">S_OK</span></span>|<span data-ttu-id="099d3-112">已成功创建 `ICorDebugStackWalk` 对象。</span><span class="sxs-lookup"><span data-stu-id="099d3-112">The `ICorDebugStackWalk` object was successfully created.</span></span>|  
|<span data-ttu-id="099d3-113">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="099d3-113">E_FAIL</span></span>|<span data-ttu-id="099d3-114">未创建 `ICorDebugStackWalk` 对象。</span><span class="sxs-lookup"><span data-stu-id="099d3-114">The `ICorDebugStackWalk` object was not created.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="099d3-115">异常</span><span class="sxs-lookup"><span data-stu-id="099d3-115">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="099d3-116">备注</span><span class="sxs-lookup"><span data-stu-id="099d3-116">Remarks</span></span>  
 <span data-ttu-id="099d3-117">如果 `CreateStackWalk` 方法成功，则返回的 `ICorDebugStackWalk` 对象的上下文将设置为线程的当前上下文。</span><span class="sxs-lookup"><span data-stu-id="099d3-117">If the `CreateStackWalk` method succeeds, the returned `ICorDebugStackWalk` object's context is set to the thread's current context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="099d3-118">需求</span><span class="sxs-lookup"><span data-stu-id="099d3-118">Requirements</span></span>  
 <span data-ttu-id="099d3-119">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="099d3-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="099d3-120">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="099d3-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="099d3-121">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="099d3-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="099d3-122">**.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="099d3-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="099d3-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="099d3-123">See also</span></span>

- [<span data-ttu-id="099d3-124">调试接口</span><span class="sxs-lookup"><span data-stu-id="099d3-124">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="099d3-125">调试</span><span class="sxs-lookup"><span data-stu-id="099d3-125">Debugging</span></span>](index.md)
