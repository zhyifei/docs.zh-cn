---
title: IXCLRDataMethodInstance：： GetRepresentativeEntryAddress 方法
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
ms.openlocfilehash: d9f9e16d243c0f3b45ac24776caea5bb9c32dcc1
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "83395753"
---
# <a name="ixclrdatamethodinstancegetrepresentativeentryaddress-method"></a><span data-ttu-id="ce5da-102">IXCLRDataMethodInstance：： GetRepresentativeEntryAddress 方法</span><span class="sxs-lookup"><span data-stu-id="ce5da-102">IXCLRDataMethodInstance::GetRepresentativeEntryAddress Method</span></span>

<span data-ttu-id="ce5da-103">获取方法的所有可能入口点的本机编译的最具代表性的入口点地址。</span><span class="sxs-lookup"><span data-stu-id="ce5da-103">Gets the most representative entry point address for the native compilation of all the possible entry points for a method.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="ce5da-104">语法</span><span class="sxs-lookup"><span data-stu-id="ce5da-104">Syntax</span></span>

```cpp
HRESULT GetRepresentativeEntryAddress(
    [out] CLRDATA_ADDRESS* addr
);
```

## <a name="parameters"></a><span data-ttu-id="ce5da-105">参数</span><span class="sxs-lookup"><span data-stu-id="ce5da-105">Parameters</span></span>

`addr`\
<span data-ttu-id="ce5da-106">弄方法的最具代表性的本机入口点的地址。</span><span class="sxs-lookup"><span data-stu-id="ce5da-106">[out] The address of the most representative native entry point for the method.</span></span>

## <a name="remarks"></a><span data-ttu-id="ce5da-107">备注</span><span class="sxs-lookup"><span data-stu-id="ce5da-107">Remarks</span></span>

<span data-ttu-id="ce5da-108">提供的方法是[ `IXCLRDataMethodInstance` 接口](ixclrdatamethodinstance-interface.md)的一部分，并且对应于虚拟方法表的第20个槽。</span><span class="sxs-lookup"><span data-stu-id="ce5da-108">The provided method is part of the [`IXCLRDataMethodInstance` interface](ixclrdatamethodinstance-interface.md) and corresponds to the 20th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="ce5da-109">要求</span><span class="sxs-lookup"><span data-stu-id="ce5da-109">Requirements</span></span>

<span data-ttu-id="ce5da-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ce5da-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="ce5da-111">**标头：** 内容</span><span class="sxs-lookup"><span data-stu-id="ce5da-111">**Header:** None</span></span>  
<span data-ttu-id="ce5da-112">**库：** 内容</span><span class="sxs-lookup"><span data-stu-id="ce5da-112">**Library:** None</span></span>  
<span data-ttu-id="ce5da-113">**.NET Framework 版本：**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="ce5da-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="ce5da-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="ce5da-114">See also</span></span>

- [<span data-ttu-id="ce5da-115">调试</span><span class="sxs-lookup"><span data-stu-id="ce5da-115">Debugging</span></span>](index.md)
- [<span data-ttu-id="ce5da-116">IXCLRDataMethodInstance 接口</span><span class="sxs-lookup"><span data-stu-id="ce5da-116">IXCLRDataMethodInstance Interface</span></span>](ixclrdatamethodinstance-interface.md)
