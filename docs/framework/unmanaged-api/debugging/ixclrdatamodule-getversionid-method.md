---
title: IXCLRDataModule：： GetVersionId 方法
ms.date: 01/16/2019
api.name:
- IXCLRDataModule::GetVersionId Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataModule::GetVersionId Method
helpviewer.keywords:
- IXCLRDataModule::GetVersionId Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 9d5ef137a5d76c3d7545ab16921352123e978fb1
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420859"
---
# <a name="ixclrdatamodulegetversionid-method"></a><span data-ttu-id="7056e-102">IXCLRDataModule：： GetVersionId 方法</span><span class="sxs-lookup"><span data-stu-id="7056e-102">IXCLRDataModule::GetVersionId Method</span></span>

<span data-ttu-id="7056e-103">获取模块的版本标识符。</span><span class="sxs-lookup"><span data-stu-id="7056e-103">Gets the module's version identifier.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="7056e-104">语法</span><span class="sxs-lookup"><span data-stu-id="7056e-104">Syntax</span></span>

```cpp
HRESULT GetVersionId(
    [out] GUID* vid
);
```

## <a name="parameters"></a><span data-ttu-id="7056e-105">参数</span><span class="sxs-lookup"><span data-stu-id="7056e-105">Parameters</span></span>

`vid`\
<span data-ttu-id="7056e-106">弄模块的版本标识符。</span><span class="sxs-lookup"><span data-stu-id="7056e-106">[out] The module's version identifier.</span></span>

## <a name="remarks"></a><span data-ttu-id="7056e-107">备注</span><span class="sxs-lookup"><span data-stu-id="7056e-107">Remarks</span></span>

<span data-ttu-id="7056e-108">提供的方法是接口的一部分 `IXCLRDataModule` ，并且对应于虚拟方法表的第41届槽。</span><span class="sxs-lookup"><span data-stu-id="7056e-108">The provided method is part of the `IXCLRDataModule` interface and corresponds to the 41st slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="7056e-109">要求</span><span class="sxs-lookup"><span data-stu-id="7056e-109">Requirements</span></span>

<span data-ttu-id="7056e-110">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7056e-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="7056e-111">**标头：** 内容</span><span class="sxs-lookup"><span data-stu-id="7056e-111">**Header:** None</span></span>  
<span data-ttu-id="7056e-112">**库：** 内容</span><span class="sxs-lookup"><span data-stu-id="7056e-112">**Library:** None</span></span>  
<span data-ttu-id="7056e-113">**.NET Framework 版本：**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="7056e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="7056e-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7056e-114">See also</span></span>

- [<span data-ttu-id="7056e-115">调试</span><span class="sxs-lookup"><span data-stu-id="7056e-115">Debugging</span></span>](index.md)
- [<span data-ttu-id="7056e-116">IXCLRDataModule 接口</span><span class="sxs-lookup"><span data-stu-id="7056e-116">IXCLRDataModule Interface</span></span>](ixclrdatamodule-interface.md)
