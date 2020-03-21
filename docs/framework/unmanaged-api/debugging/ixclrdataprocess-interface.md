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
ms.openlocfilehash: e7e53615e38d0ab76f9e7c0a753be3c13780057d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178374"
---
# <a name="ixclrdataprocess-interface"></a><span data-ttu-id="3846e-102">IXCLRDataProcess 接口</span><span class="sxs-lookup"><span data-stu-id="3846e-102">IXCLRDataProcess Interface</span></span>

<span data-ttu-id="3846e-103">提供了查询有关进程的信息的方法。</span><span class="sxs-lookup"><span data-stu-id="3846e-103">Provides methods for querying information about a process.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="3846e-104">方法</span><span class="sxs-lookup"><span data-stu-id="3846e-104">Methods</span></span>

| <span data-ttu-id="3846e-105">方法</span><span class="sxs-lookup"><span data-stu-id="3846e-105">Method</span></span>                                                                                                                                               | <span data-ttu-id="3846e-106">说明</span><span class="sxs-lookup"><span data-stu-id="3846e-106">Description</span></span>                                                                                     |
| ---------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| [<span data-ttu-id="3846e-107">GetAppDomainByUniqueId</span><span class="sxs-lookup"><span data-stu-id="3846e-107">GetAppDomainByUniqueId</span></span>](ixclrdataprocess-getappdomainbyuniqueid-method.md)                       | <span data-ttu-id="3846e-108">通过进程`AppDomain`的唯一 ID 获取 进程中的 。</span><span class="sxs-lookup"><span data-stu-id="3846e-108">Gets an `AppDomain` in a process by its unique id.</span></span>                                              |
| [<span data-ttu-id="3846e-109">StartEnumModules</span><span class="sxs-lookup"><span data-stu-id="3846e-109">StartEnumModules</span></span>](ixclrdataprocess-startenummodules-method.md)                                   | <span data-ttu-id="3846e-110">提供一个句柄来枚举进程的模块。</span><span class="sxs-lookup"><span data-stu-id="3846e-110">Provides a handle to enumerate the modules of a process.</span></span>                                        |
| [<span data-ttu-id="3846e-111">EnumModule</span><span class="sxs-lookup"><span data-stu-id="3846e-111">EnumModule</span></span>](ixclrdataprocess-enummodule-method.md)                                               | <span data-ttu-id="3846e-112">枚举此过程的模块。</span><span class="sxs-lookup"><span data-stu-id="3846e-112">Enumerates the modules of this process.</span></span>                                                         |
| [<span data-ttu-id="3846e-113">EndEnumModules</span><span class="sxs-lookup"><span data-stu-id="3846e-113">EndEnumModules</span></span>](ixclrdataprocess-endenummodules-method.md)                                       | <span data-ttu-id="3846e-114">释放模块枚举期间使用的内部迭代器使用的资源。</span><span class="sxs-lookup"><span data-stu-id="3846e-114">Releases the resources used by internal iterators used during module enumeration.</span></span>               |
| [<span data-ttu-id="3846e-115">StartEnumMethodInstancesByAddress</span><span class="sxs-lookup"><span data-stu-id="3846e-115">StartEnumMethodInstancesByAddress</span></span>](ixclrdataprocess-startenummethodinstancesbyaddress-method.md) | <span data-ttu-id="3846e-116">提供一个句柄来枚举从给定地址`AppDomain`开始的方法实例。</span><span class="sxs-lookup"><span data-stu-id="3846e-116">Provides a handle to enumerate the method instances of `AppDomain` starting at a given address.</span></span> |
| [<span data-ttu-id="3846e-117">EnumMethodInstanceByAddress</span><span class="sxs-lookup"><span data-stu-id="3846e-117">EnumMethodInstanceByAddress</span></span>](ixclrdataprocess-enummethodinstancebyaddress-method.md)             | <span data-ttu-id="3846e-118">枚举从地址偏移开始此过程的方法实例。</span><span class="sxs-lookup"><span data-stu-id="3846e-118">Enumerates the method instances of this process starting at an address offset.</span></span>                  |
| [<span data-ttu-id="3846e-119">EndEnumMethodInstancesByAddress</span><span class="sxs-lookup"><span data-stu-id="3846e-119">EndEnumMethodInstancesByAddress</span></span>](ixclrdataprocess-endenummethodinstancesbyaddress-method.md)     | <span data-ttu-id="3846e-120">释放实例枚举期间使用的内部迭代器使用的资源。</span><span class="sxs-lookup"><span data-stu-id="3846e-120">Releases the resources used by internal iterators used during instance enumeration.</span></span>             |

## <a name="remarks"></a><span data-ttu-id="3846e-121">备注</span><span class="sxs-lookup"><span data-stu-id="3846e-121">Remarks</span></span>

<span data-ttu-id="3846e-122">此接口位于运行时内，不会通过任何标头或库文件公开。</span><span class="sxs-lookup"><span data-stu-id="3846e-122">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="3846e-123">但是，它是一个 COM 接口，派生自`IUnknown`GUID，`5c552ab6-fc09-4cb3-8e36-22fa03c798b7`可通过通常的 COM 机制获得。</span><span class="sxs-lookup"><span data-stu-id="3846e-123">However, it's a COM interface that derives from `IUnknown` with GUID `5c552ab6-fc09-4cb3-8e36-22fa03c798b7` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="3846e-124">要求</span><span class="sxs-lookup"><span data-stu-id="3846e-124">Requirements</span></span>

<span data-ttu-id="3846e-125">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3846e-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>
<span data-ttu-id="3846e-126">**标题：** 没有</span><span class="sxs-lookup"><span data-stu-id="3846e-126">**Header:** None</span></span>  
<span data-ttu-id="3846e-127">**库：** 没有</span><span class="sxs-lookup"><span data-stu-id="3846e-127">**Library:** None</span></span>  
<span data-ttu-id="3846e-128">**.NET 框架版本：**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="3846e-128">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="3846e-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3846e-129">See also</span></span>

- [<span data-ttu-id="3846e-130">调试</span><span class="sxs-lookup"><span data-stu-id="3846e-130">Debugging</span></span>](index.md)
- [<span data-ttu-id="3846e-131">调试接口</span><span class="sxs-lookup"><span data-stu-id="3846e-131">Debugging Interfaces</span></span>](debugging-interfaces.md)
