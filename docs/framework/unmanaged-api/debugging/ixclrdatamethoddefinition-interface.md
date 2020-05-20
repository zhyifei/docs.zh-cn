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
ms.openlocfilehash: ebb689eee4a89a70e81d8f9d958e7826c3b3421b
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420950"
---
# <a name="ixclrdatamethoddefinition-interface"></a><span data-ttu-id="a4e8c-102">IXCLRDataMethodDefinition 接口</span><span class="sxs-lookup"><span data-stu-id="a4e8c-102">IXCLRDataMethodDefinition Interface</span></span>

<span data-ttu-id="a4e8c-103">提供用于查询有关方法定义的信息的方法。</span><span class="sxs-lookup"><span data-stu-id="a4e8c-103">Provides methods for querying information about a method definition.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="a4e8c-104">方法</span><span class="sxs-lookup"><span data-stu-id="a4e8c-104">Methods</span></span>

<span data-ttu-id="a4e8c-105">以下方法是接口中的一些可用方法。</span><span class="sxs-lookup"><span data-stu-id="a4e8c-105">The following methods are some of the methods available in the interface.</span></span>

| <span data-ttu-id="a4e8c-106">方法</span><span class="sxs-lookup"><span data-stu-id="a4e8c-106">Method</span></span>                                                                                                                          | <span data-ttu-id="a4e8c-107">说明</span><span class="sxs-lookup"><span data-stu-id="a4e8c-107">Description</span></span>                                                                                 |
| ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- |
| [<span data-ttu-id="a4e8c-108">StartEnumInstances</span><span class="sxs-lookup"><span data-stu-id="a4e8c-108">StartEnumInstances</span></span>](ixclrdatamethoddefinition-startenuminstances-method.md) | <span data-ttu-id="a4e8c-109">为给定的的方法实例枚举提供句柄 `IXCLRDataAppDomain` 。</span><span class="sxs-lookup"><span data-stu-id="a4e8c-109">Provides a handle for the enumeration of method instances for a given `IXCLRDataAppDomain`.</span></span> |
| [<span data-ttu-id="a4e8c-110">EnumInstance</span><span class="sxs-lookup"><span data-stu-id="a4e8c-110">EnumInstance</span></span>](ixclrdatamethoddefinition-enuminstance-method.md)             | <span data-ttu-id="a4e8c-111">枚举此方法定义的实例。</span><span class="sxs-lookup"><span data-stu-id="a4e8c-111">Enumerates the instances of this method definition.</span></span>                                         |
| [<span data-ttu-id="a4e8c-112">EndEnumInstances</span><span class="sxs-lookup"><span data-stu-id="a4e8c-112">EndEnumInstances</span></span>](ixclrdatamethoddefinition-endenuminstances-method.md)     | <span data-ttu-id="a4e8c-113">释放实例枚举期间使用的内部迭代器所使用的资源。</span><span class="sxs-lookup"><span data-stu-id="a4e8c-113">Releases the resources used by internal iterators used during instance enumeration.</span></span>         |

## <a name="remarks"></a><span data-ttu-id="a4e8c-114">备注</span><span class="sxs-lookup"><span data-stu-id="a4e8c-114">Remarks</span></span>

<span data-ttu-id="a4e8c-115">此接口在运行时中存在，不会通过任何标头或库文件公开。</span><span class="sxs-lookup"><span data-stu-id="a4e8c-115">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="a4e8c-116">但是，它是从使用 GUID 派生的 COM 接口， `IUnknown` `AAF60008-FB2C-420b-8FB1-42D244A54A97` 该接口可通过常用的 COM 机制获得。</span><span class="sxs-lookup"><span data-stu-id="a4e8c-116">However, it's a COM interface that derives from `IUnknown` with GUID `AAF60008-FB2C-420b-8FB1-42D244A54A97` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="a4e8c-117">要求</span><span class="sxs-lookup"><span data-stu-id="a4e8c-117">Requirements</span></span>

<span data-ttu-id="a4e8c-118">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a4e8c-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="a4e8c-119">**标头：** 内容</span><span class="sxs-lookup"><span data-stu-id="a4e8c-119">**Header:** None</span></span>  
<span data-ttu-id="a4e8c-120">**库：** 内容</span><span class="sxs-lookup"><span data-stu-id="a4e8c-120">**Library:** None</span></span>  
<span data-ttu-id="a4e8c-121">**.NET Framework 版本：**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="a4e8c-121">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="a4e8c-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a4e8c-122">See also</span></span>

- [<span data-ttu-id="a4e8c-123">调试</span><span class="sxs-lookup"><span data-stu-id="a4e8c-123">Debugging</span></span>](index.md)
- [<span data-ttu-id="a4e8c-124">调试接口</span><span class="sxs-lookup"><span data-stu-id="a4e8c-124">Debugging Interfaces</span></span>](debugging-interfaces.md)
