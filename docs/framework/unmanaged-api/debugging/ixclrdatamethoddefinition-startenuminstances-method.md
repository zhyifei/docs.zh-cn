---
title: IXCLRDataMethodDefinition：： StartEnumInstances 方法
ms.date: 01/16/2019
api.name:
- IXCLRDataMethodDefinition::StartEnumInstances Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodDefinition::StartEnumInstances Method
helpviewer.keywords:
- IXCLRDataMethodDefinition::StartEnumInstances Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: b0c37c666f23f04239ed827246b87c43ee8d5ad9
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420924"
---
# <a name="ixclrdatamethoddefinitionstartenuminstances-method"></a><span data-ttu-id="257fe-102">IXCLRDataMethodDefinition：： StartEnumInstances 方法</span><span class="sxs-lookup"><span data-stu-id="257fe-102">IXCLRDataMethodDefinition::StartEnumInstances Method</span></span>

<span data-ttu-id="257fe-103">为给定的的方法实例枚举提供句柄 `IXCLRDataAppDomain` 。</span><span class="sxs-lookup"><span data-stu-id="257fe-103">Provides a handle for the enumeration of method instances for a given `IXCLRDataAppDomain`.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="257fe-104">语法</span><span class="sxs-lookup"><span data-stu-id="257fe-104">Syntax</span></span>

```cpp
HRESULT StartEnumInstances(
    [in] IXCLRDataAppDomain* appDomain,
    [out] CLRDATA_ENUM *handle
);
```

## <a name="parameters"></a><span data-ttu-id="257fe-105">参数</span><span class="sxs-lookup"><span data-stu-id="257fe-105">Parameters</span></span>

`appDomain`\
<span data-ttu-id="257fe-106">中枚举的 AppDomain。</span><span class="sxs-lookup"><span data-stu-id="257fe-106">[in] An AppDomain for the enumeration.</span></span>

`handle`\
<span data-ttu-id="257fe-107">弄用于枚举实例的句柄。</span><span class="sxs-lookup"><span data-stu-id="257fe-107">[out] A handle for enumerating the instances.</span></span>

## <a name="remarks"></a><span data-ttu-id="257fe-108">备注</span><span class="sxs-lookup"><span data-stu-id="257fe-108">Remarks</span></span>

<span data-ttu-id="257fe-109">提供的方法是接口的一部分 `IXCLRDataMethodDefinition` ，并且对应于虚拟方法表的第5个槽。</span><span class="sxs-lookup"><span data-stu-id="257fe-109">The provided method is part of the `IXCLRDataMethodDefinition` interface and corresponds to the 5th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="257fe-110">要求</span><span class="sxs-lookup"><span data-stu-id="257fe-110">Requirements</span></span>

<span data-ttu-id="257fe-111">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="257fe-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="257fe-112">**标头：** 内容</span><span class="sxs-lookup"><span data-stu-id="257fe-112">**Header:** None</span></span>  
<span data-ttu-id="257fe-113">**库：** 内容</span><span class="sxs-lookup"><span data-stu-id="257fe-113">**Library:** None</span></span>  
<span data-ttu-id="257fe-114">**.NET Framework 版本：**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="257fe-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="257fe-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="257fe-115">See also</span></span>

- [<span data-ttu-id="257fe-116">CLRDataSourceType 枚举</span><span class="sxs-lookup"><span data-stu-id="257fe-116">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="257fe-117">调试</span><span class="sxs-lookup"><span data-stu-id="257fe-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="257fe-118">IXCLRDataMethodDefinition 接口</span><span class="sxs-lookup"><span data-stu-id="257fe-118">IXCLRDataMethodDefinition Interface</span></span>](ixclrdatamethoddefinition-interface.md)
