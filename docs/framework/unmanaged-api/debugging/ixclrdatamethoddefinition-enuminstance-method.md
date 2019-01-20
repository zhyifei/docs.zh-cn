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
ms.openlocfilehash: 420acda89858713f12ea87a8c8d3909682a3f5e3
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2019
ms.locfileid: "54416375"
---
# <a name="ixclrdatamethoddefinitionenuminstance-method"></a><span data-ttu-id="1a178-102">IXCLRDataMethodDefinition::EnumInstance 方法</span><span class="sxs-lookup"><span data-stu-id="1a178-102">IXCLRDataMethodDefinition::EnumInstance Method</span></span>

<span data-ttu-id="1a178-103">枚举该方法定义的实例。</span><span class="sxs-lookup"><span data-stu-id="1a178-103">Enumerates the instances of this method definition.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="1a178-104">语法</span><span class="sxs-lookup"><span data-stu-id="1a178-104">Syntax</span></span>

```
HRESULT EnumInstance(
    [in, out] CLRDATA_ENUM         *handle,
    [out] IXCLRDataMethodInstance **instance
);
```

### <a name="parameters"></a><span data-ttu-id="1a178-105">参数</span><span class="sxs-lookup"><span data-stu-id="1a178-105">Parameters</span></span>

<span data-ttu-id="1a178-106">`handle` [in、 out]枚举的实例句柄。</span><span class="sxs-lookup"><span data-stu-id="1a178-106">`handle` [in, out] A handle for enumerating the instances.</span></span>

<span data-ttu-id="1a178-107">`instance` [out]枚举的实例。</span><span class="sxs-lookup"><span data-stu-id="1a178-107">`instance` [out] The enumerated instance.</span></span>

## <a name="remarks"></a><span data-ttu-id="1a178-108">备注</span><span class="sxs-lookup"><span data-stu-id="1a178-108">Remarks</span></span>

<span data-ttu-id="1a178-109">提供的方法属于`IXCLRDataMethodDefinition`接口，并对应于虚拟方法表的第四个槽。</span><span class="sxs-lookup"><span data-stu-id="1a178-109">The provided method is part of the `IXCLRDataMethodDefinition` interface and corresponds to the fourth slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="1a178-110">要求</span><span class="sxs-lookup"><span data-stu-id="1a178-110">Requirements</span></span>

<span data-ttu-id="1a178-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1a178-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="1a178-112">**标头：** 无</span><span class="sxs-lookup"><span data-stu-id="1a178-112">**Header:** None</span></span>  
<span data-ttu-id="1a178-113">**库：** 无</span><span class="sxs-lookup"><span data-stu-id="1a178-113">**Library:** None</span></span>  
<span data-ttu-id="1a178-114">**.NET Framework 版本：**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="1a178-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="1a178-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="1a178-115">See Also</span></span>

- [<span data-ttu-id="1a178-116">CLRDataSourceType 枚举</span><span class="sxs-lookup"><span data-stu-id="1a178-116">CLRDataSourceType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="1a178-117">调试</span><span class="sxs-lookup"><span data-stu-id="1a178-117">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="1a178-118">IXCLRDataMethodDefinition 接口</span><span class="sxs-lookup"><span data-stu-id="1a178-118">IXCLRDataMethodDefinition Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethoddefinition-interface.md)
- [<span data-ttu-id="1a178-119">IXCLRDataMethodInstance 接口</span><span class="sxs-lookup"><span data-stu-id="1a178-119">IXCLRDataMethodInstance Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethodinstance-interface.md)
