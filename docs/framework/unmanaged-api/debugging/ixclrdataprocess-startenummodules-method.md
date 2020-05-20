---
title: IXCLRDataProcess：： StartEnumModules 方法
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::StartEnumModules Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::StartEnumModules Method
helpviewer.keywords:
- IXCLRDataProcess::StartEnumModules Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: d55b07ea3fada73237919bf677163a9096d5ad04
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420716"
---
# <a name="ixclrdataprocessstartenummodules-method"></a><span data-ttu-id="73574-102">IXCLRDataProcess：： StartEnumModules 方法</span><span class="sxs-lookup"><span data-stu-id="73574-102">IXCLRDataProcess::StartEnumModules Method</span></span>

<span data-ttu-id="73574-103">提供枚举进程的模块的句柄。</span><span class="sxs-lookup"><span data-stu-id="73574-103">Provides a handle to enumerate the modules of a process.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="73574-104">语法</span><span class="sxs-lookup"><span data-stu-id="73574-104">Syntax</span></span>

```cpp
HRESULT StartEnumModules(
    [out] CLRDATA_ENUM *handle
);
```

## <a name="parameters"></a><span data-ttu-id="73574-105">参数</span><span class="sxs-lookup"><span data-stu-id="73574-105">Parameters</span></span>

`handle`\
<span data-ttu-id="73574-106">弄用于枚举模块的句柄。</span><span class="sxs-lookup"><span data-stu-id="73574-106">[out] A handle for enumerating the modules.</span></span>

## <a name="remarks"></a><span data-ttu-id="73574-107">备注</span><span class="sxs-lookup"><span data-stu-id="73574-107">Remarks</span></span>

<span data-ttu-id="73574-108">提供的方法是接口的一部分 `IXCLRDataProcess` ，并且对应于虚拟方法表的24日槽。</span><span class="sxs-lookup"><span data-stu-id="73574-108">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 24th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="73574-109">要求</span><span class="sxs-lookup"><span data-stu-id="73574-109">Requirements</span></span>

<span data-ttu-id="73574-110">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="73574-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="73574-111">**标头：** 内容</span><span class="sxs-lookup"><span data-stu-id="73574-111">**Header:** None</span></span>  
<span data-ttu-id="73574-112">**库：** 内容</span><span class="sxs-lookup"><span data-stu-id="73574-112">**Library:** None</span></span>  
<span data-ttu-id="73574-113">**.NET Framework 版本：**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="73574-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="73574-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="73574-114">See also</span></span>

- [<span data-ttu-id="73574-115">CLRDataSourceType 枚举</span><span class="sxs-lookup"><span data-stu-id="73574-115">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="73574-116">调试</span><span class="sxs-lookup"><span data-stu-id="73574-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="73574-117">IXCLRDataProcess 接口</span><span class="sxs-lookup"><span data-stu-id="73574-117">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
