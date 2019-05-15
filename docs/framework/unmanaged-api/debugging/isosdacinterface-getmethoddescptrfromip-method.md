---
title: ISOSDacInterface::GetMethodDescPtrFromIP 方法
ms.date: 02/01/2019
api.name:
- ISOSDacInterface::GetMethodDescPtrFromIP Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- ISOSDacInterface::GetMethodDescPtrFromIP Method
helpviewer.keywords:
- ISOSDacInterface::GetMethodDescPtrFromIP Method [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: c92b112262aa2bede03bddc1396947b5fdfd6286
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "65629994"
---
# <a name="isosdacinterfacegetmethoddescptrfromip-method"></a><span data-ttu-id="ec59b-102">ISOSDacInterface::GetMethodDescPtrFromIP 方法</span><span class="sxs-lookup"><span data-stu-id="ec59b-102">ISOSDacInterface::GetMethodDescPtrFromIP Method</span></span>

<span data-ttu-id="ec59b-103">检索对应的方法，其中包含给定的本机指令地址 MethodDesc 的指针。</span><span class="sxs-lookup"><span data-stu-id="ec59b-103">Retrieves the pointer of the MethodDesc corresponding the method containing the given native instruction address.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="ec59b-104">语法</span><span class="sxs-lookup"><span data-stu-id="ec59b-104">Syntax</span></span>

```
HRESULT GetMethodDescPtrFromIP(
    CLRDATA_ADDRESS ip,
    CLRDATA_ADDRESS * ppMD
);
```

## <a name="parameters"></a><span data-ttu-id="ec59b-105">参数</span><span class="sxs-lookup"><span data-stu-id="ec59b-105">Parameters</span></span>

`ip`\
<span data-ttu-id="ec59b-106">[in]在运行时方法中的地址。</span><span class="sxs-lookup"><span data-stu-id="ec59b-106">[in] An address within the method at runtime.</span></span>

`ppMD`\
<span data-ttu-id="ec59b-107">[out]地址`MethodDesc`特定方法。</span><span class="sxs-lookup"><span data-stu-id="ec59b-107">[out] The address of the `MethodDesc` for the particular method.</span></span>

## <a name="remarks"></a><span data-ttu-id="ec59b-108">备注</span><span class="sxs-lookup"><span data-stu-id="ec59b-108">Remarks</span></span>

<span data-ttu-id="ec59b-109">提供的方法属于[`ISOSDacInterface`接口](isosdacinterface-interface.md)和对应于虚拟方法表 21 槽。</span><span class="sxs-lookup"><span data-stu-id="ec59b-109">The provided method is part of the [`ISOSDacInterface` interface](isosdacinterface-interface.md) and corresponds to the 21st slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="ec59b-110">要求</span><span class="sxs-lookup"><span data-stu-id="ec59b-110">Requirements</span></span>

<span data-ttu-id="ec59b-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ec59b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="ec59b-112">**标头：** None</span><span class="sxs-lookup"><span data-stu-id="ec59b-112">**Header:** None</span></span>  
<span data-ttu-id="ec59b-113">**库：** None</span><span class="sxs-lookup"><span data-stu-id="ec59b-113">**Library:** None</span></span>  
<span data-ttu-id="ec59b-114">**.NET Framework 版本：**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="ec59b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="ec59b-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="ec59b-115">See also</span></span>

- [<span data-ttu-id="ec59b-116">调试</span><span class="sxs-lookup"><span data-stu-id="ec59b-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="ec59b-117">ISOSDacInterface 接口</span><span class="sxs-lookup"><span data-stu-id="ec59b-117">ISOSDacInterface Interface</span></span>](isosdacinterface-interface.md)
