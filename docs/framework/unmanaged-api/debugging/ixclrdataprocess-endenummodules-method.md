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
ms.openlocfilehash: cd49ae5fa274c577cfa3c04ec599e488384dfc64
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2019
ms.locfileid: "54416361"
---
# <a name="ixclrdataprocessendenummodules-method"></a><span data-ttu-id="f7dfe-102">IXCLRDataProcess::EndEnumModules 方法</span><span class="sxs-lookup"><span data-stu-id="f7dfe-102">IXCLRDataProcess::EndEnumModules Method</span></span>

<span data-ttu-id="f7dfe-103">释放由模块枚举过程中使用的内部迭代器使用的资源。</span><span class="sxs-lookup"><span data-stu-id="f7dfe-103">Releases the resources used by internal iterators used during module enumeration.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="f7dfe-104">语法</span><span class="sxs-lookup"><span data-stu-id="f7dfe-104">Syntax</span></span>
```
HRESULT EndEnumModules(
    [in] CLRDATA_ENUM handle
);
```

### <a name="parameters"></a><span data-ttu-id="f7dfe-105">参数</span><span class="sxs-lookup"><span data-stu-id="f7dfe-105">Parameters</span></span>
<span data-ttu-id="f7dfe-106">`handle` [out]枚举模块句柄。</span><span class="sxs-lookup"><span data-stu-id="f7dfe-106">`handle` [out] A handle for enumerating the modules.</span></span>

## <a name="remarks"></a><span data-ttu-id="f7dfe-107">备注</span><span class="sxs-lookup"><span data-stu-id="f7dfe-107">Remarks</span></span>

<span data-ttu-id="f7dfe-108">提供的方法属于`IXCLRDataProcess`接口，并对应于虚拟方法表的 26 槽。</span><span class="sxs-lookup"><span data-stu-id="f7dfe-108">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 26th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="f7dfe-109">要求</span><span class="sxs-lookup"><span data-stu-id="f7dfe-109">Requirements</span></span>

<span data-ttu-id="f7dfe-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f7dfe-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>   
<span data-ttu-id="f7dfe-111">**标头：** 无</span><span class="sxs-lookup"><span data-stu-id="f7dfe-111">**Header:** None</span></span>   
<span data-ttu-id="f7dfe-112">**库：** 无</span><span class="sxs-lookup"><span data-stu-id="f7dfe-112">**Library:** None</span></span>   
<span data-ttu-id="f7dfe-113">**.NET Framework 版本：**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="f7dfe-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>   

## <a name="see-also"></a><span data-ttu-id="f7dfe-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="f7dfe-114">See Also</span></span>

- [<span data-ttu-id="f7dfe-115">调试</span><span class="sxs-lookup"><span data-stu-id="f7dfe-115">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="f7dfe-116">IXCLRDataProcess 接口</span><span class="sxs-lookup"><span data-stu-id="f7dfe-116">IXCLRDataProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdataprocess-interface.md)
