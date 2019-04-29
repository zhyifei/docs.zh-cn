---
title: IXCLRDataMethodDefinition::EndEnumInstances 方法
ms.date: 01/16/2019
api.name:
- IXCLRDataMethodDefinition::EndEnumInstances Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodDefinition::EndEnumInstances Method
helpviewer.keywords:
- IXCLRDataMethodDefinition::EndEnumInstances Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 28cd15a793d303e1d6e64c52c1d0095e8d619c7b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61789696"
---
# <a name="ixclrdatamethoddefinitionendenuminstances-method"></a><span data-ttu-id="df15c-102">IXCLRDataMethodDefinition::EndEnumInstances 方法</span><span class="sxs-lookup"><span data-stu-id="df15c-102">IXCLRDataMethodDefinition::EndEnumInstances Method</span></span>

<span data-ttu-id="df15c-103">释放使用的内部实例枚举过程中使用的迭代器的资源。</span><span class="sxs-lookup"><span data-stu-id="df15c-103">Releases the resources used by internal iterators used during instance enumeration.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="df15c-104">语法</span><span class="sxs-lookup"><span data-stu-id="df15c-104">Syntax</span></span>

```
HRESULT EndEnumInstances(
    [in] CLRDATA_ENUM handle
);
```

## <a name="parameters"></a><span data-ttu-id="df15c-105">参数</span><span class="sxs-lookup"><span data-stu-id="df15c-105">Parameters</span></span>

`handle`\
<span data-ttu-id="df15c-106">[out]枚举的实例句柄。</span><span class="sxs-lookup"><span data-stu-id="df15c-106">[out] A handle for enumerating the instances.</span></span>

## <a name="remarks"></a><span data-ttu-id="df15c-107">备注</span><span class="sxs-lookup"><span data-stu-id="df15c-107">Remarks</span></span>

<span data-ttu-id="df15c-108">提供的方法属于`IXCLRDataMethodDefinition`接口，并对应于虚拟方法表的第五个槽。</span><span class="sxs-lookup"><span data-stu-id="df15c-108">The provided method is part of the `IXCLRDataMethodDefinition` interface and corresponds to the fifth slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="df15c-109">要求</span><span class="sxs-lookup"><span data-stu-id="df15c-109">Requirements</span></span>

<span data-ttu-id="df15c-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="df15c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="df15c-111">**标头：** None</span><span class="sxs-lookup"><span data-stu-id="df15c-111">**Header:** None</span></span>  
<span data-ttu-id="df15c-112">**库：** None</span><span class="sxs-lookup"><span data-stu-id="df15c-112">**Library:** None</span></span>  
<span data-ttu-id="df15c-113">**.NET Framework 版本：**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="df15c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="df15c-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="df15c-114">See also</span></span>

- [<span data-ttu-id="df15c-115">调试</span><span class="sxs-lookup"><span data-stu-id="df15c-115">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="df15c-116">IXCLRDataMethodDefinition 接口</span><span class="sxs-lookup"><span data-stu-id="df15c-116">IXCLRDataMethodDefinition Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethoddefinition-interface.md)
