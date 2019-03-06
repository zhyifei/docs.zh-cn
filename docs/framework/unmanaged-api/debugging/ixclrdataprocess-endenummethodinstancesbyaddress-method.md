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
ms.openlocfilehash: 072e775d11d44dfbca27f1616889e388ae61d467
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57365992"
---
# <a name="ixclrdataprocessendenummethodinstancesbyaddress-method"></a><span data-ttu-id="39d8d-102">IXCLRDataProcess::EndEnumMethodInstancesByAddress 方法</span><span class="sxs-lookup"><span data-stu-id="39d8d-102">IXCLRDataProcess::EndEnumMethodInstancesByAddress Method</span></span>

<span data-ttu-id="39d8d-103">释放使用的内部实例枚举过程中使用的迭代器的资源。</span><span class="sxs-lookup"><span data-stu-id="39d8d-103">Releases the resources used by internal iterators used during instance enumeration.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="39d8d-104">语法</span><span class="sxs-lookup"><span data-stu-id="39d8d-104">Syntax</span></span>

```
HRESULT EndEnumMethodInstancesByAddress(
    [in] CLRDATA_ENUM handle
);
```

## <a name="parameters"></a><span data-ttu-id="39d8d-105">参数</span><span class="sxs-lookup"><span data-stu-id="39d8d-105">Parameters</span></span>

`handle`\
<span data-ttu-id="39d8d-106">[out]枚举的方法实例句柄。</span><span class="sxs-lookup"><span data-stu-id="39d8d-106">[out] A handle for enumerating the method instances.</span></span>

## <a name="remarks"></a><span data-ttu-id="39d8d-107">备注</span><span class="sxs-lookup"><span data-stu-id="39d8d-107">Remarks</span></span>

<span data-ttu-id="39d8d-108">提供的方法属于`IXCLRDataProcess`接口，并对应于虚拟方法表 29 槽。</span><span class="sxs-lookup"><span data-stu-id="39d8d-108">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 29th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="39d8d-109">要求</span><span class="sxs-lookup"><span data-stu-id="39d8d-109">Requirements</span></span>

<span data-ttu-id="39d8d-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="39d8d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="39d8d-111">**标头：** 无</span><span class="sxs-lookup"><span data-stu-id="39d8d-111">**Header:** None</span></span>  
<span data-ttu-id="39d8d-112">**库：** 无</span><span class="sxs-lookup"><span data-stu-id="39d8d-112">**Library:** None</span></span>  
<span data-ttu-id="39d8d-113">**.NET Framework 版本：**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="39d8d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="39d8d-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="39d8d-114">See also</span></span>

- [<span data-ttu-id="39d8d-115">CLRDataSourceType 枚举</span><span class="sxs-lookup"><span data-stu-id="39d8d-115">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="39d8d-116">调试</span><span class="sxs-lookup"><span data-stu-id="39d8d-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="39d8d-117">IXCLRDataProcess 接口</span><span class="sxs-lookup"><span data-stu-id="39d8d-117">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
