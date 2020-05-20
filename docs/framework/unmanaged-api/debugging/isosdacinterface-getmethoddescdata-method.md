---
title: ISOSDacInterface：： GetMethodDescData 方法
ms.date: 01/16/2019
api.name:
- ISOSDacInterface::GetMethodDescData Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- ISOSDacInterface::GetMethodDescData Method
helpviewer.keywords:
- ISOSDacInterface::GetMethodDescData Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 105149d0abf312c33a8498e7428e3a8b23d6ae7d
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421015"
---
# <a name="isosdacinterfacegetmethoddescdata-method"></a><span data-ttu-id="7fccc-102">ISOSDacInterface：： GetMethodDescData 方法</span><span class="sxs-lookup"><span data-stu-id="7fccc-102">ISOSDacInterface::GetMethodDescData Method</span></span>

<span data-ttu-id="7fccc-103">获取给定 MethodDesc 指针的数据。</span><span class="sxs-lookup"><span data-stu-id="7fccc-103">Gets the data for the given MethodDesc pointer.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="7fccc-104">语法</span><span class="sxs-lookup"><span data-stu-id="7fccc-104">Syntax</span></span>

```cpp
HRESULT GetMethodDescData(
    CLRDATA_ADDRESS            methodDesc,
    CLRDATA_ADDRESS            ip,
    DacpMethodDescData *data,
    ULONG                      cRevertedRejitVersions,
    DacpReJitData      *rgRevertedRejitData,
    void                      *pcNeededRevertedRejitData
);
```

## <a name="parameters"></a><span data-ttu-id="7fccc-105">参数</span><span class="sxs-lookup"><span data-stu-id="7fccc-105">Parameters</span></span>

`methodDesc`\
<span data-ttu-id="7fccc-106">中MethodDesc 的地址。</span><span class="sxs-lookup"><span data-stu-id="7fccc-106">[in] The address of the MethodDesc.</span></span>

`ip`\
<span data-ttu-id="7fccc-107">中方法的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="7fccc-107">[in] The IP address of the method.</span></span>

`data`\
<span data-ttu-id="7fccc-108">弄与 MethodDesc 关联的、从内部 Api 返回的数据。</span><span class="sxs-lookup"><span data-stu-id="7fccc-108">[out] The data associated with the MethodDesc as returned from the internal APIs.</span></span>

`cRevertedRejitVersions`\
<span data-ttu-id="7fccc-109">弄已还原的 rejit 版本数。</span><span class="sxs-lookup"><span data-stu-id="7fccc-109">[out] The number of reverted rejit versions.</span></span>

`rgRevertedRejitData`\
<span data-ttu-id="7fccc-110">弄与从内部 Api 返回的已恢复 rejit 版本关联的数据。</span><span class="sxs-lookup"><span data-stu-id="7fccc-110">[out] The data associated with the reverted rejit versions as returned from the internal APIs.</span></span>

`pcNeededRevertedRejitData`\
<span data-ttu-id="7fccc-111">弄存储与还原的 ReJit 版本关联的数据所需的字节数。</span><span class="sxs-lookup"><span data-stu-id="7fccc-111">[out] The number of bytes required to store the data associated with the reverted ReJit versions.</span></span>

## <a name="remarks"></a><span data-ttu-id="7fccc-112">备注</span><span class="sxs-lookup"><span data-stu-id="7fccc-112">Remarks</span></span>

<span data-ttu-id="7fccc-113">提供的方法是接口的一部分 `ISOSDacInterface` ，并且对应于虚拟方法表的21槽。</span><span class="sxs-lookup"><span data-stu-id="7fccc-113">The provided method is part of the `ISOSDacInterface` interface and corresponds to the 21st slot of the virtual method table.</span></span> <span data-ttu-id="7fccc-114">若要使用它们， [`CLRDATA_ADDRESS`](../common-data-types-unmanaged-api-reference.md) 必须将定义为64位无符号整数。</span><span class="sxs-lookup"><span data-stu-id="7fccc-114">To be able to use them, [`CLRDATA_ADDRESS`](../common-data-types-unmanaged-api-reference.md) must be defined as a 64-bit unsigned integer.</span></span>

## <a name="requirements"></a><span data-ttu-id="7fccc-115">要求</span><span class="sxs-lookup"><span data-stu-id="7fccc-115">Requirements</span></span>

<span data-ttu-id="7fccc-116">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7fccc-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="7fccc-117">**标头：** 内容</span><span class="sxs-lookup"><span data-stu-id="7fccc-117">**Header:** None</span></span>  
<span data-ttu-id="7fccc-118">**库：** 内容</span><span class="sxs-lookup"><span data-stu-id="7fccc-118">**Library:** None</span></span>  
<span data-ttu-id="7fccc-119">**.NET Framework 版本：**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="7fccc-119">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="7fccc-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7fccc-120">See also</span></span>

- [<span data-ttu-id="7fccc-121">调试</span><span class="sxs-lookup"><span data-stu-id="7fccc-121">Debugging</span></span>](index.md)
- [<span data-ttu-id="7fccc-122">ISOSDacInterface 接口</span><span class="sxs-lookup"><span data-stu-id="7fccc-122">ISOSDacInterface Interface</span></span>](isosdacinterface-interface.md)
