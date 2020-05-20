---
title: IXCLRDataMethodDefinition：： EnumInstance 方法
ms.date: 01/16/2019
api.name:
- IXCLRDataMethodDefinition::EnumInstance Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodDefinition::EnumInstance Method
helpviewer.keywords:
- IXCLRDataMethodDefinition::EnumInstance Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: ae1ef2a3c8cf9e042ab9ab233ed993f8e36b2fce
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420937"
---
# <a name="ixclrdatamethoddefinitionenuminstance-method"></a><span data-ttu-id="a86c7-102">IXCLRDataMethodDefinition：： EnumInstance 方法</span><span class="sxs-lookup"><span data-stu-id="a86c7-102">IXCLRDataMethodDefinition::EnumInstance Method</span></span>

<span data-ttu-id="a86c7-103">枚举此方法定义的实例。</span><span class="sxs-lookup"><span data-stu-id="a86c7-103">Enumerates the instances of this method definition.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="a86c7-104">语法</span><span class="sxs-lookup"><span data-stu-id="a86c7-104">Syntax</span></span>

```cpp
HRESULT EnumInstance(
    [in, out] CLRDATA_ENUM         *handle,
    [out] IXCLRDataMethodInstance **instance
);
```

## <a name="parameters"></a><span data-ttu-id="a86c7-105">参数</span><span class="sxs-lookup"><span data-stu-id="a86c7-105">Parameters</span></span>

`handle`\
<span data-ttu-id="a86c7-106">[in，out]用于枚举实例的句柄。</span><span class="sxs-lookup"><span data-stu-id="a86c7-106">[in, out] A handle for enumerating the instances.</span></span>

`instance`\
<span data-ttu-id="a86c7-107">弄枚举的实例。</span><span class="sxs-lookup"><span data-stu-id="a86c7-107">[out] The enumerated instance.</span></span>

## <a name="remarks"></a><span data-ttu-id="a86c7-108">备注</span><span class="sxs-lookup"><span data-stu-id="a86c7-108">Remarks</span></span>

<span data-ttu-id="a86c7-109">提供的方法是接口的一部分 `IXCLRDataMethodDefinition` ，并对应于虚拟方法表的第六个槽。</span><span class="sxs-lookup"><span data-stu-id="a86c7-109">The provided method is part of the `IXCLRDataMethodDefinition` interface and corresponds to the 6th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="a86c7-110">要求</span><span class="sxs-lookup"><span data-stu-id="a86c7-110">Requirements</span></span>

<span data-ttu-id="a86c7-111">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a86c7-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="a86c7-112">**标头：** 内容</span><span class="sxs-lookup"><span data-stu-id="a86c7-112">**Header:** None</span></span>  
<span data-ttu-id="a86c7-113">**库：** 内容</span><span class="sxs-lookup"><span data-stu-id="a86c7-113">**Library:** None</span></span>  
<span data-ttu-id="a86c7-114">**.NET Framework 版本：**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="a86c7-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="a86c7-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a86c7-115">See also</span></span>

- [<span data-ttu-id="a86c7-116">CLRDataSourceType 枚举</span><span class="sxs-lookup"><span data-stu-id="a86c7-116">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="a86c7-117">调试</span><span class="sxs-lookup"><span data-stu-id="a86c7-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="a86c7-118">IXCLRDataMethodDefinition 接口</span><span class="sxs-lookup"><span data-stu-id="a86c7-118">IXCLRDataMethodDefinition Interface</span></span>](ixclrdatamethoddefinition-interface.md)
- [<span data-ttu-id="a86c7-119">IXCLRDataMethodInstance 接口</span><span class="sxs-lookup"><span data-stu-id="a86c7-119">IXCLRDataMethodInstance Interface</span></span>](ixclrdatamethodinstance-interface.md)
