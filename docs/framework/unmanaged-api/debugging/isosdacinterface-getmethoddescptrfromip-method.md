---
title: ISOSDacInterface：： GetMethodDescPtrFromIP 方法
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
ms.openlocfilehash: c3de9e5ffe23a13c126343c6f74f042bf1239609
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421002"
---
# <a name="isosdacinterfacegetmethoddescptrfromip-method"></a><span data-ttu-id="6acb4-102">ISOSDacInterface：： GetMethodDescPtrFromIP 方法</span><span class="sxs-lookup"><span data-stu-id="6acb4-102">ISOSDacInterface::GetMethodDescPtrFromIP Method</span></span>

<span data-ttu-id="6acb4-103">检索与包含给定本机指令地址的方法相对应的 MethodDesc 的指针。</span><span class="sxs-lookup"><span data-stu-id="6acb4-103">Retrieves the pointer of the MethodDesc corresponding the method containing the given native instruction address.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="6acb4-104">语法</span><span class="sxs-lookup"><span data-stu-id="6acb4-104">Syntax</span></span>

```cpp
HRESULT GetMethodDescPtrFromIP(
    CLRDATA_ADDRESS ip,
    CLRDATA_ADDRESS * ppMD
);
```

## <a name="parameters"></a><span data-ttu-id="6acb4-105">参数</span><span class="sxs-lookup"><span data-stu-id="6acb4-105">Parameters</span></span>

`ip`\
<span data-ttu-id="6acb4-106">中运行时方法中的地址。</span><span class="sxs-lookup"><span data-stu-id="6acb4-106">[in] An address within the method at runtime.</span></span>

`ppMD`\
<span data-ttu-id="6acb4-107">弄特定方法的地址 `MethodDesc` 。</span><span class="sxs-lookup"><span data-stu-id="6acb4-107">[out] The address of the `MethodDesc` for the particular method.</span></span>

## <a name="remarks"></a><span data-ttu-id="6acb4-108">备注</span><span class="sxs-lookup"><span data-stu-id="6acb4-108">Remarks</span></span>

<span data-ttu-id="6acb4-109">提供的方法是[ `ISOSDacInterface` 接口](isosdacinterface-interface.md)的一部分，并且对应于虚拟方法表的22日槽。</span><span class="sxs-lookup"><span data-stu-id="6acb4-109">The provided method is part of the [`ISOSDacInterface` interface](isosdacinterface-interface.md) and corresponds to the 22nd slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="6acb4-110">要求</span><span class="sxs-lookup"><span data-stu-id="6acb4-110">Requirements</span></span>

<span data-ttu-id="6acb4-111">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6acb4-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="6acb4-112">**标头：** 内容</span><span class="sxs-lookup"><span data-stu-id="6acb4-112">**Header:** None</span></span>  
<span data-ttu-id="6acb4-113">**库：** 内容</span><span class="sxs-lookup"><span data-stu-id="6acb4-113">**Library:** None</span></span>  
<span data-ttu-id="6acb4-114">**.NET Framework 版本：**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="6acb4-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="6acb4-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6acb4-115">See also</span></span>

- [<span data-ttu-id="6acb4-116">调试</span><span class="sxs-lookup"><span data-stu-id="6acb4-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="6acb4-117">ISOSDacInterface 接口</span><span class="sxs-lookup"><span data-stu-id="6acb4-117">ISOSDacInterface Interface</span></span>](isosdacinterface-interface.md)
