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
ms.openlocfilehash: 1bdc958f2516bcd7c2eb74312fbf478e6d49535a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61948794"
---
# <a name="icordebugprocess4-interface"></a><span data-ttu-id="a2e46-102">ICorDebugProcess4 接口</span><span class="sxs-lookup"><span data-stu-id="a2e46-102">ICorDebugProcess4 Interface</span></span>

<span data-ttu-id="a2e46-103">提供对进程执行失控的支持。</span><span class="sxs-lookup"><span data-stu-id="a2e46-103">Provides support for out of process execution control.</span></span>

## <a name="methods"></a><span data-ttu-id="a2e46-104">方法</span><span class="sxs-lookup"><span data-stu-id="a2e46-104">Methods</span></span>

| <span data-ttu-id="a2e46-105">方法</span><span class="sxs-lookup"><span data-stu-id="a2e46-105">Method</span></span>                                                                 | <span data-ttu-id="a2e46-106">描述</span><span class="sxs-lookup"><span data-stu-id="a2e46-106">Description</span></span>                                                                                             |
| ---------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------- |
| [<span data-ttu-id="a2e46-107">ProcessStateChanged</span><span class="sxs-lookup"><span data-stu-id="a2e46-107">ProcessStateChanged</span></span>](icordebugprocess4-processstatechanged-method.md) | <span data-ttu-id="a2e46-108">通知 ICorDebug 管道的过程调试器扩展继续调试对象的执行。</span><span class="sxs-lookup"><span data-stu-id="a2e46-108">Notifies the ICorDebug pipeline that the out of process debugger is continuing the debugee's execution.</span></span> |

## <a name="remarks"></a><span data-ttu-id="a2e46-109">备注</span><span class="sxs-lookup"><span data-stu-id="a2e46-109">Remarks</span></span>

<span data-ttu-id="a2e46-110">此接口存在于运行时内并不公开通过任何标头或库文件。</span><span class="sxs-lookup"><span data-stu-id="a2e46-110">This interface lives inside the runtime and isn't exposed through any headers or library files.</span></span> <span data-ttu-id="a2e46-111">但是，它是一个 COM 接口派生`IUnknown`具有 GUID `E930C679-78AF-4953-8AB7-B0AABF0F9F80` ，可以通过常用的 COM 机制获取。</span><span class="sxs-lookup"><span data-stu-id="a2e46-111">However, it's a COM interface that derives from `IUnknown` with GUID `E930C679-78AF-4953-8AB7-B0AABF0F9F80` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="a2e46-112">要求</span><span class="sxs-lookup"><span data-stu-id="a2e46-112">Requirements</span></span>

<span data-ttu-id="a2e46-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a2e46-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="a2e46-114">**标头：** None</span><span class="sxs-lookup"><span data-stu-id="a2e46-114">**Header:** None</span></span>

<span data-ttu-id="a2e46-115">**库：** None</span><span class="sxs-lookup"><span data-stu-id="a2e46-115">**Library:** None</span></span>

<span data-ttu-id="a2e46-116">**.NET Framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a2e46-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="a2e46-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="a2e46-117">See also</span></span>

- [<span data-ttu-id="a2e46-118">调试接口</span><span class="sxs-lookup"><span data-stu-id="a2e46-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="a2e46-119">调试</span><span class="sxs-lookup"><span data-stu-id="a2e46-119">Debugging</span></span>](index.md)
