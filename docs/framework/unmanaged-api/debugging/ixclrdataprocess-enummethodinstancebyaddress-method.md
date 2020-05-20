---
title: IXCLRDataProcess：： EnumMethodInstanceByAddress 方法
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
ms.openlocfilehash: 142099ae5cf9637cc28e8c82aabcd831cc8f0f52
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420794"
---
# <a name="ixclrdataprocessenummethodinstancebyaddress-method"></a><span data-ttu-id="7d662-102">IXCLRDataProcess：： EnumMethodInstanceByAddress 方法</span><span class="sxs-lookup"><span data-stu-id="7d662-102">IXCLRDataProcess::EnumMethodInstanceByAddress Method</span></span>

<span data-ttu-id="7d662-103">枚举此进程的方法实例（从地址偏移量开始）。</span><span class="sxs-lookup"><span data-stu-id="7d662-103">Enumerates the method instances of this process starting at an address offset.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="7d662-104">语法</span><span class="sxs-lookup"><span data-stu-id="7d662-104">Syntax</span></span>

```cpp
HRESULT EnumMethodInstanceByAddress(
    [in] CLRDATA_ENUM              *handle,
    [out] IXCLRDataMethodInstance **method
);
```

## <a name="parameters"></a><span data-ttu-id="7d662-105">参数</span><span class="sxs-lookup"><span data-stu-id="7d662-105">Parameters</span></span>

`handle`\
<span data-ttu-id="7d662-106">中枚举方法实例的句柄。</span><span class="sxs-lookup"><span data-stu-id="7d662-106">[in] A handle for enumerating the method instances.</span></span>

`mod`\
<span data-ttu-id="7d662-107">弄枚举的方法实例。</span><span class="sxs-lookup"><span data-stu-id="7d662-107">[out] The enumerated method instance.</span></span>

## <a name="remarks"></a><span data-ttu-id="7d662-108">备注</span><span class="sxs-lookup"><span data-stu-id="7d662-108">Remarks</span></span>

<span data-ttu-id="7d662-109">提供的方法是接口的一部分 `IXCLRDataProcess` ，并且对应于虚拟方法表的第29个槽。</span><span class="sxs-lookup"><span data-stu-id="7d662-109">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 29th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="7d662-110">要求</span><span class="sxs-lookup"><span data-stu-id="7d662-110">Requirements</span></span>

<span data-ttu-id="7d662-111">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7d662-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>
<span data-ttu-id="7d662-112">**标头：** 无**库：** 无 **.NET Framework 版本：**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="7d662-112">**Header:** None **Library:** None **.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="7d662-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7d662-113">See also</span></span>

- [<span data-ttu-id="7d662-114">CLRDataSourceType 枚举</span><span class="sxs-lookup"><span data-stu-id="7d662-114">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="7d662-115">调试</span><span class="sxs-lookup"><span data-stu-id="7d662-115">Debugging</span></span>](index.md)
- [<span data-ttu-id="7d662-116">IXCLRDataProcess 接口</span><span class="sxs-lookup"><span data-stu-id="7d662-116">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
