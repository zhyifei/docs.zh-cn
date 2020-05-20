---
title: IXCLRDataProcess：： EndEnumMethodInstancesByAddress 方法
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::EndEnumMethodInstancesByAddress Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::EndEnumMethodInstancesByAddress Method
helpviewer.keywords:
- IXCLRDataProcess::EndEnumMethodInstancesByAddress Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 5960d08ccfc09010a20d28a22c2e2f3f5b339c7d
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420820"
---
# <a name="ixclrdataprocessendenummethodinstancesbyaddress-method"></a><span data-ttu-id="ffd88-102">IXCLRDataProcess：： EndEnumMethodInstancesByAddress 方法</span><span class="sxs-lookup"><span data-stu-id="ffd88-102">IXCLRDataProcess::EndEnumMethodInstancesByAddress Method</span></span>

<span data-ttu-id="ffd88-103">释放实例枚举期间使用的内部迭代器所使用的资源。</span><span class="sxs-lookup"><span data-stu-id="ffd88-103">Releases the resources used by internal iterators used during instance enumeration.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="ffd88-104">语法</span><span class="sxs-lookup"><span data-stu-id="ffd88-104">Syntax</span></span>

```cpp
HRESULT EndEnumMethodInstancesByAddress(
    [in] CLRDATA_ENUM handle
);
```

## <a name="parameters"></a><span data-ttu-id="ffd88-105">参数</span><span class="sxs-lookup"><span data-stu-id="ffd88-105">Parameters</span></span>

`handle`\
<span data-ttu-id="ffd88-106">弄枚举方法实例的句柄。</span><span class="sxs-lookup"><span data-stu-id="ffd88-106">[out] A handle for enumerating the method instances.</span></span>

## <a name="remarks"></a><span data-ttu-id="ffd88-107">备注</span><span class="sxs-lookup"><span data-stu-id="ffd88-107">Remarks</span></span>

<span data-ttu-id="ffd88-108">提供的方法是接口的一部分 `IXCLRDataProcess` ，并且对应于虚拟方法表的第30个槽。</span><span class="sxs-lookup"><span data-stu-id="ffd88-108">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 30th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="ffd88-109">要求</span><span class="sxs-lookup"><span data-stu-id="ffd88-109">Requirements</span></span>

<span data-ttu-id="ffd88-110">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ffd88-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="ffd88-111">**标头：** 内容</span><span class="sxs-lookup"><span data-stu-id="ffd88-111">**Header:** None</span></span>  
<span data-ttu-id="ffd88-112">**库：** 内容</span><span class="sxs-lookup"><span data-stu-id="ffd88-112">**Library:** None</span></span>  
<span data-ttu-id="ffd88-113">**.NET Framework 版本：**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="ffd88-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="ffd88-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ffd88-114">See also</span></span>

- [<span data-ttu-id="ffd88-115">CLRDataSourceType 枚举</span><span class="sxs-lookup"><span data-stu-id="ffd88-115">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="ffd88-116">调试</span><span class="sxs-lookup"><span data-stu-id="ffd88-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="ffd88-117">IXCLRDataProcess 接口</span><span class="sxs-lookup"><span data-stu-id="ffd88-117">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
