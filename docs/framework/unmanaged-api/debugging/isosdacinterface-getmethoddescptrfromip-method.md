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
ms.openlocfilehash: 0c8d91c11205e06857b4a6e7edfedcd087270d00
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396926"
---
# <a name="isosdacinterfacegetmethoddescptrfromip-method"></a><span data-ttu-id="30a61-102">ISOSDacInterface：： GetMethodDescPtrFromIP 方法</span><span class="sxs-lookup"><span data-stu-id="30a61-102">ISOSDacInterface::GetMethodDescPtrFromIP Method</span></span>

<span data-ttu-id="30a61-103">检索与包含给定本机指令地址的方法相对应的 MethodDesc 的指针。</span><span class="sxs-lookup"><span data-stu-id="30a61-103">Retrieves the pointer of the MethodDesc corresponding the method containing the given native instruction address.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="30a61-104">语法</span><span class="sxs-lookup"><span data-stu-id="30a61-104">Syntax</span></span>

```cpp
HRESULT GetMethodDescPtrFromIP(
    CLRDATA_ADDRESS ip,
    CLRDATA_ADDRESS * ppMD
);
```

## <a name="parameters"></a><span data-ttu-id="30a61-105">参数</span><span class="sxs-lookup"><span data-stu-id="30a61-105">Parameters</span></span>

`ip`\
<span data-ttu-id="30a61-106">中运行时方法中的地址。</span><span class="sxs-lookup"><span data-stu-id="30a61-106">[in] An address within the method at runtime.</span></span>

`ppMD`\
<span data-ttu-id="30a61-107">弄特定方法的地址 `MethodDesc` 。</span><span class="sxs-lookup"><span data-stu-id="30a61-107">[out] The address of the `MethodDesc` for the particular method.</span></span>

## <a name="remarks"></a><span data-ttu-id="30a61-108">备注</span><span class="sxs-lookup"><span data-stu-id="30a61-108">Remarks</span></span>

<span data-ttu-id="30a61-109">提供的方法是[ `ISOSDacInterface` 接口](isosdacinterface-interface.md)的一部分，并且对应于虚拟方法表的22日槽。</span><span class="sxs-lookup"><span data-stu-id="30a61-109">The provided method is part of the [`ISOSDacInterface` interface](isosdacinterface-interface.md) and corresponds to the 22nd slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="30a61-110">要求</span><span class="sxs-lookup"><span data-stu-id="30a61-110">Requirements</span></span>

<span data-ttu-id="30a61-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="30a61-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="30a61-112">**标头：** 内容</span><span class="sxs-lookup"><span data-stu-id="30a61-112">**Header:** None</span></span>  
<span data-ttu-id="30a61-113">**库：** 内容</span><span class="sxs-lookup"><span data-stu-id="30a61-113">**Library:** None</span></span>  
<span data-ttu-id="30a61-114">**.NET Framework 版本：**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="30a61-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="30a61-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="30a61-115">See also</span></span>

- [<span data-ttu-id="30a61-116">调试</span><span class="sxs-lookup"><span data-stu-id="30a61-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="30a61-117">ISOSDacInterface 接口</span><span class="sxs-lookup"><span data-stu-id="30a61-117">ISOSDacInterface Interface</span></span>](isosdacinterface-interface.md)
