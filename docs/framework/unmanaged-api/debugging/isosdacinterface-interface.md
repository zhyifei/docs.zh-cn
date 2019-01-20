---
title: ISOSDacInterface 接口
ms.date: 01/16/2019
api.name:
- ISOSDacInterface Interface
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- ISOSDacInterface Interface
helpviewer.keywords:
- ISOSDacInterface Interface [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 745ecfbffaad841e1ceb9216802644ba9dd5b94e
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2019
ms.locfileid: "54416287"
---
# <a name="isosdacinterface-interface"></a><span data-ttu-id="27b3f-102">ISOSDacInterface 接口</span><span class="sxs-lookup"><span data-stu-id="27b3f-102">ISOSDacInterface Interface</span></span>

<span data-ttu-id="27b3f-103">访问的数据提供帮助器方法`SOS`。</span><span class="sxs-lookup"><span data-stu-id="27b3f-103">Provides helper methods to access data from `SOS`.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="27b3f-104">方法</span><span class="sxs-lookup"><span data-stu-id="27b3f-104">Methods</span></span>

| <span data-ttu-id="27b3f-105">方法</span><span class="sxs-lookup"><span data-stu-id="27b3f-105">Method</span></span>                                                                                                               | <span data-ttu-id="27b3f-106">描述</span><span class="sxs-lookup"><span data-stu-id="27b3f-106">Description</span></span>                                                                                                                   |
| -------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| [<span data-ttu-id="27b3f-107">GetMethodDescData</span><span class="sxs-lookup"><span data-stu-id="27b3f-107">GetMethodDescData</span></span>](../../../../docs/framework/unmanaged-api/debugging/isosdacinterface-getmethoddescdata-method.md) | <span data-ttu-id="27b3f-108">获取有关数据给定[MethodDesc](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md)。</span><span class="sxs-lookup"><span data-stu-id="27b3f-108">Gets the data for the given [MethodDesc](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md).</span></span> |

## <a name="remarks"></a><span data-ttu-id="27b3f-109">备注</span><span class="sxs-lookup"><span data-stu-id="27b3f-109">Remarks</span></span>

<span data-ttu-id="27b3f-110">此接口存在于运行时内并不通过任何标头或库文件公开。</span><span class="sxs-lookup"><span data-stu-id="27b3f-110">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="27b3f-111">但是，它是一个 COM 接口派生`IUnknown`具有 GUID `436f00f2-b42a-4b9f-870c-e73db66ae930` ，可以通过常用的 COM 机制获取。</span><span class="sxs-lookup"><span data-stu-id="27b3f-111">However, it's a COM interface that derives from `IUnknown` with GUID `436f00f2-b42a-4b9f-870c-e73db66ae930` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="27b3f-112">要求</span><span class="sxs-lookup"><span data-stu-id="27b3f-112">Requirements</span></span>

<span data-ttu-id="27b3f-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="27b3f-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="27b3f-114">**标头：** 无</span><span class="sxs-lookup"><span data-stu-id="27b3f-114">**Header:** None</span></span>  
<span data-ttu-id="27b3f-115">**库：** 无</span><span class="sxs-lookup"><span data-stu-id="27b3f-115">**Library:** None</span></span>  
<span data-ttu-id="27b3f-116">**.NET Framework 版本：**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="27b3f-116">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="27b3f-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="27b3f-117">See Also</span></span>

- [<span data-ttu-id="27b3f-118">调试</span><span class="sxs-lookup"><span data-stu-id="27b3f-118">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="27b3f-119">调试接口</span><span class="sxs-lookup"><span data-stu-id="27b3f-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
