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
ms.openlocfilehash: 708c681a98113a406249a360c2fc81087e5b97f8
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790427"
---
# <a name="ixclrdatamethoddefinition-interface"></a><span data-ttu-id="cf8eb-102">IXCLRDataMethodDefinition 接口</span><span class="sxs-lookup"><span data-stu-id="cf8eb-102">IXCLRDataMethodDefinition Interface</span></span>

<span data-ttu-id="cf8eb-103">提供用于查询有关方法定义的信息的方法。</span><span class="sxs-lookup"><span data-stu-id="cf8eb-103">Provides methods for querying information about a method definition.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="cf8eb-104">方法</span><span class="sxs-lookup"><span data-stu-id="cf8eb-104">Methods</span></span>

<span data-ttu-id="cf8eb-105">以下方法是接口中的一些可用方法。</span><span class="sxs-lookup"><span data-stu-id="cf8eb-105">The following methods are some of the methods available in the interface.</span></span>

| <span data-ttu-id="cf8eb-106">方法</span><span class="sxs-lookup"><span data-stu-id="cf8eb-106">Method</span></span>                                                                                                                          | <span data-ttu-id="cf8eb-107">描述</span><span class="sxs-lookup"><span data-stu-id="cf8eb-107">Description</span></span>                                                                                 |
| ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- |
| [<span data-ttu-id="cf8eb-108">StartEnumInstances</span><span class="sxs-lookup"><span data-stu-id="cf8eb-108">StartEnumInstances</span></span>](ixclrdatamethoddefinition-startenuminstances-method.md) | <span data-ttu-id="cf8eb-109">提供给定 `IXCLRDataAppDomain`的方法实例枚举的句柄。</span><span class="sxs-lookup"><span data-stu-id="cf8eb-109">Provides a handle for the enumeration of method instances for a given `IXCLRDataAppDomain`.</span></span> |
| [<span data-ttu-id="cf8eb-110">EnumInstance</span><span class="sxs-lookup"><span data-stu-id="cf8eb-110">EnumInstance</span></span>](ixclrdatamethoddefinition-enuminstance-method.md)             | <span data-ttu-id="cf8eb-111">枚举此方法定义的实例。</span><span class="sxs-lookup"><span data-stu-id="cf8eb-111">Enumerates the instances of this method definition.</span></span>                                         |
| [<span data-ttu-id="cf8eb-112">EndEnumInstances</span><span class="sxs-lookup"><span data-stu-id="cf8eb-112">EndEnumInstances</span></span>](ixclrdatamethoddefinition-endenuminstances-method.md)     | <span data-ttu-id="cf8eb-113">释放实例枚举期间使用的内部迭代器所使用的资源。</span><span class="sxs-lookup"><span data-stu-id="cf8eb-113">Releases the resources used by internal iterators used during instance enumeration.</span></span>         |

## <a name="remarks"></a><span data-ttu-id="cf8eb-114">备注</span><span class="sxs-lookup"><span data-stu-id="cf8eb-114">Remarks</span></span>

<span data-ttu-id="cf8eb-115">此接口在运行时中存在，不会通过任何标头或库文件公开。</span><span class="sxs-lookup"><span data-stu-id="cf8eb-115">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="cf8eb-116">不过，它是一个使用 GUID `AAF60008-FB2C-420b-8FB1-42D244A54A97` 派生的 COM 接口，可通过常用的 COM 机制来获取 `IUnknown`。</span><span class="sxs-lookup"><span data-stu-id="cf8eb-116">However, it's a COM interface that derives from `IUnknown` with GUID `AAF60008-FB2C-420b-8FB1-42D244A54A97` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="cf8eb-117">需求</span><span class="sxs-lookup"><span data-stu-id="cf8eb-117">Requirements</span></span>

<span data-ttu-id="cf8eb-118">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="cf8eb-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="cf8eb-119">**标头：** 内容</span><span class="sxs-lookup"><span data-stu-id="cf8eb-119">**Header:** None</span></span>  
<span data-ttu-id="cf8eb-120">**库：** 内容</span><span class="sxs-lookup"><span data-stu-id="cf8eb-120">**Library:** None</span></span>  
<span data-ttu-id="cf8eb-121">**.NET Framework 版本：** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="cf8eb-121">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="cf8eb-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cf8eb-122">See also</span></span>

- [<span data-ttu-id="cf8eb-123">调试</span><span class="sxs-lookup"><span data-stu-id="cf8eb-123">Debugging</span></span>](index.md)
- [<span data-ttu-id="cf8eb-124">调试接口</span><span class="sxs-lookup"><span data-stu-id="cf8eb-124">Debugging Interfaces</span></span>](debugging-interfaces.md)
