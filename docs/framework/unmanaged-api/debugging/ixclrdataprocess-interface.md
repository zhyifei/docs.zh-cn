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
ms.openlocfilehash: a5d707d61513b030e5968af28db3c2a606e4419b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790375"
---
# <a name="ixclrdataprocess-interface"></a><span data-ttu-id="c6083-102">IXCLRDataProcess 接口</span><span class="sxs-lookup"><span data-stu-id="c6083-102">IXCLRDataProcess Interface</span></span>

<span data-ttu-id="c6083-103">提供用于查询有关进程的信息的方法。</span><span class="sxs-lookup"><span data-stu-id="c6083-103">Provides methods for querying information about a process.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="c6083-104">方法</span><span class="sxs-lookup"><span data-stu-id="c6083-104">Methods</span></span>

| <span data-ttu-id="c6083-105">方法</span><span class="sxs-lookup"><span data-stu-id="c6083-105">Method</span></span>                                                                                                                                               | <span data-ttu-id="c6083-106">描述</span><span class="sxs-lookup"><span data-stu-id="c6083-106">Description</span></span>                                                                                     |
| ---------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| [<span data-ttu-id="c6083-107">GetAppDomainByUniqueId</span><span class="sxs-lookup"><span data-stu-id="c6083-107">GetAppDomainByUniqueId</span></span>](ixclrdataprocess-getappdomainbyuniqueid-method.md)                       | <span data-ttu-id="c6083-108">按唯一 id 获取进程中的 `AppDomain`。</span><span class="sxs-lookup"><span data-stu-id="c6083-108">Gets an `AppDomain` in a process by its unique id.</span></span>                                              |
| [<span data-ttu-id="c6083-109">StartEnumModules</span><span class="sxs-lookup"><span data-stu-id="c6083-109">StartEnumModules</span></span>](ixclrdataprocess-startenummodules-method.md)                                   | <span data-ttu-id="c6083-110">提供枚举进程的模块的句柄。</span><span class="sxs-lookup"><span data-stu-id="c6083-110">Provides a handle to enumerate the modules of a process.</span></span>                                        |
| [<span data-ttu-id="c6083-111">EnumModule</span><span class="sxs-lookup"><span data-stu-id="c6083-111">EnumModule</span></span>](ixclrdataprocess-enummodule-method.md)                                               | <span data-ttu-id="c6083-112">枚举此进程的模块。</span><span class="sxs-lookup"><span data-stu-id="c6083-112">Enumerates the modules of this process.</span></span>                                                         |
| [<span data-ttu-id="c6083-113">EndEnumModules</span><span class="sxs-lookup"><span data-stu-id="c6083-113">EndEnumModules</span></span>](ixclrdataprocess-endenummodules-method.md)                                       | <span data-ttu-id="c6083-114">释放模块枚举期间使用的内部迭代器所使用的资源。</span><span class="sxs-lookup"><span data-stu-id="c6083-114">Releases the resources used by internal iterators used during module enumeration.</span></span>               |
| [<span data-ttu-id="c6083-115">StartEnumMethodInstancesByAddress</span><span class="sxs-lookup"><span data-stu-id="c6083-115">StartEnumMethodInstancesByAddress</span></span>](ixclrdataprocess-startenummethodinstancesbyaddress-method.md) | <span data-ttu-id="c6083-116">提供一个句柄，用于枚举从给定地址开始 `AppDomain` 的方法实例。</span><span class="sxs-lookup"><span data-stu-id="c6083-116">Provides a handle to enumerate the method instances of `AppDomain` starting at a given address.</span></span> |
| [<span data-ttu-id="c6083-117">EnumMethodInstanceByAddress</span><span class="sxs-lookup"><span data-stu-id="c6083-117">EnumMethodInstanceByAddress</span></span>](ixclrdataprocess-enummethodinstancebyaddress-method.md)             | <span data-ttu-id="c6083-118">枚举此进程的方法实例（从地址偏移量开始）。</span><span class="sxs-lookup"><span data-stu-id="c6083-118">Enumerates the method instances of this process starting at an address offset.</span></span>                  |
| [<span data-ttu-id="c6083-119">EndEnumMethodInstancesByAddress</span><span class="sxs-lookup"><span data-stu-id="c6083-119">EndEnumMethodInstancesByAddress</span></span>](ixclrdataprocess-endenummethodinstancesbyaddress-method.md)     | <span data-ttu-id="c6083-120">释放实例枚举期间使用的内部迭代器所使用的资源。</span><span class="sxs-lookup"><span data-stu-id="c6083-120">Releases the resources used by internal iterators used during instance enumeration.</span></span>             |

## <a name="remarks"></a><span data-ttu-id="c6083-121">备注</span><span class="sxs-lookup"><span data-stu-id="c6083-121">Remarks</span></span>

<span data-ttu-id="c6083-122">此接口在运行时中存在，不会通过任何标头或库文件公开。</span><span class="sxs-lookup"><span data-stu-id="c6083-122">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="c6083-123">不过，它是一个使用 GUID `5c552ab6-fc09-4cb3-8e36-22fa03c798b7` 派生的 COM 接口，可通过常用的 COM 机制来获取 `IUnknown`。</span><span class="sxs-lookup"><span data-stu-id="c6083-123">However, it's a COM interface that derives from `IUnknown` with GUID `5c552ab6-fc09-4cb3-8e36-22fa03c798b7` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="c6083-124">需求</span><span class="sxs-lookup"><span data-stu-id="c6083-124">Requirements</span></span>

<span data-ttu-id="c6083-125">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c6083-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>   
<span data-ttu-id="c6083-126">**标头：** 内容</span><span class="sxs-lookup"><span data-stu-id="c6083-126">**Header:** None</span></span>  
<span data-ttu-id="c6083-127">**库：** 内容</span><span class="sxs-lookup"><span data-stu-id="c6083-127">**Library:** None</span></span>  
<span data-ttu-id="c6083-128">**.NET Framework 版本：** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="c6083-128">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="c6083-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c6083-129">See also</span></span>

- [<span data-ttu-id="c6083-130">调试</span><span class="sxs-lookup"><span data-stu-id="c6083-130">Debugging</span></span>](index.md)
- [<span data-ttu-id="c6083-131">调试接口</span><span class="sxs-lookup"><span data-stu-id="c6083-131">Debugging Interfaces</span></span>](debugging-interfaces.md)
