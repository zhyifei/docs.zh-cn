---
title: IXCLR数据处理：：枚举方法实例按地址方法
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::EnumMethodInstanceByAddress Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::EnumMethodInstanceByAddress Method
helpviewer.keywords:
- IXCLRDataProcess::EnumMethodInstanceByAddress Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: afc5fc377dd45d5e8d4d2d7b3385ca0524df69e1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176651"
---
# <a name="ixclrdataprocessenummethodinstancebyaddress-method"></a><span data-ttu-id="5d4ce-102">IXCLR数据处理：：枚举方法实例按地址方法</span><span class="sxs-lookup"><span data-stu-id="5d4ce-102">IXCLRDataProcess::EnumMethodInstanceByAddress Method</span></span>

<span data-ttu-id="5d4ce-103">枚举从地址偏移开始此过程的方法实例。</span><span class="sxs-lookup"><span data-stu-id="5d4ce-103">Enumerates the method instances of this process starting at an address offset.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="5d4ce-104">语法</span><span class="sxs-lookup"><span data-stu-id="5d4ce-104">Syntax</span></span>

```cpp
HRESULT EnumMethodInstanceByAddress(
    [in] CLRDATA_ENUM              *handle,
    [out] IXCLRDataMethodInstance **method
);
```

## <a name="parameters"></a><span data-ttu-id="5d4ce-105">parameters</span><span class="sxs-lookup"><span data-stu-id="5d4ce-105">Parameters</span></span>

`handle`\
<span data-ttu-id="5d4ce-106">[在]用于枚举方法实例的句柄。</span><span class="sxs-lookup"><span data-stu-id="5d4ce-106">[in] A handle for enumerating the method instances.</span></span>

`mod`\
<span data-ttu-id="5d4ce-107">[出]枚举的方法实例。</span><span class="sxs-lookup"><span data-stu-id="5d4ce-107">[out] The enumerated method instance.</span></span>

## <a name="remarks"></a><span data-ttu-id="5d4ce-108">备注</span><span class="sxs-lookup"><span data-stu-id="5d4ce-108">Remarks</span></span>

<span data-ttu-id="5d4ce-109">提供的方法是接口的一`IXCLRDataProcess`部分，对应于虚拟方法表的第 28 个插槽。</span><span class="sxs-lookup"><span data-stu-id="5d4ce-109">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 28th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="5d4ce-110">要求</span><span class="sxs-lookup"><span data-stu-id="5d4ce-110">Requirements</span></span>

<span data-ttu-id="5d4ce-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5d4ce-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>
<span data-ttu-id="5d4ce-112">**标题：** 无**库：** 无 **.NET 框架版本：**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="5d4ce-112">**Header:** None **Library:** None **.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="5d4ce-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5d4ce-113">See also</span></span>

- [<span data-ttu-id="5d4ce-114">CLRDataSource 类型枚举</span><span class="sxs-lookup"><span data-stu-id="5d4ce-114">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="5d4ce-115">调试</span><span class="sxs-lookup"><span data-stu-id="5d4ce-115">Debugging</span></span>](index.md)
- [<span data-ttu-id="5d4ce-116">IXCLRDataProcess 接口</span><span class="sxs-lookup"><span data-stu-id="5d4ce-116">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
