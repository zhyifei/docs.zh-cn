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
ms.openlocfilehash: cacdccf5c27cd1d115134d49e754b4ace2870b72
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83205164"
---
# <a name="icordebugframegetstackrange-method"></a><span data-ttu-id="f1fe6-102">ICorDebugFrame::GetStackRange 方法</span><span class="sxs-lookup"><span data-stu-id="f1fe6-102">ICorDebugFrame::GetStackRange Method</span></span>
<span data-ttu-id="f1fe6-103">获取此堆栈帧的绝对地址范围。</span><span class="sxs-lookup"><span data-stu-id="f1fe6-103">Gets the absolute address range of this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1fe6-104">语法</span><span class="sxs-lookup"><span data-stu-id="f1fe6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStackRange (  
    [out] CORDB_ADDRESS      *pStart,
    [out] CORDB_ADDRESS      *pEnd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f1fe6-105">参数</span><span class="sxs-lookup"><span data-stu-id="f1fe6-105">Parameters</span></span>  
 `pStart`  
 <span data-ttu-id="f1fe6-106">弄指向的指针 `CORDB_ADDRESS` ，它指定此对象表示的堆栈帧的起始地址 `ICorDebugFrame` 。</span><span class="sxs-lookup"><span data-stu-id="f1fe6-106">[out] A pointer to a `CORDB_ADDRESS` that specifies the starting address of the stack frame represented by this `ICorDebugFrame` object.</span></span>  
  
 `pEnd`  
 <span data-ttu-id="f1fe6-107">弄指向的指针 `CORDB_ADDRESS` ，它指定此对象表示的堆栈帧的结束地址 `ICorDebugFrame` 。</span><span class="sxs-lookup"><span data-stu-id="f1fe6-107">[out] A pointer to a `CORDB_ADDRESS` that specifies the ending address of the stack frame represented by this `ICorDebugFrame` object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f1fe6-108">备注</span><span class="sxs-lookup"><span data-stu-id="f1fe6-108">Remarks</span></span>  
 <span data-ttu-id="f1fe6-109">堆栈的地址范围可用于拼凑将从多个调试引擎中收集的交错堆栈跟踪组合在一起。</span><span class="sxs-lookup"><span data-stu-id="f1fe6-109">The address range of the stack is useful for piecing together interleaved stack traces gathered from multiple debugging engines.</span></span> <span data-ttu-id="f1fe6-110">数值范围不提供有关堆栈帧内容的信息。</span><span class="sxs-lookup"><span data-stu-id="f1fe6-110">The numeric range provides no information about the contents of the stack frame.</span></span> <span data-ttu-id="f1fe6-111">它仅用于比较堆栈帧位置。</span><span class="sxs-lookup"><span data-stu-id="f1fe6-111">It is meaningful only for comparison of stack frame locations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1fe6-112">要求</span><span class="sxs-lookup"><span data-stu-id="f1fe6-112">Requirements</span></span>  
 <span data-ttu-id="f1fe6-113">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f1fe6-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1fe6-114">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f1fe6-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f1fe6-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f1fe6-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f1fe6-116">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1fe6-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
