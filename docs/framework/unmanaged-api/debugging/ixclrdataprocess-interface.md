---
title: IXCLRDataProcess 接口
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess Interface
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess Interface
helpviewer.keywords:
- IXCLRDataProcess Interface [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 6a6def8fc10f04b89aa8d8c735025b01f9b6ddfb
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420755"
---
# <a name="ixclrdataprocess-interface"></a><span data-ttu-id="e688a-102">IXCLRDataProcess 接口</span><span class="sxs-lookup"><span data-stu-id="e688a-102">IXCLRDataProcess Interface</span></span>

<span data-ttu-id="e688a-103">提供用于查询有关进程的信息的方法。</span><span class="sxs-lookup"><span data-stu-id="e688a-103">Provides methods for querying information about a process.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="e688a-104">方法</span><span class="sxs-lookup"><span data-stu-id="e688a-104">Methods</span></span>

| <span data-ttu-id="e688a-105">方法</span><span class="sxs-lookup"><span data-stu-id="e688a-105">Method</span></span>                                                                                                                                               | <span data-ttu-id="e688a-106">说明</span><span class="sxs-lookup"><span data-stu-id="e688a-106">Description</span></span>                                                                                     |
| ---------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| [<span data-ttu-id="e688a-107">GetAppDomainByUniqueId</span><span class="sxs-lookup"><span data-stu-id="e688a-107">GetAppDomainByUniqueId</span></span>](ixclrdataprocess-getappdomainbyuniqueid-method.md)                       | <span data-ttu-id="e688a-108">`AppDomain`按其唯一 id 在进程中获取。</span><span class="sxs-lookup"><span data-stu-id="e688a-108">Gets an `AppDomain` in a process by its unique id.</span></span>                                              |
| [<span data-ttu-id="e688a-109">StartEnumModules</span><span class="sxs-lookup"><span data-stu-id="e688a-109">StartEnumModules</span></span>](ixclrdataprocess-startenummodules-method.md)                                   | <span data-ttu-id="e688a-110">提供枚举进程的模块的句柄。</span><span class="sxs-lookup"><span data-stu-id="e688a-110">Provides a handle to enumerate the modules of a process.</span></span>                                        |
| [<span data-ttu-id="e688a-111">EnumModule</span><span class="sxs-lookup"><span data-stu-id="e688a-111">EnumModule</span></span>](ixclrdataprocess-enummodule-method.md)                                               | <span data-ttu-id="e688a-112">枚举此进程的模块。</span><span class="sxs-lookup"><span data-stu-id="e688a-112">Enumerates the modules of this process.</span></span>                                                         |
| [<span data-ttu-id="e688a-113">EndEnumModules</span><span class="sxs-lookup"><span data-stu-id="e688a-113">EndEnumModules</span></span>](ixclrdataprocess-endenummodules-method.md)                                       | <span data-ttu-id="e688a-114">释放模块枚举期间使用的内部迭代器所使用的资源。</span><span class="sxs-lookup"><span data-stu-id="e688a-114">Releases the resources used by internal iterators used during module enumeration.</span></span>               |
| [<span data-ttu-id="e688a-115">StartEnumMethodInstancesByAddress</span><span class="sxs-lookup"><span data-stu-id="e688a-115">StartEnumMethodInstancesByAddress</span></span>](ixclrdataprocess-startenummethodinstancesbyaddress-method.md) | <span data-ttu-id="e688a-116">提供用于枚举 `AppDomain` 从给定地址开始的方法实例的句柄。</span><span class="sxs-lookup"><span data-stu-id="e688a-116">Provides a handle to enumerate the method instances of `AppDomain` starting at a given address.</span></span> |
| [<span data-ttu-id="e688a-117">EnumMethodInstanceByAddress</span><span class="sxs-lookup"><span data-stu-id="e688a-117">EnumMethodInstanceByAddress</span></span>](ixclrdataprocess-enummethodinstancebyaddress-method.md)             | <span data-ttu-id="e688a-118">枚举此进程的方法实例（从地址偏移量开始）。</span><span class="sxs-lookup"><span data-stu-id="e688a-118">Enumerates the method instances of this process starting at an address offset.</span></span>                  |
| [<span data-ttu-id="e688a-119">EndEnumMethodInstancesByAddress</span><span class="sxs-lookup"><span data-stu-id="e688a-119">EndEnumMethodInstancesByAddress</span></span>](ixclrdataprocess-endenummethodinstancesbyaddress-method.md)     | <span data-ttu-id="e688a-120">释放实例枚举期间使用的内部迭代器所使用的资源。</span><span class="sxs-lookup"><span data-stu-id="e688a-120">Releases the resources used by internal iterators used during instance enumeration.</span></span>             |

## <a name="remarks"></a><span data-ttu-id="e688a-121">备注</span><span class="sxs-lookup"><span data-stu-id="e688a-121">Remarks</span></span>

<span data-ttu-id="e688a-122">此接口在运行时中存在，不会通过任何标头或库文件公开。</span><span class="sxs-lookup"><span data-stu-id="e688a-122">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="e688a-123">但是，它是从使用 GUID 派生的 COM 接口， `IUnknown` `5c552ab6-fc09-4cb3-8e36-22fa03c798b7` 该接口可通过常用的 COM 机制获得。</span><span class="sxs-lookup"><span data-stu-id="e688a-123">However, it's a COM interface that derives from `IUnknown` with GUID `5c552ab6-fc09-4cb3-8e36-22fa03c798b7` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="e688a-124">要求</span><span class="sxs-lookup"><span data-stu-id="e688a-124">Requirements</span></span>

<span data-ttu-id="e688a-125">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e688a-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>
<span data-ttu-id="e688a-126">**标头：** 内容</span><span class="sxs-lookup"><span data-stu-id="e688a-126">**Header:** None</span></span>  
<span data-ttu-id="e688a-127">**库：** 内容</span><span class="sxs-lookup"><span data-stu-id="e688a-127">**Library:** None</span></span>  
<span data-ttu-id="e688a-128">**.NET Framework 版本：**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="e688a-128">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="e688a-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e688a-129">See also</span></span>

- [<span data-ttu-id="e688a-130">调试</span><span class="sxs-lookup"><span data-stu-id="e688a-130">Debugging</span></span>](index.md)
- [<span data-ttu-id="e688a-131">调试接口</span><span class="sxs-lookup"><span data-stu-id="e688a-131">Debugging Interfaces</span></span>](debugging-interfaces.md)
