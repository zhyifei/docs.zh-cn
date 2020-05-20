---
title: IXCLRDataProcess：： EndEnumModules 方法
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::EndEnumModules Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::EndEnumModules Method
helpviewer.keywords:
- IXCLRDataProcess::EndEnumModules Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 9a7a23e53f5c2bc7d643046830cf335fec780f11
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420830"
---
# <a name="ixclrdataprocessendenummodules-method"></a><span data-ttu-id="d6ffa-102">IXCLRDataProcess：： EndEnumModules 方法</span><span class="sxs-lookup"><span data-stu-id="d6ffa-102">IXCLRDataProcess::EndEnumModules Method</span></span>

<span data-ttu-id="d6ffa-103">释放模块枚举期间使用的内部迭代器所使用的资源。</span><span class="sxs-lookup"><span data-stu-id="d6ffa-103">Releases the resources used by internal iterators used during module enumeration.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="d6ffa-104">语法</span><span class="sxs-lookup"><span data-stu-id="d6ffa-104">Syntax</span></span>

```cpp
HRESULT EndEnumModules(
    [in] CLRDATA_ENUM handle
);
```

## <a name="parameters"></a><span data-ttu-id="d6ffa-105">参数</span><span class="sxs-lookup"><span data-stu-id="d6ffa-105">Parameters</span></span>

`handle`\
<span data-ttu-id="d6ffa-106">弄用于枚举模块的句柄。</span><span class="sxs-lookup"><span data-stu-id="d6ffa-106">[out] A handle for enumerating the modules.</span></span>

## <a name="remarks"></a><span data-ttu-id="d6ffa-107">备注</span><span class="sxs-lookup"><span data-stu-id="d6ffa-107">Remarks</span></span>

<span data-ttu-id="d6ffa-108">提供的方法是接口的一部分 `IXCLRDataProcess` ，并且对应于虚拟方法表的26个槽。</span><span class="sxs-lookup"><span data-stu-id="d6ffa-108">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 26th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="d6ffa-109">要求</span><span class="sxs-lookup"><span data-stu-id="d6ffa-109">Requirements</span></span>

<span data-ttu-id="d6ffa-110">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d6ffa-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>
<span data-ttu-id="d6ffa-111">**标头：** 无**库：** 无 **.NET Framework 版本：**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="d6ffa-111">**Header:** None **Library:** None **.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="d6ffa-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d6ffa-112">See also</span></span>

- [<span data-ttu-id="d6ffa-113">调试</span><span class="sxs-lookup"><span data-stu-id="d6ffa-113">Debugging</span></span>](index.md)
- [<span data-ttu-id="d6ffa-114">IXCLRDataProcess 接口</span><span class="sxs-lookup"><span data-stu-id="d6ffa-114">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
