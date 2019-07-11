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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fc647805fcb7d8354a2540ac9424dc7155853444
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67745032"
---
# <a name="icordebugchainenumerateframes-method"></a><span data-ttu-id="198f6-102">ICorDebugChain::EnumerateFrames 方法</span><span class="sxs-lookup"><span data-stu-id="198f6-102">ICorDebugChain::EnumerateFrames Method</span></span>
<span data-ttu-id="198f6-103">获取一个枚举器包含在链中的所有托管的堆栈帧并从最新帧开始。</span><span class="sxs-lookup"><span data-stu-id="198f6-103">Gets an enumerator that contains all the managed stack frames in the chain, starting with the most recent frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="198f6-104">语法</span><span class="sxs-lookup"><span data-stu-id="198f6-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateFrames (  
    [out] ICorDebugFrameEnum **ppFrames  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="198f6-105">参数</span><span class="sxs-lookup"><span data-stu-id="198f6-105">Parameters</span></span>  
 `ppFrames`  
 <span data-ttu-id="198f6-106">[out]指向一个 ICorDebugFrameEnum 对象，它的堆栈帧的枚举器的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="198f6-106">[out] A pointer to the address of an ICorDebugFrameEnum object that is the enumerator for the stack frames.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="198f6-107">备注</span><span class="sxs-lookup"><span data-stu-id="198f6-107">Remarks</span></span>  
 <span data-ttu-id="198f6-108">链表示在线程的物理调用堆栈。</span><span class="sxs-lookup"><span data-stu-id="198f6-108">The chain represents the physical call stack for the thread.</span></span>  
  
 <span data-ttu-id="198f6-109">`EnumerateFrames`应仅为托管链中调用方法。</span><span class="sxs-lookup"><span data-stu-id="198f6-109">The `EnumerateFrames` method should be called only for managed chains.</span></span> <span data-ttu-id="198f6-110">调试 API 不提供用于获取非托管链中包含的帧的方法。</span><span class="sxs-lookup"><span data-stu-id="198f6-110">The debugging API does not provide methods for obtaining frames contained in unmanaged chains.</span></span> <span data-ttu-id="198f6-111">调试器必须使用其他方式获取此信息。</span><span class="sxs-lookup"><span data-stu-id="198f6-111">The debugger must use other means to obtain this information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="198f6-112">要求</span><span class="sxs-lookup"><span data-stu-id="198f6-112">Requirements</span></span>  
 <span data-ttu-id="198f6-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="198f6-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="198f6-114">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="198f6-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="198f6-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="198f6-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="198f6-116">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="198f6-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
