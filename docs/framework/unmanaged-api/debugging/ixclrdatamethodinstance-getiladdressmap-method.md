---
title: IXCLRDataMethodInstance::GetILAddressMap 方法
ms.date: 01/16/2019
api.name:
- IXCLRDataMethodInstance::GetILAddressMap Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodInstance::GetILAddressMap Method
helpviewer.keywords:
- IXCLRDataMethodInstance::GetILAddressMap Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 8442d1373ede241d262ab41928fd5d9924ec9c80
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54567186"
---
# <a name="ixclrdatamethodinstancegetiladdressmap-method"></a><span data-ttu-id="7241b-102">IXCLRDataMethodInstance::GetILAddressMap 方法</span><span class="sxs-lookup"><span data-stu-id="7241b-102">IXCLRDataMethodInstance::GetILAddressMap Method</span></span>

<span data-ttu-id="7241b-103">获取到地址映射信息的 IL。</span><span class="sxs-lookup"><span data-stu-id="7241b-103">Gets the IL to address mapping information.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="7241b-104">语法</span><span class="sxs-lookup"><span data-stu-id="7241b-104">Syntax</span></span>

```
HRESULT GetILAddressMap(
    [in] ULONG32                                   mapLen,
    [out] ULONG32                                 *mapNeeded,
    [out, size_is(mapLen)] CLRDATA_IL_ADDRESS_MAP  maps[]
);
```

### <a name="parameters"></a><span data-ttu-id="7241b-105">参数</span><span class="sxs-lookup"><span data-stu-id="7241b-105">Parameters</span></span>

<span data-ttu-id="7241b-106">`mapLen` [in]提供的映射数组的长度。</span><span class="sxs-lookup"><span data-stu-id="7241b-106">`mapLen` [in] The length of the provided maps array.</span></span>

<span data-ttu-id="7241b-107">`mapNeeded` [out]方法需要的映射条目数。</span><span class="sxs-lookup"><span data-stu-id="7241b-107">`mapNeeded` [out] The number of map entries that the method needs.</span></span>

<span data-ttu-id="7241b-108">`maps` [out，size_is(mapLen)]用于存储映射项数组。</span><span class="sxs-lookup"><span data-stu-id="7241b-108">`maps` [out, size_is(mapLen)] The array for storing the map entries.</span></span>

## <a name="remarks"></a><span data-ttu-id="7241b-109">备注</span><span class="sxs-lookup"><span data-stu-id="7241b-109">Remarks</span></span>

<span data-ttu-id="7241b-110">提供的方法属于`IXCLRDataMethodInstance`接口，并对应于虚拟方法表 14 槽。</span><span class="sxs-lookup"><span data-stu-id="7241b-110">The provided method is part of the `IXCLRDataMethodInstance` interface and corresponds to the 14th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="7241b-111">要求</span><span class="sxs-lookup"><span data-stu-id="7241b-111">Requirements</span></span>

<span data-ttu-id="7241b-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7241b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="7241b-113">**标头：** 无</span><span class="sxs-lookup"><span data-stu-id="7241b-113">**Header:** None</span></span>  
<span data-ttu-id="7241b-114">**库：** 无</span><span class="sxs-lookup"><span data-stu-id="7241b-114">**Library:** None</span></span>  
<span data-ttu-id="7241b-115">**.NET Framework 版本：**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="7241b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="7241b-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="7241b-116">See also</span></span>

- [<span data-ttu-id="7241b-117">调试</span><span class="sxs-lookup"><span data-stu-id="7241b-117">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="7241b-118">IXCLRDataMethodInstance 接口</span><span class="sxs-lookup"><span data-stu-id="7241b-118">IXCLRDataMethodInstance Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethodinstance-interface.md)
