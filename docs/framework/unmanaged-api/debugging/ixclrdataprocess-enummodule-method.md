---
title: IXCLRDataProcess：： EnumModule 方法
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::EnumModule Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::EnumModule Method
helpviewer.keywords:
- IXCLRDataProcess::EnumModule Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 5caadcfe091393a8ff79106d57a50a532c349829
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420768"
---
# <a name="ixclrdataprocessenummodule-method"></a><span data-ttu-id="e436c-102">IXCLRDataProcess：： EnumModule 方法</span><span class="sxs-lookup"><span data-stu-id="e436c-102">IXCLRDataProcess::EnumModule Method</span></span>

<span data-ttu-id="e436c-103">枚举此进程的模块。</span><span class="sxs-lookup"><span data-stu-id="e436c-103">Enumerates the modules of this process.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="e436c-104">语法</span><span class="sxs-lookup"><span data-stu-id="e436c-104">Syntax</span></span>

```cpp
HRESULT EnumModule(
    [in, out] CLRDATA_ENUM  *handle,
    [out] IXCLRDataModule  **mod
);
```

## <a name="parameters"></a><span data-ttu-id="e436c-105">参数</span><span class="sxs-lookup"><span data-stu-id="e436c-105">Parameters</span></span>

`handle`\
<span data-ttu-id="e436c-106">[in，out]用于枚举模块的句柄。</span><span class="sxs-lookup"><span data-stu-id="e436c-106">[in, out] A handle for enumerating the modules.</span></span>

`mod`\
<span data-ttu-id="e436c-107">弄枚举的模块。</span><span class="sxs-lookup"><span data-stu-id="e436c-107">[out] The enumerated module.</span></span>

## <a name="remarks"></a><span data-ttu-id="e436c-108">备注</span><span class="sxs-lookup"><span data-stu-id="e436c-108">Remarks</span></span>

<span data-ttu-id="e436c-109">提供的方法是接口的一部分 `IXCLRDataProcess` ，并且对应于虚拟方法表的第25个槽。</span><span class="sxs-lookup"><span data-stu-id="e436c-109">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 25th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="e436c-110">要求</span><span class="sxs-lookup"><span data-stu-id="e436c-110">Requirements</span></span>

<span data-ttu-id="e436c-111">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e436c-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="e436c-112">**标头：** 内容</span><span class="sxs-lookup"><span data-stu-id="e436c-112">**Header:** None</span></span>  
<span data-ttu-id="e436c-113">**库：** 内容</span><span class="sxs-lookup"><span data-stu-id="e436c-113">**Library:** None</span></span>  
<span data-ttu-id="e436c-114">**.NET Framework 版本：**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="e436c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="e436c-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e436c-115">See also</span></span>

- [<span data-ttu-id="e436c-116">CLRDataSourceType 枚举</span><span class="sxs-lookup"><span data-stu-id="e436c-116">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="e436c-117">调试</span><span class="sxs-lookup"><span data-stu-id="e436c-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="e436c-118">IXCLRDataModule 接口</span><span class="sxs-lookup"><span data-stu-id="e436c-118">IXCLRDataModule Interface</span></span>](ixclrdatamodule-interface.md)
- [<span data-ttu-id="e436c-119">IXCLRDataProcess 接口</span><span class="sxs-lookup"><span data-stu-id="e436c-119">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
