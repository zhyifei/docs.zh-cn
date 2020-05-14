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
ms.openlocfilehash: e28fa73300e147ac07a2d325fbf517480bb73797
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "83394939"
---
# <a name="ixclrdataprocessstartenummethodinstancesbyaddress-method"></a><span data-ttu-id="a81f9-102">IXCLRDataProcess：： StartEnumMethodInstancesByAddress 方法</span><span class="sxs-lookup"><span data-stu-id="a81f9-102">IXCLRDataProcess::StartEnumMethodInstancesByAddress Method</span></span>

<span data-ttu-id="a81f9-103">提供用于枚举 `AppDomain` 从给定地址开始的方法实例的句柄。</span><span class="sxs-lookup"><span data-stu-id="a81f9-103">Provides a handle to enumerate the method instances of `AppDomain` starting at a given address.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="a81f9-104">语法</span><span class="sxs-lookup"><span data-stu-id="a81f9-104">Syntax</span></span>

```cpp
HRESULT StartEnumMethodInstancesByAddress(
    [in] CLRDATA_ADDRESS     address,
    [in] IXCLRDataAppDomain *appDomain,
    [out] CLRDATA_ENUM      *handle
);
```

## <a name="parameters"></a><span data-ttu-id="a81f9-105">参数</span><span class="sxs-lookup"><span data-stu-id="a81f9-105">Parameters</span></span>

`address`\
<span data-ttu-id="a81f9-106">中第一个方法实例的地址。</span><span class="sxs-lookup"><span data-stu-id="a81f9-106">[in] The address of the first method instance.</span></span>

`appDomain`\
<span data-ttu-id="a81f9-107">中方法实例的 AppDomain。</span><span class="sxs-lookup"><span data-stu-id="a81f9-107">[in] The AppDomain of the method instances.</span></span>

`handle`\
<span data-ttu-id="a81f9-108">弄枚举方法实例的句柄。</span><span class="sxs-lookup"><span data-stu-id="a81f9-108">[out] A handle for enumerating the method instances.</span></span>

## <a name="remarks"></a><span data-ttu-id="a81f9-109">备注</span><span class="sxs-lookup"><span data-stu-id="a81f9-109">Remarks</span></span>

<span data-ttu-id="a81f9-110">提供的方法是接口的一部分 `IXCLRDataProcess` ，并且对应于虚拟方法表的第28个槽。</span><span class="sxs-lookup"><span data-stu-id="a81f9-110">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 28th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="a81f9-111">要求</span><span class="sxs-lookup"><span data-stu-id="a81f9-111">Requirements</span></span>

<span data-ttu-id="a81f9-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a81f9-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="a81f9-113">**标头：** 内容</span><span class="sxs-lookup"><span data-stu-id="a81f9-113">**Header:** None</span></span>  
<span data-ttu-id="a81f9-114">**库：** 内容</span><span class="sxs-lookup"><span data-stu-id="a81f9-114">**Library:** None</span></span>  
<span data-ttu-id="a81f9-115">**.NET Framework 版本：**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="a81f9-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="a81f9-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="a81f9-116">See also</span></span>

- [<span data-ttu-id="a81f9-117">CLRDataSourceType 枚举</span><span class="sxs-lookup"><span data-stu-id="a81f9-117">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="a81f9-118">调试</span><span class="sxs-lookup"><span data-stu-id="a81f9-118">Debugging</span></span>](index.md)
- [<span data-ttu-id="a81f9-119">IXCLRDataProcess 接口</span><span class="sxs-lookup"><span data-stu-id="a81f9-119">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
