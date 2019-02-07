---
title: IXCLRDataMethodInstance::GetRepresentativeEntryAddress 方法
ms.date: 02/01/2019
api.name:
- IXCLRDataMethodInstance::GetRepresentativeEntryAddress
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodInstance::GetRepresentativeEntryAddress
helpviewer.keywords:
- IXCLRDataMethodInstance::GetRepresentativeEntryAddress Method [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: 52b2fdaaefd16a49300641f44041b8352141385b
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/07/2019
ms.locfileid: "55828602"
---
# <a name="ixclrdatamethodinstancegetrepresentativeentryaddress-method"></a><span data-ttu-id="32f85-102">IXCLRDataMethodInstance::GetRepresentativeEntryAddress 方法</span><span class="sxs-lookup"><span data-stu-id="32f85-102">IXCLRDataMethodInstance::GetRepresentativeEntryAddress Method</span></span>

<span data-ttu-id="32f85-103">获取方法的所有可能的入口点在本机编译的最具代表性的入口点地址。</span><span class="sxs-lookup"><span data-stu-id="32f85-103">Gets the most representative entry point address for the native compilation of all the possible entry points for a method.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="32f85-104">语法</span><span class="sxs-lookup"><span data-stu-id="32f85-104">Syntax</span></span>

```
HRESULT GetRepresentativeEntryAddress(
    [out] CLRDATA_ADDRESS* addr
);
```

### <a name="parameters"></a><span data-ttu-id="32f85-105">参数</span><span class="sxs-lookup"><span data-stu-id="32f85-105">Parameters</span></span>

<span data-ttu-id="32f85-106">`addr` [out]该方法的最具代表性本机入口点的地址。</span><span class="sxs-lookup"><span data-stu-id="32f85-106">`addr` [out] The address of the most representative native entry point for the method.</span></span>

## <a name="remarks"></a><span data-ttu-id="32f85-107">备注</span><span class="sxs-lookup"><span data-stu-id="32f85-107">Remarks</span></span>

<span data-ttu-id="32f85-108">提供的方法属于[`IXCLRDataMethodInstance`接口](ixclrdatamethodinstance-interface.md)和对应于虚拟方法表 19 槽。</span><span class="sxs-lookup"><span data-stu-id="32f85-108">The provided method is part of the [`IXCLRDataMethodInstance` interface](ixclrdatamethodinstance-interface.md) and corresponds to the 19th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="32f85-109">要求</span><span class="sxs-lookup"><span data-stu-id="32f85-109">Requirements</span></span>

<span data-ttu-id="32f85-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="32f85-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="32f85-111">**标头：** 无</span><span class="sxs-lookup"><span data-stu-id="32f85-111">**Header:** None</span></span>  
<span data-ttu-id="32f85-112">**库：** 无</span><span class="sxs-lookup"><span data-stu-id="32f85-112">**Library:** None</span></span>  
<span data-ttu-id="32f85-113">**.NET Framework 版本：**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="32f85-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="32f85-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="32f85-114">See also</span></span>

- [<span data-ttu-id="32f85-115">调试</span><span class="sxs-lookup"><span data-stu-id="32f85-115">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="32f85-116">IXCLRDataMethodInstance 接口</span><span class="sxs-lookup"><span data-stu-id="32f85-116">IXCLRDataMethodInstance Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethodinstance-interface.md)
