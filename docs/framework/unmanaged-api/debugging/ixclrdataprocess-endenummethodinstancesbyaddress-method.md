---
title: IXCLRDataProcess::EndEnumMethodInstancesByAddress 方法
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::EndEnumMethodInstancesByAddress Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::EndEnumMethodInstancesByAddress Method
helpviewer.keywords:
- IXCLRDataProcess::EndEnumMethodInstancesByAddress Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 67978e49a8c23c4b25234ecbb3639c696c7232f4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54655642"
---
# <a name="ixclrdataprocessendenummethodinstancesbyaddress-method"></a><span data-ttu-id="5051d-102">IXCLRDataProcess::EndEnumMethodInstancesByAddress 方法</span><span class="sxs-lookup"><span data-stu-id="5051d-102">IXCLRDataProcess::EndEnumMethodInstancesByAddress Method</span></span>

<span data-ttu-id="5051d-103">释放使用的内部实例枚举过程中使用的迭代器的资源。</span><span class="sxs-lookup"><span data-stu-id="5051d-103">Releases the resources used by internal iterators used during instance enumeration.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="5051d-104">语法</span><span class="sxs-lookup"><span data-stu-id="5051d-104">Syntax</span></span>

```
HRESULT EndEnumMethodInstancesByAddress(
    [in] CLRDATA_ENUM handle
);
```

### <a name="parameters"></a><span data-ttu-id="5051d-105">参数</span><span class="sxs-lookup"><span data-stu-id="5051d-105">Parameters</span></span>

<span data-ttu-id="5051d-106">`handle` [out]枚举的方法实例句柄。</span><span class="sxs-lookup"><span data-stu-id="5051d-106">`handle` [out] A handle for enumerating the method instances.</span></span>

## <a name="remarks"></a><span data-ttu-id="5051d-107">备注</span><span class="sxs-lookup"><span data-stu-id="5051d-107">Remarks</span></span>

<span data-ttu-id="5051d-108">提供的方法属于`IXCLRDataProcess`接口，并对应于虚拟方法表 29 槽。</span><span class="sxs-lookup"><span data-stu-id="5051d-108">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 29th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="5051d-109">要求</span><span class="sxs-lookup"><span data-stu-id="5051d-109">Requirements</span></span>

<span data-ttu-id="5051d-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5051d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="5051d-111">**标头：** 无</span><span class="sxs-lookup"><span data-stu-id="5051d-111">**Header:** None</span></span>  
<span data-ttu-id="5051d-112">**库：** 无</span><span class="sxs-lookup"><span data-stu-id="5051d-112">**Library:** None</span></span>  
<span data-ttu-id="5051d-113">**.NET Framework 版本：**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="5051d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="5051d-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="5051d-114">See also</span></span>

- [<span data-ttu-id="5051d-115">CLRDataSourceType 枚举</span><span class="sxs-lookup"><span data-stu-id="5051d-115">CLRDataSourceType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="5051d-116">调试</span><span class="sxs-lookup"><span data-stu-id="5051d-116">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="5051d-117">IXCLRDataProcess 接口</span><span class="sxs-lookup"><span data-stu-id="5051d-117">IXCLRDataProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdataprocess-interface.md)
