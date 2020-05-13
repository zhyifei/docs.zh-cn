---
title: ICorDebugProcess4：:P rocessStateChanged 方法
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
ms.openlocfilehash: 910c411d2c63ce2c6cf262e28e08546657dc2a4c
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213564"
---
# <a name="icordebugprocess4processstatechanged-method"></a><span data-ttu-id="6d562-102">ICorDebugProcess4：:P rocessStateChanged 方法</span><span class="sxs-lookup"><span data-stu-id="6d562-102">ICorDebugProcess4::ProcessStateChanged Method</span></span>

<span data-ttu-id="6d562-103">通知 ICorDebug 管道进程外调试器正在继续执行调试对象的执行。</span><span class="sxs-lookup"><span data-stu-id="6d562-103">Notifies the ICorDebug pipeline that the out of process debugger is continuing the debugee's execution.</span></span>

## <a name="syntax"></a><span data-ttu-id="6d562-104">语法</span><span class="sxs-lookup"><span data-stu-id="6d562-104">Syntax</span></span>

```cpp
HRESULT ProcessStateChanged(
    [in] CorDebugStateChange change
);
```

## <a name="parameters"></a><span data-ttu-id="6d562-105">参数</span><span class="sxs-lookup"><span data-stu-id="6d562-105">Parameters</span></span>

 `eChange`\
<span data-ttu-id="6d562-106">中描述进程的执行状态更改的[CorDebugStateChange 枚举](cordebugstatechange-enumeration.md)的成员。</span><span class="sxs-lookup"><span data-stu-id="6d562-106">[in] A member of the [CorDebugStateChange enumeration](cordebugstatechange-enumeration.md) describing a change in the process's execution state.</span></span>

## <a name="remarks"></a><span data-ttu-id="6d562-107">备注</span><span class="sxs-lookup"><span data-stu-id="6d562-107">Remarks</span></span>

<span data-ttu-id="6d562-108">提供的方法是接口的一部分 `ICorDebugProcess4` ，并且对应于虚拟方法表的第四个槽。</span><span class="sxs-lookup"><span data-stu-id="6d562-108">The provided method is part of the `ICorDebugProcess4` interface and corresponds to the fourth slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="6d562-109">要求</span><span class="sxs-lookup"><span data-stu-id="6d562-109">Requirements</span></span>

 <span data-ttu-id="6d562-110">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6d562-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

 <span data-ttu-id="6d562-111">**标头：** 内容</span><span class="sxs-lookup"><span data-stu-id="6d562-111">**Header:** None</span></span>

 <span data-ttu-id="6d562-112">**库：** 内容</span><span class="sxs-lookup"><span data-stu-id="6d562-112">**Library:** None</span></span>

 <span data-ttu-id="6d562-113">**.NET Framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d562-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="6d562-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="6d562-114">See also</span></span>

- [<span data-ttu-id="6d562-115">ICorDebugProcess4 接口</span><span class="sxs-lookup"><span data-stu-id="6d562-115">ICorDebugProcess4 Interface</span></span>](icordebugprocess4-interface.md)
- [<span data-ttu-id="6d562-116">调试接口</span><span class="sxs-lookup"><span data-stu-id="6d562-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="6d562-117">调试</span><span class="sxs-lookup"><span data-stu-id="6d562-117">Debugging</span></span>](index.md)
