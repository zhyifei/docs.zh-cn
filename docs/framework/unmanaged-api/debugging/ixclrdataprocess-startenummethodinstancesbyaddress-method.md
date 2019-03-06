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
ms.openlocfilehash: 8d0494e53705493de814ed4d4caa869e1e8a700f
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57374565"
---
# <a name="ixclrdataprocessstartenummethodinstancesbyaddress-method"></a><span data-ttu-id="fc939-102">IXCLRDataProcess::StartEnumMethodInstancesByAddress 方法</span><span class="sxs-lookup"><span data-stu-id="fc939-102">IXCLRDataProcess::StartEnumMethodInstancesByAddress Method</span></span>

<span data-ttu-id="fc939-103">提供要枚举的方法实例的句柄`AppDomain`给定地址开始。</span><span class="sxs-lookup"><span data-stu-id="fc939-103">Provides a handle to enumerate the method instances of `AppDomain` starting at a given address.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="fc939-104">语法</span><span class="sxs-lookup"><span data-stu-id="fc939-104">Syntax</span></span>

```
HRESULT StartEnumMethodInstancesByAddress(
    [in] CLRDATA_ADDRESS     address,
    [in] IXCLRDataAppDomain *appDomain,
    [out] CLRDATA_ENUM      *handle
);
```

### <a name="parameters"></a><span data-ttu-id="fc939-105">参数</span><span class="sxs-lookup"><span data-stu-id="fc939-105">Parameters</span></span>

`address`\
<span data-ttu-id="fc939-106">[in]第一个方法实例的地址。</span><span class="sxs-lookup"><span data-stu-id="fc939-106">[in] The address of the first method instance.</span></span>

`appDomain`\
<span data-ttu-id="fc939-107">[in]方法实例的应用程序域。</span><span class="sxs-lookup"><span data-stu-id="fc939-107">[in] The AppDomain of the method instances.</span></span>

`handle`\
<span data-ttu-id="fc939-108">[out]枚举的方法实例句柄。</span><span class="sxs-lookup"><span data-stu-id="fc939-108">[out] A handle for enumerating the method instances.</span></span>

## <a name="remarks"></a><span data-ttu-id="fc939-109">备注</span><span class="sxs-lookup"><span data-stu-id="fc939-109">Remarks</span></span>

<span data-ttu-id="fc939-110">提供的方法属于`IXCLRDataProcess`接口，并对应于虚拟方法表 27 槽。</span><span class="sxs-lookup"><span data-stu-id="fc939-110">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 27th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="fc939-111">要求</span><span class="sxs-lookup"><span data-stu-id="fc939-111">Requirements</span></span>

<span data-ttu-id="fc939-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fc939-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="fc939-113">**标头：** 无</span><span class="sxs-lookup"><span data-stu-id="fc939-113">**Header:** None</span></span>  
<span data-ttu-id="fc939-114">**库：** 无</span><span class="sxs-lookup"><span data-stu-id="fc939-114">**Library:** None</span></span>  
<span data-ttu-id="fc939-115">**.NET Framework 版本：**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="fc939-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="fc939-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="fc939-116">See also</span></span>

- [<span data-ttu-id="fc939-117">CLRDataSourceType 枚举</span><span class="sxs-lookup"><span data-stu-id="fc939-117">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="fc939-118">调试</span><span class="sxs-lookup"><span data-stu-id="fc939-118">Debugging</span></span>](index.md)
- [<span data-ttu-id="fc939-119">IXCLRDataProcess 接口</span><span class="sxs-lookup"><span data-stu-id="fc939-119">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
