---
title: IXCLRDataProcess::StartEnumModules 方法
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
ms.openlocfilehash: 4a086157b27b7426cb6d5f17f13426c0f26d2b2d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54658216"
---
# <a name="ixclrdataprocessstartenummodules-method"></a><span data-ttu-id="6ac2a-102">IXCLRDataProcess::StartEnumModules 方法</span><span class="sxs-lookup"><span data-stu-id="6ac2a-102">IXCLRDataProcess::StartEnumModules Method</span></span>

<span data-ttu-id="6ac2a-103">提供要枚举的进程的模块的句柄。</span><span class="sxs-lookup"><span data-stu-id="6ac2a-103">Provides a handle to enumerate the modules of a process.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="6ac2a-104">语法</span><span class="sxs-lookup"><span data-stu-id="6ac2a-104">Syntax</span></span>

```
HRESULT StartEnumModules(
    [out] CLRDATA_ENUM *handle
);
```

### <a name="parameters"></a><span data-ttu-id="6ac2a-105">参数</span><span class="sxs-lookup"><span data-stu-id="6ac2a-105">Parameters</span></span>

<span data-ttu-id="6ac2a-106">`handle` [out]枚举模块句柄。</span><span class="sxs-lookup"><span data-stu-id="6ac2a-106">`handle` [out] A handle for enumerating the modules.</span></span>

## <a name="remarks"></a><span data-ttu-id="6ac2a-107">备注</span><span class="sxs-lookup"><span data-stu-id="6ac2a-107">Remarks</span></span>

<span data-ttu-id="6ac2a-108">提供的方法属于`IXCLRDataProcess`接口，并对应于虚拟方法表 24 槽。</span><span class="sxs-lookup"><span data-stu-id="6ac2a-108">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 24th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="6ac2a-109">要求</span><span class="sxs-lookup"><span data-stu-id="6ac2a-109">Requirements</span></span>

<span data-ttu-id="6ac2a-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6ac2a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="6ac2a-111">**标头：** 无</span><span class="sxs-lookup"><span data-stu-id="6ac2a-111">**Header:** None</span></span>  
<span data-ttu-id="6ac2a-112">**库：** 无</span><span class="sxs-lookup"><span data-stu-id="6ac2a-112">**Library:** None</span></span>  
<span data-ttu-id="6ac2a-113">**.NET Framework 版本：**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="6ac2a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="6ac2a-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="6ac2a-114">See also</span></span>

- [<span data-ttu-id="6ac2a-115">CLRDataSourceType 枚举</span><span class="sxs-lookup"><span data-stu-id="6ac2a-115">CLRDataSourceType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="6ac2a-116">调试</span><span class="sxs-lookup"><span data-stu-id="6ac2a-116">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="6ac2a-117">IXCLRDataProcess 接口</span><span class="sxs-lookup"><span data-stu-id="6ac2a-117">IXCLRDataProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdataprocess-interface.md)
