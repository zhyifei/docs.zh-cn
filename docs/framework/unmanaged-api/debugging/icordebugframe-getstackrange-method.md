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
ms.openlocfilehash: 5da87071bc23ac17a3077049cd77f0fb8611439f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33413015"
---
# <a name="icordebugframegetstackrange-method"></a><span data-ttu-id="84b58-102">ICorDebugFrame::GetStackRange 方法</span><span class="sxs-lookup"><span data-stu-id="84b58-102">ICorDebugFrame::GetStackRange Method</span></span>
<span data-ttu-id="84b58-103">获取此堆栈帧的绝对地址范围。</span><span class="sxs-lookup"><span data-stu-id="84b58-103">Gets the absolute address range of this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84b58-104">语法</span><span class="sxs-lookup"><span data-stu-id="84b58-104">Syntax</span></span>  
  
```  
HRESULT GetStackRange (  
    [out] CORDB_ADDRESS      *pStart,   
    [out] CORDB_ADDRESS      *pEnd  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="84b58-105">参数</span><span class="sxs-lookup"><span data-stu-id="84b58-105">Parameters</span></span>  
 `pStart`  
 <span data-ttu-id="84b58-106">[out]指向的指针`CORDB_ADDRESS`，指定表示此堆栈帧的起始地址`ICorDebugFrame`对象。</span><span class="sxs-lookup"><span data-stu-id="84b58-106">[out] A pointer to a `CORDB_ADDRESS` that specifies the starting address of the stack frame represented by this `ICorDebugFrame` object.</span></span>  
  
 `pEnd`  
 <span data-ttu-id="84b58-107">[out]指向的指针`CORDB_ADDRESS`，指定表示此堆栈帧的结束地址`ICorDebugFrame`对象。</span><span class="sxs-lookup"><span data-stu-id="84b58-107">[out] A pointer to a `CORDB_ADDRESS` that specifies the ending address of the stack frame represented by this `ICorDebugFrame` object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="84b58-108">备注</span><span class="sxs-lookup"><span data-stu-id="84b58-108">Remarks</span></span>  
 <span data-ttu-id="84b58-109">堆栈的地址范围可用于从多个调试引擎中收集的交错的堆栈跟踪进行汇总。</span><span class="sxs-lookup"><span data-stu-id="84b58-109">The address range of the stack is useful for piecing together interleaved stack traces gathered from multiple debugging engines.</span></span> <span data-ttu-id="84b58-110">数值范围提供有关内容的堆栈帧的任何信息。</span><span class="sxs-lookup"><span data-stu-id="84b58-110">The numeric range provides no information about the contents of the stack frame.</span></span> <span data-ttu-id="84b58-111">它是仅对比较的堆栈帧位置有意义。</span><span class="sxs-lookup"><span data-stu-id="84b58-111">It is meaningful only for comparison of stack frame locations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84b58-112">要求</span><span class="sxs-lookup"><span data-stu-id="84b58-112">Requirements</span></span>  
 <span data-ttu-id="84b58-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="84b58-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84b58-114">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="84b58-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="84b58-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="84b58-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="84b58-116">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84b58-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
