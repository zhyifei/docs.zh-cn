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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c9f58e66286f5e3e169507efd2f87ce10e9d323b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67754852"
---
# <a name="icordebugframegetstackrange-method"></a><span data-ttu-id="37a89-102">ICorDebugFrame::GetStackRange 方法</span><span class="sxs-lookup"><span data-stu-id="37a89-102">ICorDebugFrame::GetStackRange Method</span></span>
<span data-ttu-id="37a89-103">获取此堆栈帧的绝对地址范围。</span><span class="sxs-lookup"><span data-stu-id="37a89-103">Gets the absolute address range of this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37a89-104">语法</span><span class="sxs-lookup"><span data-stu-id="37a89-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStackRange (  
    [out] CORDB_ADDRESS      *pStart,   
    [out] CORDB_ADDRESS      *pEnd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="37a89-105">参数</span><span class="sxs-lookup"><span data-stu-id="37a89-105">Parameters</span></span>  
 `pStart`  
 <span data-ttu-id="37a89-106">[out]一个指向`CORDB_ADDRESS`，它指定表示此堆栈帧的起始地址`ICorDebugFrame`对象。</span><span class="sxs-lookup"><span data-stu-id="37a89-106">[out] A pointer to a `CORDB_ADDRESS` that specifies the starting address of the stack frame represented by this `ICorDebugFrame` object.</span></span>  
  
 `pEnd`  
 <span data-ttu-id="37a89-107">[out]一个指向`CORDB_ADDRESS`，它指定表示此堆栈帧的结束地址`ICorDebugFrame`对象。</span><span class="sxs-lookup"><span data-stu-id="37a89-107">[out] A pointer to a `CORDB_ADDRESS` that specifies the ending address of the stack frame represented by this `ICorDebugFrame` object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="37a89-108">备注</span><span class="sxs-lookup"><span data-stu-id="37a89-108">Remarks</span></span>  
 <span data-ttu-id="37a89-109">在堆栈的地址范围可用于拼凑从多个调试引擎中收集的交错的堆栈跟踪。</span><span class="sxs-lookup"><span data-stu-id="37a89-109">The address range of the stack is useful for piecing together interleaved stack traces gathered from multiple debugging engines.</span></span> <span data-ttu-id="37a89-110">数值范围提供内容的堆栈帧的任何信息。</span><span class="sxs-lookup"><span data-stu-id="37a89-110">The numeric range provides no information about the contents of the stack frame.</span></span> <span data-ttu-id="37a89-111">它是仅对的堆栈帧位置比较有意义。</span><span class="sxs-lookup"><span data-stu-id="37a89-111">It is meaningful only for comparison of stack frame locations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="37a89-112">要求</span><span class="sxs-lookup"><span data-stu-id="37a89-112">Requirements</span></span>  
 <span data-ttu-id="37a89-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="37a89-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="37a89-114">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="37a89-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="37a89-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="37a89-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="37a89-116">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="37a89-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
