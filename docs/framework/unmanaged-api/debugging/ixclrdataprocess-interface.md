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
ms.openlocfilehash: ff74a7acb5cc84c177f083c19402cd78977aeab5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54680369"
---
# <a name="ixclrdataprocess-interface"></a><span data-ttu-id="0e7a0-102">IXCLRDataProcess 接口</span><span class="sxs-lookup"><span data-stu-id="0e7a0-102">IXCLRDataProcess Interface</span></span>

<span data-ttu-id="0e7a0-103">提供用于查询有关进程的信息的方法。</span><span class="sxs-lookup"><span data-stu-id="0e7a0-103">Provides methods for querying information about a process.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="0e7a0-104">方法</span><span class="sxs-lookup"><span data-stu-id="0e7a0-104">Methods</span></span>

| <span data-ttu-id="0e7a0-105">方法</span><span class="sxs-lookup"><span data-stu-id="0e7a0-105">Method</span></span>                                                                                                                                               | <span data-ttu-id="0e7a0-106">描述</span><span class="sxs-lookup"><span data-stu-id="0e7a0-106">Description</span></span>                                                                                     |
| ---------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| [<span data-ttu-id="0e7a0-107">GetAppDomainByUniqueId</span><span class="sxs-lookup"><span data-stu-id="0e7a0-107">GetAppDomainByUniqueId</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdataprocess-getappdomainbyuniqueid-method.md)                       | <span data-ttu-id="0e7a0-108">获取`AppDomain`由其唯一 id 的进程中。</span><span class="sxs-lookup"><span data-stu-id="0e7a0-108">Gets an `AppDomain` in a process by its unique id.</span></span>                                              |
| [<span data-ttu-id="0e7a0-109">StartEnumModules</span><span class="sxs-lookup"><span data-stu-id="0e7a0-109">StartEnumModules</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdataprocess-startenummodules-method.md)                                   | <span data-ttu-id="0e7a0-110">提供要枚举的进程的模块的句柄。</span><span class="sxs-lookup"><span data-stu-id="0e7a0-110">Provides a handle to enumerate the modules of a process.</span></span>                                        |
| [<span data-ttu-id="0e7a0-111">EnumModule</span><span class="sxs-lookup"><span data-stu-id="0e7a0-111">EnumModule</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdataprocess-enummodule-method.md)                                               | <span data-ttu-id="0e7a0-112">枚举此进程的模块。</span><span class="sxs-lookup"><span data-stu-id="0e7a0-112">Enumerates the modules of this process.</span></span>                                                         |
| [<span data-ttu-id="0e7a0-113">EndEnumModules</span><span class="sxs-lookup"><span data-stu-id="0e7a0-113">EndEnumModules</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdataprocess-endenummodules-method.md)                                       | <span data-ttu-id="0e7a0-114">释放由模块枚举过程中使用的内部迭代器使用的资源。</span><span class="sxs-lookup"><span data-stu-id="0e7a0-114">Releases the resources used by internal iterators used during module enumeration.</span></span>               |
| [<span data-ttu-id="0e7a0-115">StartEnumMethodInstancesByAddress</span><span class="sxs-lookup"><span data-stu-id="0e7a0-115">StartEnumMethodInstancesByAddress</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdataprocess-startenummethodinstancesbyaddress-method.md) | <span data-ttu-id="0e7a0-116">提供要枚举的方法实例的句柄`AppDomain`给定地址开始。</span><span class="sxs-lookup"><span data-stu-id="0e7a0-116">Provides a handle to enumerate the method instances of `AppDomain` starting at a given address.</span></span> |
| [<span data-ttu-id="0e7a0-117">EnumMethodInstanceByAddress</span><span class="sxs-lookup"><span data-stu-id="0e7a0-117">EnumMethodInstanceByAddress</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdataprocess-enummethodinstancebyaddress-method.md)             | <span data-ttu-id="0e7a0-118">枚举的方法实例的地址偏移量开始此过程。</span><span class="sxs-lookup"><span data-stu-id="0e7a0-118">Enumerates the method instances of this process starting at an address offset.</span></span>                  |
| [<span data-ttu-id="0e7a0-119">EndEnumMethodInstancesByAddress</span><span class="sxs-lookup"><span data-stu-id="0e7a0-119">EndEnumMethodInstancesByAddress</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdataprocess-endenummethodinstancesbyaddress-method.md)     | <span data-ttu-id="0e7a0-120">释放使用的内部实例枚举过程中使用的迭代器的资源。</span><span class="sxs-lookup"><span data-stu-id="0e7a0-120">Releases the resources used by internal iterators used during instance enumeration.</span></span>             |

## <a name="remarks"></a><span data-ttu-id="0e7a0-121">备注</span><span class="sxs-lookup"><span data-stu-id="0e7a0-121">Remarks</span></span>

<span data-ttu-id="0e7a0-122">此接口存在于运行时内并不通过任何标头或库文件公开。</span><span class="sxs-lookup"><span data-stu-id="0e7a0-122">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="0e7a0-123">但是，它是一个 COM 接口派生`IUnknown`具有 GUID `5c552ab6-fc09-4cb3-8e36-22fa03c798b7` ，可以通过常用的 COM 机制获取。</span><span class="sxs-lookup"><span data-stu-id="0e7a0-123">However, it's a COM interface that derives from `IUnknown` with GUID `5c552ab6-fc09-4cb3-8e36-22fa03c798b7` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="0e7a0-124">要求</span><span class="sxs-lookup"><span data-stu-id="0e7a0-124">Requirements</span></span>

<span data-ttu-id="0e7a0-125">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0e7a0-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>   
<span data-ttu-id="0e7a0-126">**标头：** 无</span><span class="sxs-lookup"><span data-stu-id="0e7a0-126">**Header:** None</span></span>  
<span data-ttu-id="0e7a0-127">**库：** 无</span><span class="sxs-lookup"><span data-stu-id="0e7a0-127">**Library:** None</span></span>  
<span data-ttu-id="0e7a0-128">**.NET Framework 版本：**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="0e7a0-128">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="0e7a0-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="0e7a0-129">See also</span></span>

- [<span data-ttu-id="0e7a0-130">调试</span><span class="sxs-lookup"><span data-stu-id="0e7a0-130">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="0e7a0-131">调试接口</span><span class="sxs-lookup"><span data-stu-id="0e7a0-131">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
