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
ms.openlocfilehash: d408f317b546fb7e8314e904e6f5ad9e6296ae6d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33403261"
---
# <a name="icordebugchainenumerateframes-method"></a><span data-ttu-id="97464-102">ICorDebugChain::EnumerateFrames 方法</span><span class="sxs-lookup"><span data-stu-id="97464-102">ICorDebugChain::EnumerateFrames Method</span></span>
<span data-ttu-id="97464-103">获取一个枚举器包含的链中的所有托管的堆栈帧并从最新帧开始。</span><span class="sxs-lookup"><span data-stu-id="97464-103">Gets an enumerator that contains all the managed stack frames in the chain, starting with the most recent frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97464-104">语法</span><span class="sxs-lookup"><span data-stu-id="97464-104">Syntax</span></span>  
  
```  
HRESULT EnumerateFrames (  
    [out] ICorDebugFrameEnum **ppFrames  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="97464-105">参数</span><span class="sxs-lookup"><span data-stu-id="97464-105">Parameters</span></span>  
 `ppFrames`  
 <span data-ttu-id="97464-106">[out]指向一个 ICorDebugFrameEnum 对象，它的堆栈帧的枚举器的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="97464-106">[out] A pointer to the address of an ICorDebugFrameEnum object that is the enumerator for the stack frames.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="97464-107">备注</span><span class="sxs-lookup"><span data-stu-id="97464-107">Remarks</span></span>  
 <span data-ttu-id="97464-108">链表示线程的物理调用堆栈。</span><span class="sxs-lookup"><span data-stu-id="97464-108">The chain represents the physical call stack for the thread.</span></span>  
  
 <span data-ttu-id="97464-109">`EnumerateFrames`应该仅用于托管链的调用方法。</span><span class="sxs-lookup"><span data-stu-id="97464-109">The `EnumerateFrames` method should be called only for managed chains.</span></span> <span data-ttu-id="97464-110">调试 API 不提供用于获取非托管链中包含的帧的方法。</span><span class="sxs-lookup"><span data-stu-id="97464-110">The debugging API does not provide methods for obtaining frames contained in unmanaged chains.</span></span> <span data-ttu-id="97464-111">调试器必须使用其他方法来获取此信息。</span><span class="sxs-lookup"><span data-stu-id="97464-111">The debugger must use other means to obtain this information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97464-112">要求</span><span class="sxs-lookup"><span data-stu-id="97464-112">Requirements</span></span>  
 <span data-ttu-id="97464-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="97464-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="97464-114">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="97464-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="97464-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="97464-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="97464-116">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="97464-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
