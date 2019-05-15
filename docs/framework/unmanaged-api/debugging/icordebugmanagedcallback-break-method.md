---
title: ICorDebugManagedCallback::Break 方法
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.Break
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::Break
helpviewer_keywords:
- Break method [.NET Framework debugging]
- ICorDebugManagedCallback::Break method [.NET Framework debugging]
ms.assetid: 7d78a301-82b3-43b2-9d65-3cda3285ae97
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 621c5b1e32a1a21c2b0b883249c3b65fadceb5f2
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "65632352"
---
# <a name="icordebugmanagedcallbackbreak-method"></a><span data-ttu-id="c6034-102">ICorDebugManagedCallback::Break 方法</span><span class="sxs-lookup"><span data-stu-id="c6034-102">ICorDebugManagedCallback::Break Method</span></span>

<span data-ttu-id="c6034-103">通知调试器时<xref:System.Reflection.Emit.OpCodes.Break>执行代码流中的指令。</span><span class="sxs-lookup"><span data-stu-id="c6034-103">Notifies the debugger when a <xref:System.Reflection.Emit.OpCodes.Break> instruction in the code stream is executed.</span></span>

## <a name="syntax"></a><span data-ttu-id="c6034-104">语法</span><span class="sxs-lookup"><span data-stu-id="c6034-104">Syntax</span></span>

```cpp
HRESULT Break (
    [in] ICorDebugAppDomain *pAppDomain,
    [in] ICorDebugThread    *thread
);
```

## <a name="parameters"></a><span data-ttu-id="c6034-105">参数</span><span class="sxs-lookup"><span data-stu-id="c6034-105">Parameters</span></span>

`pAppDomain`\
<span data-ttu-id="c6034-106">[in]指向一个 ICorDebugAppDomain 对象，表示包含 break 指令的应用程序域的指针。</span><span class="sxs-lookup"><span data-stu-id="c6034-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contains the break instruction.</span></span>

`thread`\
<span data-ttu-id="c6034-107">[in]指向表示，包含 break 指令的线程的 ICorDebugThread 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="c6034-107">[in] A pointer to an ICorDebugThread object that represents the thread that contains the break instruction.</span></span>

## <a name="requirements"></a><span data-ttu-id="c6034-108">要求</span><span class="sxs-lookup"><span data-stu-id="c6034-108">Requirements</span></span>

<span data-ttu-id="c6034-109">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c6034-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="c6034-110">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c6034-110">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="c6034-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c6034-111">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="c6034-112">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6034-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="c6034-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="c6034-113">See also</span></span>

- [<span data-ttu-id="c6034-114">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="c6034-114">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
