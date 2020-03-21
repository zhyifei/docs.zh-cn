---
title: ICorDebugFrame::GetStackRange 方法
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetStackRange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetStackRange
helpviewer_keywords:
- GetStackRange method, ICorDebugFrame interface [.NET Framework debugging]
- ICorDebugFrame::GetStackRange method [.NET Framework debugging]
ms.assetid: fab037cb-fda6-40fb-9367-921e435dd5a0
topic_type:
- apiref
ms.openlocfilehash: 7a35ce025360e0ec8b7085d68e54548026b7c7fc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178901"
---
# <a name="icordebugframegetstackrange-method"></a><span data-ttu-id="3cba9-102">ICorDebugFrame::GetStackRange 方法</span><span class="sxs-lookup"><span data-stu-id="3cba9-102">ICorDebugFrame::GetStackRange Method</span></span>
<span data-ttu-id="3cba9-103">获取此堆栈帧的绝对地址范围。</span><span class="sxs-lookup"><span data-stu-id="3cba9-103">Gets the absolute address range of this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3cba9-104">语法</span><span class="sxs-lookup"><span data-stu-id="3cba9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStackRange (  
    [out] CORDB_ADDRESS      *pStart,
    [out] CORDB_ADDRESS      *pEnd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3cba9-105">parameters</span><span class="sxs-lookup"><span data-stu-id="3cba9-105">Parameters</span></span>  
 `pStart`  
 <span data-ttu-id="3cba9-106">[出]指向`CORDB_ADDRESS`指定此`ICorDebugFrame`对象表示的堆栈帧的起始地址的指针。</span><span class="sxs-lookup"><span data-stu-id="3cba9-106">[out] A pointer to a `CORDB_ADDRESS` that specifies the starting address of the stack frame represented by this `ICorDebugFrame` object.</span></span>  
  
 `pEnd`  
 <span data-ttu-id="3cba9-107">[出]指向`CORDB_ADDRESS`指定此`ICorDebugFrame`对象表示的堆栈帧的结束地址的指针。</span><span class="sxs-lookup"><span data-stu-id="3cba9-107">[out] A pointer to a `CORDB_ADDRESS` that specifies the ending address of the stack frame represented by this `ICorDebugFrame` object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3cba9-108">备注</span><span class="sxs-lookup"><span data-stu-id="3cba9-108">Remarks</span></span>  
 <span data-ttu-id="3cba9-109">堆栈的地址范围可用于拼凑从多个调试引擎收集的交错堆栈跟踪。</span><span class="sxs-lookup"><span data-stu-id="3cba9-109">The address range of the stack is useful for piecing together interleaved stack traces gathered from multiple debugging engines.</span></span> <span data-ttu-id="3cba9-110">数值范围不提供有关堆栈帧内容的信息。</span><span class="sxs-lookup"><span data-stu-id="3cba9-110">The numeric range provides no information about the contents of the stack frame.</span></span> <span data-ttu-id="3cba9-111">它仅对堆栈帧位置的比较有意义。</span><span class="sxs-lookup"><span data-stu-id="3cba9-111">It is meaningful only for comparison of stack frame locations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3cba9-112">要求</span><span class="sxs-lookup"><span data-stu-id="3cba9-112">Requirements</span></span>  
 <span data-ttu-id="3cba9-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3cba9-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3cba9-114">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3cba9-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3cba9-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3cba9-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3cba9-116">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3cba9-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
