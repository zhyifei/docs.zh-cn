---
title: ICorDebugProcess4：:Process状态更改方法
ms.date: 02/07/2019
api_name:
- ICorDebugProcess4::ProcessStateChanged
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess4::ProcessStateChanged
helpviewer_keywords:
- ICorDebugProcess4::ProcessStateChanged method [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: a6f36f5b86b4fa58ce2a4ef4aa23d527f797a5a5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178629"
---
# <a name="icordebugprocess4processstatechanged-method"></a><span data-ttu-id="24b04-102">ICorDebugProcess4：:Process状态更改方法</span><span class="sxs-lookup"><span data-stu-id="24b04-102">ICorDebugProcess4::ProcessStateChanged Method</span></span>

<span data-ttu-id="24b04-103">通知 ICorDebug 管道进程外调试器正在继续执行调试器。</span><span class="sxs-lookup"><span data-stu-id="24b04-103">Notifies the ICorDebug pipeline that the out of process debugger is continuing the debugee's execution.</span></span>

## <a name="syntax"></a><span data-ttu-id="24b04-104">语法</span><span class="sxs-lookup"><span data-stu-id="24b04-104">Syntax</span></span>

```cpp
HRESULT ProcessStateChanged(
    [in] CorDebugStateChange change
);
```

## <a name="parameters"></a><span data-ttu-id="24b04-105">parameters</span><span class="sxs-lookup"><span data-stu-id="24b04-105">Parameters</span></span>

 `eChange`\
<span data-ttu-id="24b04-106">[在][CorDebugStateChange 计数](cordebugstatechange-enumeration.md)的成员，描述进程执行状态的变化。</span><span class="sxs-lookup"><span data-stu-id="24b04-106">[in] A member of the [CorDebugStateChange enumeration](cordebugstatechange-enumeration.md) describing a change in the process's execution state.</span></span>

## <a name="remarks"></a><span data-ttu-id="24b04-107">备注</span><span class="sxs-lookup"><span data-stu-id="24b04-107">Remarks</span></span>

<span data-ttu-id="24b04-108">提供的方法是接口的一`ICorDebugProcess4`部分，对应于虚拟方法表的第四个槽。</span><span class="sxs-lookup"><span data-stu-id="24b04-108">The provided method is part of the `ICorDebugProcess4` interface and corresponds to the fourth slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="24b04-109">要求</span><span class="sxs-lookup"><span data-stu-id="24b04-109">Requirements</span></span>

 <span data-ttu-id="24b04-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="24b04-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

 <span data-ttu-id="24b04-111">**标题：** 没有</span><span class="sxs-lookup"><span data-stu-id="24b04-111">**Header:** None</span></span>

 <span data-ttu-id="24b04-112">**库：** 没有</span><span class="sxs-lookup"><span data-stu-id="24b04-112">**Library:** None</span></span>

 <span data-ttu-id="24b04-113">**.NET 框架版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="24b04-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="24b04-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="24b04-114">See also</span></span>

- [<span data-ttu-id="24b04-115">ICorDebugProcess4 接口</span><span class="sxs-lookup"><span data-stu-id="24b04-115">ICorDebugProcess4 Interface</span></span>](icordebugprocess4-interface.md)
- [<span data-ttu-id="24b04-116">调试接口</span><span class="sxs-lookup"><span data-stu-id="24b04-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="24b04-117">调试</span><span class="sxs-lookup"><span data-stu-id="24b04-117">Debugging</span></span>](index.md)
