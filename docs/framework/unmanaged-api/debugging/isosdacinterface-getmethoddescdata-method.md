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
ms.openlocfilehash: 3f22752446413c622a20340541b0ac328f63c77b
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2019
ms.locfileid: "54416376"
---
# <a name="isosdacinterfacegetmethoddescdata-method"></a><span data-ttu-id="529e4-102">ISOSDacInterface::GetMethodDescData 方法</span><span class="sxs-lookup"><span data-stu-id="529e4-102">ISOSDacInterface::GetMethodDescData Method</span></span>

<span data-ttu-id="529e4-103">获取有关数据给定[MethodDesc](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md)。</span><span class="sxs-lookup"><span data-stu-id="529e4-103">Gets the data for the given [MethodDesc](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md).</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="529e4-104">语法</span><span class="sxs-lookup"><span data-stu-id="529e4-104">Syntax</span></span>

```
HRESULT GetMethodDescData(
    CLRDATA_ADDRESS            methodDesc,
    CLRDATA_ADDRESS            ip,
    void                       *data,
    ULONG                      cRevertedRejitVersions,
    void                      *rgRevertedRejitData,
    void                      *pcNeededRevertedRejitData
);
```

### <a name="parameters"></a><span data-ttu-id="529e4-105">参数</span><span class="sxs-lookup"><span data-stu-id="529e4-105">Parameters</span></span>

<span data-ttu-id="529e4-106">`methodDesc` [in]MethodDesc 的地址。</span><span class="sxs-lookup"><span data-stu-id="529e4-106">`methodDesc` [in] The address of the MethodDesc.</span></span>

<span data-ttu-id="529e4-107">`ip` [in]该方法的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="529e4-107">`ip` [in] The IP address of the method.</span></span>

<span data-ttu-id="529e4-108">`data` [out]返回从内部 Api 与 MethodDesc 关联的数据。</span><span class="sxs-lookup"><span data-stu-id="529e4-108">`data` [out] The data associated with the MethodDesc as returned from the internal APIs.</span></span> <span data-ttu-id="529e4-109">结构需要至少 168 个字节。</span><span class="sxs-lookup"><span data-stu-id="529e4-109">The structure needs at least 168 bytes.</span></span>

<span data-ttu-id="529e4-110">`cRevertedRejitVersions` [out]已还原的 rejit 版本数。</span><span class="sxs-lookup"><span data-stu-id="529e4-110">`cRevertedRejitVersions` [out] The number of reverted rejit versions.</span></span>

<span data-ttu-id="529e4-111">`rgRevertedRejitData` [out]返回从内部 Api 与已还原的 rejit 版本关联的数据。</span><span class="sxs-lookup"><span data-stu-id="529e4-111">`rgRevertedRejitData` [out] The data associated with the reverted rejit versions as returned from the internal APIs.</span></span> <span data-ttu-id="529e4-112">结构需要至少 24 个字节。</span><span class="sxs-lookup"><span data-stu-id="529e4-112">The structure needs at least 24 bytes.</span></span>

<span data-ttu-id="529e4-113">`pcNeededRevertedRejitData` [out]存储与已还原的 ReJit 版本关联的数据所需的字节数。</span><span class="sxs-lookup"><span data-stu-id="529e4-113">`pcNeededRevertedRejitData` [out] The number of bytes required to store the data associated with the reverted ReJit versions.</span></span>

## <a name="remarks"></a><span data-ttu-id="529e4-114">备注</span><span class="sxs-lookup"><span data-stu-id="529e4-114">Remarks</span></span>

<span data-ttu-id="529e4-115">提供的方法属于`ISOSDacInterface`接口，并对应于虚拟方法表的 20 槽。</span><span class="sxs-lookup"><span data-stu-id="529e4-115">The provided method is part of the `ISOSDacInterface` interface and corresponds to the 20th slot of the virtual method table.</span></span> <span data-ttu-id="529e4-116">此外`CLRDATA_ADDRESS`是 64 位无符号的整数。</span><span class="sxs-lookup"><span data-stu-id="529e4-116">Also the `CLRDATA_ADDRESS` are 64-bit unsigned integer.</span></span>

## <a name="requirements"></a><span data-ttu-id="529e4-117">要求</span><span class="sxs-lookup"><span data-stu-id="529e4-117">Requirements</span></span>

<span data-ttu-id="529e4-118">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="529e4-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="529e4-119">**标头：** 无</span><span class="sxs-lookup"><span data-stu-id="529e4-119">**Header:** None</span></span>  
<span data-ttu-id="529e4-120">**库：** 无</span><span class="sxs-lookup"><span data-stu-id="529e4-120">**Library:** None</span></span>  
<span data-ttu-id="529e4-121">**.NET Framework 版本：**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="529e4-121">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="529e4-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="529e4-122">See Also</span></span>

- [<span data-ttu-id="529e4-123">调试</span><span class="sxs-lookup"><span data-stu-id="529e4-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="529e4-124">ISOSDacInterface 接口</span><span class="sxs-lookup"><span data-stu-id="529e4-124">ISOSDacInterface Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/isosdacinterface-interface.md)
