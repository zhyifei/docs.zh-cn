---
title: ICorDebugChain::EnumerateFrames 方法
ms.date: 03/30/2017
api_name:
- ICorDebugChain.EnumerateFrames
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::EnumerateFrames method
helpviewer_keywords:
- EnumerateFrames method [.NET Framework debugging]
- ICorDebugChain::EnumerateFrames method [.NET Framework debugging]
ms.assetid: 9fcefa98-750d-4168-8915-8173a43accf2
topic_type:
- apiref
ms.openlocfilehash: c8a62d8b4a4db0f36d991c32dbfc5bad68780f1b
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894697"
---
# <a name="icordebugchainenumerateframes-method"></a><span data-ttu-id="6b064-102">ICorDebugChain::EnumerateFrames 方法</span><span class="sxs-lookup"><span data-stu-id="6b064-102">ICorDebugChain::EnumerateFrames Method</span></span>
<span data-ttu-id="6b064-103">获取一个枚举数，该枚举数包含链中所有托管堆栈帧（从最新帧开始）。</span><span class="sxs-lookup"><span data-stu-id="6b064-103">Gets an enumerator that contains all the managed stack frames in the chain, starting with the most recent frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b064-104">语法</span><span class="sxs-lookup"><span data-stu-id="6b064-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateFrames (  
    [out] ICorDebugFrameEnum **ppFrames  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6b064-105">参数</span><span class="sxs-lookup"><span data-stu-id="6b064-105">Parameters</span></span>  
 `ppFrames`  
 <span data-ttu-id="6b064-106">弄指向 ICorDebugFrameEnum 对象地址的指针，该对象是堆栈帧的枚举器。</span><span class="sxs-lookup"><span data-stu-id="6b064-106">[out] A pointer to the address of an ICorDebugFrameEnum object that is the enumerator for the stack frames.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6b064-107">备注</span><span class="sxs-lookup"><span data-stu-id="6b064-107">Remarks</span></span>  
 <span data-ttu-id="6b064-108">链表示线程的物理调用堆栈。</span><span class="sxs-lookup"><span data-stu-id="6b064-108">The chain represents the physical call stack for the thread.</span></span>  
  
 <span data-ttu-id="6b064-109">只`EnumerateFrames`应为托管链调用方法。</span><span class="sxs-lookup"><span data-stu-id="6b064-109">The `EnumerateFrames` method should be called only for managed chains.</span></span> <span data-ttu-id="6b064-110">调试 API 不提供用于获取非托管链中包含的帧的方法。</span><span class="sxs-lookup"><span data-stu-id="6b064-110">The debugging API does not provide methods for obtaining frames contained in unmanaged chains.</span></span> <span data-ttu-id="6b064-111">调试器必须使用其他方法来获取此信息。</span><span class="sxs-lookup"><span data-stu-id="6b064-111">The debugger must use other means to obtain this information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b064-112">要求</span><span class="sxs-lookup"><span data-stu-id="6b064-112">Requirements</span></span>  
 <span data-ttu-id="6b064-113">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6b064-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b064-114">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6b064-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6b064-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6b064-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6b064-116">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6b064-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
