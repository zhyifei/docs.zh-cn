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
ms.openlocfilehash: 5e037cf6fb88fff4886733ff4152dca0a827e0a3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54491023"
---
# <a name="isosdacinterface-interface"></a><span data-ttu-id="a51f1-102">ISOSDacInterface 接口</span><span class="sxs-lookup"><span data-stu-id="a51f1-102">ISOSDacInterface Interface</span></span>

<span data-ttu-id="a51f1-103">访问的数据提供帮助器方法`SOS`。</span><span class="sxs-lookup"><span data-stu-id="a51f1-103">Provides helper methods to access data from `SOS`.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="a51f1-104">方法</span><span class="sxs-lookup"><span data-stu-id="a51f1-104">Methods</span></span>

| <span data-ttu-id="a51f1-105">方法</span><span class="sxs-lookup"><span data-stu-id="a51f1-105">Method</span></span>                                                                                                               | <span data-ttu-id="a51f1-106">描述</span><span class="sxs-lookup"><span data-stu-id="a51f1-106">Description</span></span>                                                                                                                   |
| -------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| [<span data-ttu-id="a51f1-107">GetMethodDescData</span><span class="sxs-lookup"><span data-stu-id="a51f1-107">GetMethodDescData</span></span>](../../../../docs/framework/unmanaged-api/debugging/isosdacinterface-getmethoddescdata-method.md) | <span data-ttu-id="a51f1-108">获取有关数据给定[MethodDesc](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md)。</span><span class="sxs-lookup"><span data-stu-id="a51f1-108">Gets the data for the given [MethodDesc](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md).</span></span> |

## <a name="remarks"></a><span data-ttu-id="a51f1-109">备注</span><span class="sxs-lookup"><span data-stu-id="a51f1-109">Remarks</span></span>

<span data-ttu-id="a51f1-110">此接口存在于运行时内并不通过任何标头或库文件公开。</span><span class="sxs-lookup"><span data-stu-id="a51f1-110">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="a51f1-111">但是，它是一个 COM 接口派生`IUnknown`具有 GUID `436f00f2-b42a-4b9f-870c-e73db66ae930` ，可以通过常用的 COM 机制获取。</span><span class="sxs-lookup"><span data-stu-id="a51f1-111">However, it's a COM interface that derives from `IUnknown` with GUID `436f00f2-b42a-4b9f-870c-e73db66ae930` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="a51f1-112">要求</span><span class="sxs-lookup"><span data-stu-id="a51f1-112">Requirements</span></span>

<span data-ttu-id="a51f1-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a51f1-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="a51f1-114">**标头：** 无</span><span class="sxs-lookup"><span data-stu-id="a51f1-114">**Header:** None</span></span>  
<span data-ttu-id="a51f1-115">**库：** 无</span><span class="sxs-lookup"><span data-stu-id="a51f1-115">**Library:** None</span></span>  
<span data-ttu-id="a51f1-116">**.NET Framework 版本：**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="a51f1-116">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="a51f1-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="a51f1-117">See also</span></span>

- [<span data-ttu-id="a51f1-118">调试</span><span class="sxs-lookup"><span data-stu-id="a51f1-118">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="a51f1-119">调试接口</span><span class="sxs-lookup"><span data-stu-id="a51f1-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
