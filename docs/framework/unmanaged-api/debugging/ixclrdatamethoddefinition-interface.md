---
title: IXCLRDataMethodDefinition 接口
ms.date: 01/16/2019
api.name:
- IXCLRDataMethodDefinition Interface
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodDefinition Interface
helpviewer.keywords:
- IXCLRDataMethodDefinition Interface [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 4b1e8cb1cf34bb1c5ade1353351aab953e2b734a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54644242"
---
# <a name="ixclrdatamethoddefinition-interface"></a><span data-ttu-id="9a4b5-102">IXCLRDataMethodDefinition 接口</span><span class="sxs-lookup"><span data-stu-id="9a4b5-102">IXCLRDataMethodDefinition Interface</span></span>

<span data-ttu-id="9a4b5-103">提供用于查询方法定义的有关信息的方法。</span><span class="sxs-lookup"><span data-stu-id="9a4b5-103">Provides methods for querying information about a method definition.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="9a4b5-104">方法</span><span class="sxs-lookup"><span data-stu-id="9a4b5-104">Methods</span></span>

<span data-ttu-id="9a4b5-105">以下方法是一些在界面中可用的方法。</span><span class="sxs-lookup"><span data-stu-id="9a4b5-105">The following methods are some of the methods available in the interface.</span></span>

| <span data-ttu-id="9a4b5-106">方法</span><span class="sxs-lookup"><span data-stu-id="9a4b5-106">Method</span></span>                                                                                                                          | <span data-ttu-id="9a4b5-107">描述</span><span class="sxs-lookup"><span data-stu-id="9a4b5-107">Description</span></span>                                                                                 |
| ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- |
| [<span data-ttu-id="9a4b5-108">StartEnumInstances</span><span class="sxs-lookup"><span data-stu-id="9a4b5-108">StartEnumInstances</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethoddefinition-startenuminstances-method.md) | <span data-ttu-id="9a4b5-109">提供一个句柄的方法实例枚举给定`IXCLRDataAppDomain`。</span><span class="sxs-lookup"><span data-stu-id="9a4b5-109">Provides a handle for the enumeration of method instances for a given `IXCLRDataAppDomain`.</span></span> |
| [<span data-ttu-id="9a4b5-110">EnumInstance</span><span class="sxs-lookup"><span data-stu-id="9a4b5-110">EnumInstance</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethoddefinition-enuminstance-method.md)             | <span data-ttu-id="9a4b5-111">枚举该方法定义的实例。</span><span class="sxs-lookup"><span data-stu-id="9a4b5-111">Enumerates the instances of this method definition.</span></span>                                         |
| [<span data-ttu-id="9a4b5-112">EndEnumInstances</span><span class="sxs-lookup"><span data-stu-id="9a4b5-112">EndEnumInstances</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethoddefinition-endenuminstances-method.md)     | <span data-ttu-id="9a4b5-113">释放使用的内部实例枚举过程中使用的迭代器的资源。</span><span class="sxs-lookup"><span data-stu-id="9a4b5-113">Releases the resources used by internal iterators used during instance enumeration.</span></span>         |

## <a name="remarks"></a><span data-ttu-id="9a4b5-114">备注</span><span class="sxs-lookup"><span data-stu-id="9a4b5-114">Remarks</span></span>

<span data-ttu-id="9a4b5-115">此接口存在于运行时内并不通过任何标头或库文件公开。</span><span class="sxs-lookup"><span data-stu-id="9a4b5-115">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="9a4b5-116">但是，它是一个 COM 接口派生`IUnknown`具有 GUID `AAF60008-FB2C-420b-8FB1-42D244A54A97` ，可以通过常用的 COM 机制获取。</span><span class="sxs-lookup"><span data-stu-id="9a4b5-116">However, it's a COM interface that derives from `IUnknown` with GUID `AAF60008-FB2C-420b-8FB1-42D244A54A97` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="9a4b5-117">要求</span><span class="sxs-lookup"><span data-stu-id="9a4b5-117">Requirements</span></span>

<span data-ttu-id="9a4b5-118">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9a4b5-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="9a4b5-119">**标头：** 无</span><span class="sxs-lookup"><span data-stu-id="9a4b5-119">**Header:** None</span></span>  
<span data-ttu-id="9a4b5-120">**库：** 无</span><span class="sxs-lookup"><span data-stu-id="9a4b5-120">**Library:** None</span></span>  
<span data-ttu-id="9a4b5-121">**.NET Framework 版本：**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="9a4b5-121">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="9a4b5-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="9a4b5-122">See also</span></span>

- [<span data-ttu-id="9a4b5-123">调试</span><span class="sxs-lookup"><span data-stu-id="9a4b5-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="9a4b5-124">调试接口</span><span class="sxs-lookup"><span data-stu-id="9a4b5-124">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
