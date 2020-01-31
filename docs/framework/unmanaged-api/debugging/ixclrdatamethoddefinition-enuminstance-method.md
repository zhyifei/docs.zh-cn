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
ms.openlocfilehash: b6393d7fa4853c230203521e665bbe89d7b228e2
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790432"
---
# <a name="ixclrdatamethoddefinitionenuminstance-method"></a><span data-ttu-id="95df5-102">IXCLRDataMethodDefinition：： EnumInstance 方法</span><span class="sxs-lookup"><span data-stu-id="95df5-102">IXCLRDataMethodDefinition::EnumInstance Method</span></span>

<span data-ttu-id="95df5-103">枚举此方法定义的实例。</span><span class="sxs-lookup"><span data-stu-id="95df5-103">Enumerates the instances of this method definition.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="95df5-104">语法</span><span class="sxs-lookup"><span data-stu-id="95df5-104">Syntax</span></span>

```cpp
HRESULT EnumInstance(
    [in, out] CLRDATA_ENUM         *handle,
    [out] IXCLRDataMethodInstance **instance
);
```

## <a name="parameters"></a><span data-ttu-id="95df5-105">参数</span><span class="sxs-lookup"><span data-stu-id="95df5-105">Parameters</span></span>

`handle`\
<span data-ttu-id="95df5-106">[in，out]用于枚举实例的句柄。</span><span class="sxs-lookup"><span data-stu-id="95df5-106">[in, out] A handle for enumerating the instances.</span></span>

`instance`\
<span data-ttu-id="95df5-107">弄枚举的实例。</span><span class="sxs-lookup"><span data-stu-id="95df5-107">[out] The enumerated instance.</span></span>

## <a name="remarks"></a><span data-ttu-id="95df5-108">备注</span><span class="sxs-lookup"><span data-stu-id="95df5-108">Remarks</span></span>

<span data-ttu-id="95df5-109">提供的方法是 `IXCLRDataMethodDefinition` 接口的一部分，并且对应于虚拟方法表的第四个槽。</span><span class="sxs-lookup"><span data-stu-id="95df5-109">The provided method is part of the `IXCLRDataMethodDefinition` interface and corresponds to the fourth slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="95df5-110">需求</span><span class="sxs-lookup"><span data-stu-id="95df5-110">Requirements</span></span>

<span data-ttu-id="95df5-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="95df5-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="95df5-112">**标头：** 内容</span><span class="sxs-lookup"><span data-stu-id="95df5-112">**Header:** None</span></span>  
<span data-ttu-id="95df5-113">**库：** 内容</span><span class="sxs-lookup"><span data-stu-id="95df5-113">**Library:** None</span></span>  
<span data-ttu-id="95df5-114">**.NET Framework 版本：** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="95df5-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="95df5-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="95df5-115">See also</span></span>

- [<span data-ttu-id="95df5-116">CLRDataSourceType 枚举</span><span class="sxs-lookup"><span data-stu-id="95df5-116">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="95df5-117">调试</span><span class="sxs-lookup"><span data-stu-id="95df5-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="95df5-118">IXCLRDataMethodDefinition 接口</span><span class="sxs-lookup"><span data-stu-id="95df5-118">IXCLRDataMethodDefinition Interface</span></span>](ixclrdatamethoddefinition-interface.md)
- [<span data-ttu-id="95df5-119">IXCLRDataMethodInstance 接口</span><span class="sxs-lookup"><span data-stu-id="95df5-119">IXCLRDataMethodInstance Interface</span></span>](ixclrdatamethodinstance-interface.md)
