---
title: IXCLRDataProcess::EndEnumModules 方法
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
ms.openlocfilehash: de30384b4c12c4fcac3eafe580484685f8a43fa4
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2019
ms.locfileid: "59611427"
---
# <a name="ixclrdataprocessendenummodules-method"></a><span data-ttu-id="0f8ae-102">IXCLRDataProcess::EndEnumModules 方法</span><span class="sxs-lookup"><span data-stu-id="0f8ae-102">IXCLRDataProcess::EndEnumModules Method</span></span>

<span data-ttu-id="0f8ae-103">释放由模块枚举过程中使用的内部迭代器使用的资源。</span><span class="sxs-lookup"><span data-stu-id="0f8ae-103">Releases the resources used by internal iterators used during module enumeration.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="0f8ae-104">语法</span><span class="sxs-lookup"><span data-stu-id="0f8ae-104">Syntax</span></span>

```cpp
HRESULT EndEnumModules(
    [in] CLRDATA_ENUM handle
);
```

## <a name="parameters"></a><span data-ttu-id="0f8ae-105">参数</span><span class="sxs-lookup"><span data-stu-id="0f8ae-105">Parameters</span></span>

`handle`\
<span data-ttu-id="0f8ae-106">[out]枚举模块句柄。</span><span class="sxs-lookup"><span data-stu-id="0f8ae-106">[out] A handle for enumerating the modules.</span></span>

## <a name="remarks"></a><span data-ttu-id="0f8ae-107">备注</span><span class="sxs-lookup"><span data-stu-id="0f8ae-107">Remarks</span></span>

<span data-ttu-id="0f8ae-108">提供的方法属于`IXCLRDataProcess`接口，并对应于虚拟方法表的 26 槽。</span><span class="sxs-lookup"><span data-stu-id="0f8ae-108">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 26th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="0f8ae-109">要求</span><span class="sxs-lookup"><span data-stu-id="0f8ae-109">Requirements</span></span>

<span data-ttu-id="0f8ae-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0f8ae-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>
<span data-ttu-id="0f8ae-111">**标头：** 无**库：** 无 **.NET Framework 版本：** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="0f8ae-111">**Header:** None **Library:** None **.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="0f8ae-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="0f8ae-112">See also</span></span>

- [<span data-ttu-id="0f8ae-113">调试</span><span class="sxs-lookup"><span data-stu-id="0f8ae-113">Debugging</span></span>](index.md)
- [<span data-ttu-id="0f8ae-114">IXCLRDataProcess 接口</span><span class="sxs-lookup"><span data-stu-id="0f8ae-114">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
