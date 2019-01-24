---
title: IXCLRDataProcess::StartEnumMethodInstancesByAddress 方法
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::StartEnumMethodInstancesByAddress Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::StartEnumMethodInstancesByAddress Method
helpviewer.keywords:
- IXCLRDataProcess::StartEnumMethodInstancesByAddress Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 9afbf0665b114169661a74b60c744203d160fed3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54662616"
---
# <a name="ixclrdataprocessstartenummethodinstancesbyaddress-method"></a><span data-ttu-id="9ae80-102">IXCLRDataProcess::StartEnumMethodInstancesByAddress 方法</span><span class="sxs-lookup"><span data-stu-id="9ae80-102">IXCLRDataProcess::StartEnumMethodInstancesByAddress Method</span></span>

<span data-ttu-id="9ae80-103">提供要枚举的方法实例的句柄`AppDomain`给定地址开始。</span><span class="sxs-lookup"><span data-stu-id="9ae80-103">Provides a handle to enumerate the method instances of `AppDomain` starting at a given address.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="9ae80-104">语法</span><span class="sxs-lookup"><span data-stu-id="9ae80-104">Syntax</span></span>

```
HRESULT StartEnumMethodInstancesByAddress(
    [in] CLRDATA_ADDRESS     address,
    [in] IXCLRDataAppDomain *appDomain,
    [out] CLRDATA_ENUM      *handle
);
```

### <a name="parameters"></a><span data-ttu-id="9ae80-105">参数</span><span class="sxs-lookup"><span data-stu-id="9ae80-105">Parameters</span></span>

<span data-ttu-id="9ae80-106">`address` [in]第一个方法实例的地址。</span><span class="sxs-lookup"><span data-stu-id="9ae80-106">`address` [in] The address of the first method instance.</span></span>

<span data-ttu-id="9ae80-107">`appDomain` [in]方法实例的应用程序域。</span><span class="sxs-lookup"><span data-stu-id="9ae80-107">`appDomain` [in] The AppDomain of the method instances.</span></span>

<span data-ttu-id="9ae80-108">`handle` [out]枚举的方法实例句柄。</span><span class="sxs-lookup"><span data-stu-id="9ae80-108">`handle` [out] A handle for enumerating the method instances.</span></span>

## <a name="remarks"></a><span data-ttu-id="9ae80-109">备注</span><span class="sxs-lookup"><span data-stu-id="9ae80-109">Remarks</span></span>

<span data-ttu-id="9ae80-110">提供的方法属于`IXCLRDataProcess`接口，并对应于虚拟方法表 27 槽。</span><span class="sxs-lookup"><span data-stu-id="9ae80-110">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 27th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="9ae80-111">要求</span><span class="sxs-lookup"><span data-stu-id="9ae80-111">Requirements</span></span>

<span data-ttu-id="9ae80-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9ae80-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="9ae80-113">**标头：** 无</span><span class="sxs-lookup"><span data-stu-id="9ae80-113">**Header:** None</span></span>  
<span data-ttu-id="9ae80-114">**库：** 无</span><span class="sxs-lookup"><span data-stu-id="9ae80-114">**Library:** None</span></span>  
<span data-ttu-id="9ae80-115">**.NET Framework 版本：**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="9ae80-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="9ae80-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="9ae80-116">See also</span></span>

- [<span data-ttu-id="9ae80-117">CLRDataSourceType 枚举</span><span class="sxs-lookup"><span data-stu-id="9ae80-117">CLRDataSourceType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="9ae80-118">调试</span><span class="sxs-lookup"><span data-stu-id="9ae80-118">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="9ae80-119">IXCLRDataProcess 接口</span><span class="sxs-lookup"><span data-stu-id="9ae80-119">IXCLRDataProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdataprocess-interface.md)
