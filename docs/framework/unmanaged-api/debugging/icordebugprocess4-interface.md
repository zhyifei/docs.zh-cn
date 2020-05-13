---
title: ICorDebugProcess4 接口
ms.date: 02/07/2019
api_name:
- ICorDebugProcess4
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess4
helpviewer_keywords:
- ICorDebugProcess4 interface [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: fcf725ea98fa4351e72cf592f92968ee2233ecb0
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213577"
---
# <a name="icordebugprocess4-interface"></a><span data-ttu-id="eff3e-102">ICorDebugProcess4 接口</span><span class="sxs-lookup"><span data-stu-id="eff3e-102">ICorDebugProcess4 Interface</span></span>

<span data-ttu-id="eff3e-103">为进程外执行控制提供支持。</span><span class="sxs-lookup"><span data-stu-id="eff3e-103">Provides support for out of process execution control.</span></span>

## <a name="methods"></a><span data-ttu-id="eff3e-104">方法</span><span class="sxs-lookup"><span data-stu-id="eff3e-104">Methods</span></span>

| <span data-ttu-id="eff3e-105">方法</span><span class="sxs-lookup"><span data-stu-id="eff3e-105">Method</span></span>                                                                 | <span data-ttu-id="eff3e-106">描述</span><span class="sxs-lookup"><span data-stu-id="eff3e-106">Description</span></span>                                                                                             |
| ---------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------- |
| [<span data-ttu-id="eff3e-107">ProcessStateChanged</span><span class="sxs-lookup"><span data-stu-id="eff3e-107">ProcessStateChanged</span></span>](icordebugprocess4-processstatechanged-method.md) | <span data-ttu-id="eff3e-108">通知 ICorDebug 管道进程外调试器正在继续执行调试对象的执行。</span><span class="sxs-lookup"><span data-stu-id="eff3e-108">Notifies the ICorDebug pipeline that the out of process debugger is continuing the debugee's execution.</span></span> |

## <a name="remarks"></a><span data-ttu-id="eff3e-109">备注</span><span class="sxs-lookup"><span data-stu-id="eff3e-109">Remarks</span></span>

<span data-ttu-id="eff3e-110">此接口在运行时中存在，不会通过任何标头或库文件公开。</span><span class="sxs-lookup"><span data-stu-id="eff3e-110">This interface lives inside the runtime and isn't exposed through any headers or library files.</span></span> <span data-ttu-id="eff3e-111">但是，它是从使用 GUID 派生的 COM 接口， `IUnknown` `E930C679-78AF-4953-8AB7-B0AABF0F9F80` 该接口可通过常用的 COM 机制获得。</span><span class="sxs-lookup"><span data-stu-id="eff3e-111">However, it's a COM interface that derives from `IUnknown` with GUID `E930C679-78AF-4953-8AB7-B0AABF0F9F80` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="eff3e-112">要求</span><span class="sxs-lookup"><span data-stu-id="eff3e-112">Requirements</span></span>

<span data-ttu-id="eff3e-113">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="eff3e-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="eff3e-114">**标头：** 内容</span><span class="sxs-lookup"><span data-stu-id="eff3e-114">**Header:** None</span></span>

<span data-ttu-id="eff3e-115">**库：** 内容</span><span class="sxs-lookup"><span data-stu-id="eff3e-115">**Library:** None</span></span>

<span data-ttu-id="eff3e-116">**.NET Framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eff3e-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="eff3e-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="eff3e-117">See also</span></span>

- [<span data-ttu-id="eff3e-118">调试接口</span><span class="sxs-lookup"><span data-stu-id="eff3e-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="eff3e-119">调试</span><span class="sxs-lookup"><span data-stu-id="eff3e-119">Debugging</span></span>](index.md)
