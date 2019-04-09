---
title: IXCLRDataProcess::GetAppDomainByUniqueId 方法
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::GetAppDomainByUniqueId Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::GetAppDomainByUniqueId Method
helpviewer.keywords:
- IXCLRDataProcess::GetAppDomainByUniqueId Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 257fa2cf03a62ea888b76519aa5c9f9e84038045
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59126498"
---
# <a name="ixclrdataprocessgetappdomainbyuniqueid-method"></a><span data-ttu-id="eb08d-102">IXCLRDataProcess::GetAppDomainByUniqueId 方法</span><span class="sxs-lookup"><span data-stu-id="eb08d-102">IXCLRDataProcess::GetAppDomainByUniqueId Method</span></span>

<span data-ttu-id="eb08d-103">获取`AppDomain`基于它的唯一标识符的进程中。</span><span class="sxs-lookup"><span data-stu-id="eb08d-103">Gets an `AppDomain` in a process based on its unique identifier.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="eb08d-104">语法</span><span class="sxs-lookup"><span data-stu-id="eb08d-104">Syntax</span></span>
```
HRESULT GetAppDomainByUniqueID(
    [in] ULONG64               id,
    [out] IXCLRDataAppDomain **appDomain
);
```

## <a name="parameters"></a><span data-ttu-id="eb08d-105">参数</span><span class="sxs-lookup"><span data-stu-id="eb08d-105">Parameters</span></span>

`id`\
<span data-ttu-id="eb08d-106">[in]AppDomain 的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="eb08d-106">[in] The unique identifier of the AppDomain</span></span>

`appDomain`\
<span data-ttu-id="eb08d-107">[out]AppDomain</span><span class="sxs-lookup"><span data-stu-id="eb08d-107">[out] The AppDomain</span></span>

## <a name="remarks"></a><span data-ttu-id="eb08d-108">备注</span><span class="sxs-lookup"><span data-stu-id="eb08d-108">Remarks</span></span>

<span data-ttu-id="eb08d-109">提供的方法属于`IXCLRDataProcess`接口，并对应于虚拟方法表的 20 槽。</span><span class="sxs-lookup"><span data-stu-id="eb08d-109">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 20th slot of the virtual method table.</span></span> <span data-ttu-id="eb08d-110">`IXCLRDataAppDomain*`返回用于与其他 Api 的交互。</span><span class="sxs-lookup"><span data-stu-id="eb08d-110">The `IXCLRDataAppDomain*` returned is used for interaction with other APIs.</span></span>

## <a name="requirements"></a><span data-ttu-id="eb08d-111">要求</span><span class="sxs-lookup"><span data-stu-id="eb08d-111">Requirements</span></span>
<span data-ttu-id="eb08d-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="eb08d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="eb08d-113">**标头：** None</span><span class="sxs-lookup"><span data-stu-id="eb08d-113">**Header:** None</span></span>  
<span data-ttu-id="eb08d-114">**库：** None</span><span class="sxs-lookup"><span data-stu-id="eb08d-114">**Library:** None</span></span>  
**<span data-ttu-id="eb08d-115">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="eb08d-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a><span data-ttu-id="eb08d-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="eb08d-116">See also</span></span>

- [<span data-ttu-id="eb08d-117">调试</span><span class="sxs-lookup"><span data-stu-id="eb08d-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="eb08d-118">IXCLRDataProcess 接口</span><span class="sxs-lookup"><span data-stu-id="eb08d-118">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
