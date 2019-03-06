---
title: ICorDebugProcess4::ProcessStateChanged 方法
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
ms.openlocfilehash: b77dd1277e7d23729f30d9d495c5417055a22759
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57378985"
---
# <a name="icordebugprocess4processstatechanged-method"></a><span data-ttu-id="2cfe9-102">ICorDebugProcess4::ProcessStateChanged 方法</span><span class="sxs-lookup"><span data-stu-id="2cfe9-102">ICorDebugProcess4::ProcessStateChanged Method</span></span>

<span data-ttu-id="2cfe9-103">通知 ICorDebug 管道的过程调试器扩展继续调试对象的执行。</span><span class="sxs-lookup"><span data-stu-id="2cfe9-103">Notifies the ICorDebug pipeline that the out of process debugger is continuing the debugee's execution.</span></span>

## <a name="syntax"></a><span data-ttu-id="2cfe9-104">语法</span><span class="sxs-lookup"><span data-stu-id="2cfe9-104">Syntax</span></span>

```
HRESULT ProcessStateChanged(
    [in] CorDebugStateChange change
);
```

## <a name="parameters"></a><span data-ttu-id="2cfe9-105">参数</span><span class="sxs-lookup"><span data-stu-id="2cfe9-105">Parameters</span></span>

 `eChange`\
<span data-ttu-id="2cfe9-106">[in]成员[CorDebugStateChange 枚举](cordebugstatechange-enumeration.md)描述进程的执行状态的更改。</span><span class="sxs-lookup"><span data-stu-id="2cfe9-106">[in] A member of the [CorDebugStateChange enumeration](cordebugstatechange-enumeration.md) describing a change in the process's execution state.</span></span>

## <a name="remarks"></a><span data-ttu-id="2cfe9-107">备注</span><span class="sxs-lookup"><span data-stu-id="2cfe9-107">Remarks</span></span>

<span data-ttu-id="2cfe9-108">提供的方法属于`ICorDebugProcess4`接口，并对应于虚拟方法表的第四个槽。</span><span class="sxs-lookup"><span data-stu-id="2cfe9-108">The provided method is part of the `ICorDebugProcess4` interface and corresponds to the fourth slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="2cfe9-109">要求</span><span class="sxs-lookup"><span data-stu-id="2cfe9-109">Requirements</span></span>

 <span data-ttu-id="2cfe9-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2cfe9-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

 <span data-ttu-id="2cfe9-111">**标头：** 无</span><span class="sxs-lookup"><span data-stu-id="2cfe9-111">**Header:** None</span></span>

 <span data-ttu-id="2cfe9-112">**库：** 无</span><span class="sxs-lookup"><span data-stu-id="2cfe9-112">**Library:** None</span></span>
 
 <span data-ttu-id="2cfe9-113">**.NET Framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2cfe9-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="2cfe9-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="2cfe9-114">See also</span></span>

- [<span data-ttu-id="2cfe9-115">ICorDebugProcess4 接口</span><span class="sxs-lookup"><span data-stu-id="2cfe9-115">ICorDebugProcess4 Interface</span></span>](icordebugprocess4-interface.md)
- [<span data-ttu-id="2cfe9-116">调试接口</span><span class="sxs-lookup"><span data-stu-id="2cfe9-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="2cfe9-117">调试</span><span class="sxs-lookup"><span data-stu-id="2cfe9-117">Debugging</span></span>](index.md)