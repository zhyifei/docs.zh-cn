---
title: IXCLRDataMethodDefinition：： EndEnumInstances 方法
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
ms.openlocfilehash: 7271c9594a679af205c404f59ff6731821aa0acf
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420989"
---
# <a name="ixclrdatamethoddefinitionendenuminstances-method"></a><span data-ttu-id="2d61b-102">IXCLRDataMethodDefinition：： EndEnumInstances 方法</span><span class="sxs-lookup"><span data-stu-id="2d61b-102">IXCLRDataMethodDefinition::EndEnumInstances Method</span></span>

<span data-ttu-id="2d61b-103">释放实例枚举期间使用的内部迭代器所使用的资源。</span><span class="sxs-lookup"><span data-stu-id="2d61b-103">Releases the resources used by internal iterators used during instance enumeration.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="2d61b-104">语法</span><span class="sxs-lookup"><span data-stu-id="2d61b-104">Syntax</span></span>

```cpp
HRESULT EndEnumInstances(
    [in] CLRDATA_ENUM handle
);
```

## <a name="parameters"></a><span data-ttu-id="2d61b-105">参数</span><span class="sxs-lookup"><span data-stu-id="2d61b-105">Parameters</span></span>

`handle`\
<span data-ttu-id="2d61b-106">弄用于枚举实例的句柄。</span><span class="sxs-lookup"><span data-stu-id="2d61b-106">[out] A handle for enumerating the instances.</span></span>

## <a name="remarks"></a><span data-ttu-id="2d61b-107">备注</span><span class="sxs-lookup"><span data-stu-id="2d61b-107">Remarks</span></span>

<span data-ttu-id="2d61b-108">提供的方法是接口的一部分 `IXCLRDataMethodDefinition` ，并且对应于虚拟方法表的第7个槽。</span><span class="sxs-lookup"><span data-stu-id="2d61b-108">The provided method is part of the `IXCLRDataMethodDefinition` interface and corresponds to the 7th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="2d61b-109">要求</span><span class="sxs-lookup"><span data-stu-id="2d61b-109">Requirements</span></span>

<span data-ttu-id="2d61b-110">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2d61b-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="2d61b-111">**标头：** 内容</span><span class="sxs-lookup"><span data-stu-id="2d61b-111">**Header:** None</span></span>  
<span data-ttu-id="2d61b-112">**库：** 内容</span><span class="sxs-lookup"><span data-stu-id="2d61b-112">**Library:** None</span></span>  
<span data-ttu-id="2d61b-113">**.NET Framework 版本：**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="2d61b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="2d61b-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2d61b-114">See also</span></span>

- [<span data-ttu-id="2d61b-115">调试</span><span class="sxs-lookup"><span data-stu-id="2d61b-115">Debugging</span></span>](index.md)
- [<span data-ttu-id="2d61b-116">IXCLRDataMethodDefinition 接口</span><span class="sxs-lookup"><span data-stu-id="2d61b-116">IXCLRDataMethodDefinition Interface</span></span>](ixclrdatamethoddefinition-interface.md)
