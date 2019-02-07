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
ms.openlocfilehash: 74853733b1fb7f023d9f192d3e862dbf6875ecda
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/07/2019
ms.locfileid: "55828597"
---
# <a name="isosdacinterfacegetmethoddescptrfromip-method"></a><span data-ttu-id="34b4e-102">ISOSDacInterface::GetMethodDescPtrFromIP 方法</span><span class="sxs-lookup"><span data-stu-id="34b4e-102">ISOSDacInterface::GetMethodDescPtrFromIP Method</span></span>

<span data-ttu-id="34b4e-103">检索对应的方法，其中包含给定的本机指令地址 MethodDesc 的指针。</span><span class="sxs-lookup"><span data-stu-id="34b4e-103">Retrieves the pointer of the MethodDesc corresponding the method containing the given native instruction address.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="34b4e-104">语法</span><span class="sxs-lookup"><span data-stu-id="34b4e-104">Syntax</span></span>

```
HRESULT GetMethodDescPtrFromIP(
    CLRDATA_ADDRESS ip,
    CLRDATA_ADDRESS * ppMD
);
```

### <a name="parameters"></a><span data-ttu-id="34b4e-105">参数</span><span class="sxs-lookup"><span data-stu-id="34b4e-105">Parameters</span></span>

<span data-ttu-id="34b4e-106">`ip` [in]在运行时方法中的地址。</span><span class="sxs-lookup"><span data-stu-id="34b4e-106">`ip` [in] An address within the method at runtime.</span></span>

<span data-ttu-id="34b4e-107">`ppMD` [out]地址`MethodDesc`特定方法。</span><span class="sxs-lookup"><span data-stu-id="34b4e-107">`ppMD` [out] The address of the `MethodDesc` for the particular method.</span></span>

## <a name="remarks"></a><span data-ttu-id="34b4e-108">备注</span><span class="sxs-lookup"><span data-stu-id="34b4e-108">Remarks</span></span>

<span data-ttu-id="34b4e-109">提供的方法属于[`ISOSDacInterface`接口](isosdacinterface-interface.md)和对应于虚拟方法表 21 槽。</span><span class="sxs-lookup"><span data-stu-id="34b4e-109">The provided method is part of the [`ISOSDacInterface` interface](isosdacinterface-interface.md) and corresponds to the 21st slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="34b4e-110">要求</span><span class="sxs-lookup"><span data-stu-id="34b4e-110">Requirements</span></span>

<span data-ttu-id="34b4e-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="34b4e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="34b4e-112">**标头：** 无</span><span class="sxs-lookup"><span data-stu-id="34b4e-112">**Header:** None</span></span>  
<span data-ttu-id="34b4e-113">**库：** 无</span><span class="sxs-lookup"><span data-stu-id="34b4e-113">**Library:** None</span></span>  
<span data-ttu-id="34b4e-114">**.NET Framework 版本：**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="34b4e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="34b4e-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="34b4e-115">See also</span></span>

- [<span data-ttu-id="34b4e-116">调试</span><span class="sxs-lookup"><span data-stu-id="34b4e-116">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="34b4e-117">ISOSDacInterface 接口</span><span class="sxs-lookup"><span data-stu-id="34b4e-117">ISOSDacInterface Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/isosdacinterface-interface.md)
