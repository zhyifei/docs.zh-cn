---
title: IXCLRDataProcess：： StartEnumMethodInstancesByAddress 方法
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::StartEnumMethodInstancesByAddress Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::StartEnumMethodInstancesByAddress Method
helpviewer.keywords:
- IXCLRDataProcess::StartEnumMethodInstancesByAddress Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 52d533f1c86b34b7b9febade8590e7ab58d8221e
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420729"
---
# <a name="ixclrdataprocessstartenummethodinstancesbyaddress-method"></a><span data-ttu-id="55a6b-102">IXCLRDataProcess：： StartEnumMethodInstancesByAddress 方法</span><span class="sxs-lookup"><span data-stu-id="55a6b-102">IXCLRDataProcess::StartEnumMethodInstancesByAddress Method</span></span>

<span data-ttu-id="55a6b-103">提供用于枚举 `AppDomain` 从给定地址开始的方法实例的句柄。</span><span class="sxs-lookup"><span data-stu-id="55a6b-103">Provides a handle to enumerate the method instances of `AppDomain` starting at a given address.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="55a6b-104">语法</span><span class="sxs-lookup"><span data-stu-id="55a6b-104">Syntax</span></span>

```cpp
HRESULT StartEnumMethodInstancesByAddress(
    [in] CLRDATA_ADDRESS     address,
    [in] IXCLRDataAppDomain *appDomain,
    [out] CLRDATA_ENUM      *handle
);
```

## <a name="parameters"></a><span data-ttu-id="55a6b-105">参数</span><span class="sxs-lookup"><span data-stu-id="55a6b-105">Parameters</span></span>

`address`\
<span data-ttu-id="55a6b-106">中第一个方法实例的地址。</span><span class="sxs-lookup"><span data-stu-id="55a6b-106">[in] The address of the first method instance.</span></span>

`appDomain`\
<span data-ttu-id="55a6b-107">中方法实例的 AppDomain。</span><span class="sxs-lookup"><span data-stu-id="55a6b-107">[in] The AppDomain of the method instances.</span></span>

`handle`\
<span data-ttu-id="55a6b-108">弄枚举方法实例的句柄。</span><span class="sxs-lookup"><span data-stu-id="55a6b-108">[out] A handle for enumerating the method instances.</span></span>

## <a name="remarks"></a><span data-ttu-id="55a6b-109">备注</span><span class="sxs-lookup"><span data-stu-id="55a6b-109">Remarks</span></span>

<span data-ttu-id="55a6b-110">提供的方法是接口的一部分 `IXCLRDataProcess` ，并且对应于虚拟方法表的第28个槽。</span><span class="sxs-lookup"><span data-stu-id="55a6b-110">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 28th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="55a6b-111">要求</span><span class="sxs-lookup"><span data-stu-id="55a6b-111">Requirements</span></span>

<span data-ttu-id="55a6b-112">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="55a6b-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="55a6b-113">**标头：** 内容</span><span class="sxs-lookup"><span data-stu-id="55a6b-113">**Header:** None</span></span>  
<span data-ttu-id="55a6b-114">**库：** 内容</span><span class="sxs-lookup"><span data-stu-id="55a6b-114">**Library:** None</span></span>  
<span data-ttu-id="55a6b-115">**.NET Framework 版本：**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="55a6b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="55a6b-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="55a6b-116">See also</span></span>

- [<span data-ttu-id="55a6b-117">CLRDataSourceType 枚举</span><span class="sxs-lookup"><span data-stu-id="55a6b-117">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="55a6b-118">调试</span><span class="sxs-lookup"><span data-stu-id="55a6b-118">Debugging</span></span>](index.md)
- [<span data-ttu-id="55a6b-119">IXCLRDataProcess 接口</span><span class="sxs-lookup"><span data-stu-id="55a6b-119">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
