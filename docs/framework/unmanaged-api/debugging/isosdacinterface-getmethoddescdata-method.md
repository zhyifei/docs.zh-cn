---
title: ISOSDacInterface::GetMethodDescData 方法
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
ms.openlocfilehash: cdbf662c664d6c87b2fa17bcb10d735b0f573dd2
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "65632319"
---
# <a name="isosdacinterfacegetmethoddescdata-method"></a><span data-ttu-id="9bba4-102">ISOSDacInterface::GetMethodDescData 方法</span><span class="sxs-lookup"><span data-stu-id="9bba4-102">ISOSDacInterface::GetMethodDescData Method</span></span>

<span data-ttu-id="9bba4-103">获取给定 MethodDesc 指针的数据。</span><span class="sxs-lookup"><span data-stu-id="9bba4-103">Gets the data for the given MethodDesc pointer.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="9bba4-104">语法</span><span class="sxs-lookup"><span data-stu-id="9bba4-104">Syntax</span></span>

```
HRESULT GetMethodDescData(
    CLRDATA_ADDRESS            methodDesc,
    CLRDATA_ADDRESS            ip,
    DacpMethodDescData *data,
    ULONG                      cRevertedRejitVersions,
    DacpReJitData      *rgRevertedRejitData,
    void                      *pcNeededRevertedRejitData
);
```

## <a name="parameters"></a><span data-ttu-id="9bba4-105">参数</span><span class="sxs-lookup"><span data-stu-id="9bba4-105">Parameters</span></span>

`methodDesc`\
<span data-ttu-id="9bba4-106">[in]MethodDesc 的地址。</span><span class="sxs-lookup"><span data-stu-id="9bba4-106">[in] The address of the MethodDesc.</span></span>

`ip`\
<span data-ttu-id="9bba4-107">[in]该方法的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="9bba4-107">[in] The IP address of the method.</span></span>

`data`\
<span data-ttu-id="9bba4-108">[out]返回从内部 Api 与 MethodDesc 关联的数据。</span><span class="sxs-lookup"><span data-stu-id="9bba4-108">[out] The data associated with the MethodDesc as returned from the internal APIs.</span></span>

`cRevertedRejitVersions`\
<span data-ttu-id="9bba4-109">[out]已还原的 rejit 版本数。</span><span class="sxs-lookup"><span data-stu-id="9bba4-109">[out] The number of reverted rejit versions.</span></span>

`rgRevertedRejitData`\
<span data-ttu-id="9bba4-110">[out]返回从内部 Api 与已还原的 rejit 版本关联的数据。</span><span class="sxs-lookup"><span data-stu-id="9bba4-110">[out] The data associated with the reverted rejit versions as returned from the internal APIs.</span></span>

`pcNeededRevertedRejitData`\
<span data-ttu-id="9bba4-111">[out]存储与已还原的 ReJit 版本关联的数据所需的字节数。</span><span class="sxs-lookup"><span data-stu-id="9bba4-111">[out] The number of bytes required to store the data associated with the reverted ReJit versions.</span></span>

## <a name="remarks"></a><span data-ttu-id="9bba4-112">备注</span><span class="sxs-lookup"><span data-stu-id="9bba4-112">Remarks</span></span>

<span data-ttu-id="9bba4-113">提供的方法属于`ISOSDacInterface`接口，并对应于虚拟方法表的 20 槽。</span><span class="sxs-lookup"><span data-stu-id="9bba4-113">The provided method is part of the `ISOSDacInterface` interface and corresponds to the 20th slot of the virtual method table.</span></span> <span data-ttu-id="9bba4-114">若要能够使用它们[ `CLRDATA_ADDRESS` ](../common-data-types-unmanaged-api-reference.md)必须定义为 64 位无符号整数。</span><span class="sxs-lookup"><span data-stu-id="9bba4-114">To be able to use them, [`CLRDATA_ADDRESS`](../common-data-types-unmanaged-api-reference.md) must be defined as a 64-bit unsigned integer.</span></span>

## <a name="requirements"></a><span data-ttu-id="9bba4-115">要求</span><span class="sxs-lookup"><span data-stu-id="9bba4-115">Requirements</span></span>

<span data-ttu-id="9bba4-116">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9bba4-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="9bba4-117">**标头：** None</span><span class="sxs-lookup"><span data-stu-id="9bba4-117">**Header:** None</span></span>  
<span data-ttu-id="9bba4-118">**库：** None</span><span class="sxs-lookup"><span data-stu-id="9bba4-118">**Library:** None</span></span>  
<span data-ttu-id="9bba4-119">**.NET Framework 版本：**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="9bba4-119">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="9bba4-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="9bba4-120">See also</span></span>

- [<span data-ttu-id="9bba4-121">调试</span><span class="sxs-lookup"><span data-stu-id="9bba4-121">Debugging</span></span>](index.md)
- [<span data-ttu-id="9bba4-122">ISOSDacInterface 接口</span><span class="sxs-lookup"><span data-stu-id="9bba4-122">ISOSDacInterface Interface</span></span>](isosdacinterface-interface.md)
