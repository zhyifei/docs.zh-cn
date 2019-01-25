---
title: IXCLRDataMethodDefinition::EnumInstance 方法
ms.date: 01/16/2019
api.name:
- IXCLRDataMethodDefinition::EnumInstance Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodDefinition::EnumInstance Method
helpviewer.keywords:
- IXCLRDataMethodDefinition::EnumInstance Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 0fbb246f8c4bf791dd705aedf8eab6ef8bfeae56
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54680255"
---
# <a name="ixclrdatamethoddefinitionenuminstance-method"></a><span data-ttu-id="9a131-102">IXCLRDataMethodDefinition::EnumInstance 方法</span><span class="sxs-lookup"><span data-stu-id="9a131-102">IXCLRDataMethodDefinition::EnumInstance Method</span></span>

<span data-ttu-id="9a131-103">枚举该方法定义的实例。</span><span class="sxs-lookup"><span data-stu-id="9a131-103">Enumerates the instances of this method definition.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="9a131-104">语法</span><span class="sxs-lookup"><span data-stu-id="9a131-104">Syntax</span></span>

```
HRESULT EnumInstance(
    [in, out] CLRDATA_ENUM         *handle,
    [out] IXCLRDataMethodInstance **instance
);
```

### <a name="parameters"></a><span data-ttu-id="9a131-105">参数</span><span class="sxs-lookup"><span data-stu-id="9a131-105">Parameters</span></span>

<span data-ttu-id="9a131-106">`handle` [in、 out]枚举的实例句柄。</span><span class="sxs-lookup"><span data-stu-id="9a131-106">`handle` [in, out] A handle for enumerating the instances.</span></span>

<span data-ttu-id="9a131-107">`instance` [out]枚举的实例。</span><span class="sxs-lookup"><span data-stu-id="9a131-107">`instance` [out] The enumerated instance.</span></span>

## <a name="remarks"></a><span data-ttu-id="9a131-108">备注</span><span class="sxs-lookup"><span data-stu-id="9a131-108">Remarks</span></span>

<span data-ttu-id="9a131-109">提供的方法属于`IXCLRDataMethodDefinition`接口，并对应于虚拟方法表的第四个槽。</span><span class="sxs-lookup"><span data-stu-id="9a131-109">The provided method is part of the `IXCLRDataMethodDefinition` interface and corresponds to the fourth slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="9a131-110">要求</span><span class="sxs-lookup"><span data-stu-id="9a131-110">Requirements</span></span>

<span data-ttu-id="9a131-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9a131-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="9a131-112">**标头：** 无</span><span class="sxs-lookup"><span data-stu-id="9a131-112">**Header:** None</span></span>  
<span data-ttu-id="9a131-113">**库：** 无</span><span class="sxs-lookup"><span data-stu-id="9a131-113">**Library:** None</span></span>  
<span data-ttu-id="9a131-114">**.NET Framework 版本：**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="9a131-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="9a131-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="9a131-115">See also</span></span>

- [<span data-ttu-id="9a131-116">CLRDataSourceType 枚举</span><span class="sxs-lookup"><span data-stu-id="9a131-116">CLRDataSourceType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="9a131-117">调试</span><span class="sxs-lookup"><span data-stu-id="9a131-117">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="9a131-118">IXCLRDataMethodDefinition 接口</span><span class="sxs-lookup"><span data-stu-id="9a131-118">IXCLRDataMethodDefinition Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethoddefinition-interface.md)
- [<span data-ttu-id="9a131-119">IXCLRDataMethodInstance 接口</span><span class="sxs-lookup"><span data-stu-id="9a131-119">IXCLRDataMethodInstance Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethodinstance-interface.md)
