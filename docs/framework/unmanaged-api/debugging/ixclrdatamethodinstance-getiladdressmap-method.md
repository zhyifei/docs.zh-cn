---
title: IXCLRDataMethodInstance：： GetILAddressMap 方法
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
ms.openlocfilehash: 7c4dcf59ce159434d5012120043f5bb548d49731
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396821"
---
# <a name="ixclrdatamethodinstancegetiladdressmap-method"></a><span data-ttu-id="707ec-102">IXCLRDataMethodInstance：： GetILAddressMap 方法</span><span class="sxs-lookup"><span data-stu-id="707ec-102">IXCLRDataMethodInstance::GetILAddressMap Method</span></span>

<span data-ttu-id="707ec-103">获取用于寻址映射信息的 IL。</span><span class="sxs-lookup"><span data-stu-id="707ec-103">Gets the IL to address mapping information.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="707ec-104">语法</span><span class="sxs-lookup"><span data-stu-id="707ec-104">Syntax</span></span>

```cpp
HRESULT GetILAddressMap(
    [in] ULONG32                                   mapLen,
    [out] ULONG32                                 *mapNeeded,
    [out, size_is(mapLen)] CLRDATA_IL_ADDRESS_MAP  maps[]
);
```

## <a name="parameters"></a><span data-ttu-id="707ec-105">参数</span><span class="sxs-lookup"><span data-stu-id="707ec-105">Parameters</span></span>

`mapLen`\
<span data-ttu-id="707ec-106">中所提供的映射数组的长度。</span><span class="sxs-lookup"><span data-stu-id="707ec-106">[in] The length of the provided maps array.</span></span>

`mapNeeded`\
<span data-ttu-id="707ec-107">弄该方法所需的映射项的数目。</span><span class="sxs-lookup"><span data-stu-id="707ec-107">[out] The number of map entries that the method needs.</span></span>

`maps`\
<span data-ttu-id="707ec-108">[out，size_is （mapLen）]用于存储映射项的数组。</span><span class="sxs-lookup"><span data-stu-id="707ec-108">[out, size_is(mapLen)] The array for storing the map entries.</span></span>

## <a name="remarks"></a><span data-ttu-id="707ec-109">备注</span><span class="sxs-lookup"><span data-stu-id="707ec-109">Remarks</span></span>

<span data-ttu-id="707ec-110">提供的方法是接口的一部分 `IXCLRDataMethodInstance` ，并且对应于虚拟方法表的第15个槽。</span><span class="sxs-lookup"><span data-stu-id="707ec-110">The provided method is part of the `IXCLRDataMethodInstance` interface and corresponds to the 15th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="707ec-111">要求</span><span class="sxs-lookup"><span data-stu-id="707ec-111">Requirements</span></span>

<span data-ttu-id="707ec-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="707ec-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="707ec-113">**标头：** 内容</span><span class="sxs-lookup"><span data-stu-id="707ec-113">**Header:** None</span></span>  
<span data-ttu-id="707ec-114">**库：** 内容</span><span class="sxs-lookup"><span data-stu-id="707ec-114">**Library:** None</span></span>  
<span data-ttu-id="707ec-115">**.NET Framework 版本：**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="707ec-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="707ec-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="707ec-116">See also</span></span>

- [<span data-ttu-id="707ec-117">调试</span><span class="sxs-lookup"><span data-stu-id="707ec-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="707ec-118">IXCLRDataMethodInstance 接口</span><span class="sxs-lookup"><span data-stu-id="707ec-118">IXCLRDataMethodInstance Interface</span></span>](ixclrdatamethodinstance-interface.md)
