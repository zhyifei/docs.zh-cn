---
title: CoInitializeCor 函数
ms.date: 03/30/2017
api_name:
- CoInitializeCor
api_location:
- mscoree.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CoInitializeCor
helpviewer_keywords:
- CoInitializeCor function [.NET Framework hosting]
ms.assetid: 9b9079fb-579e-4141-b3f0-791072dd40dc
topic_type:
- apiref
ms.openlocfilehash: 188f98504fa73c4a85615a4e688bae02d966b9b6
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616744"
---
# <a name="coinitializecor-function"></a><span data-ttu-id="6bf7c-102">CoInitializeCor 函数</span><span class="sxs-lookup"><span data-stu-id="6bf7c-102">CoInitializeCor Function</span></span>
<span data-ttu-id="6bf7c-103">`CoInitializeCor` 已过时。</span><span class="sxs-lookup"><span data-stu-id="6bf7c-103">`CoInitializeCor` is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6bf7c-104">语法</span><span class="sxs-lookup"><span data-stu-id="6bf7c-104">Syntax</span></span>  
  
```cpp  
STDAPI CoInitializeCor (  
    DWORD fFlags  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="6bf7c-105">备注</span><span class="sxs-lookup"><span data-stu-id="6bf7c-105">Remarks</span></span>  
 <span data-ttu-id="6bf7c-106">若要初始化公共语言运行时，请使用[CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)或[CorBindToCurrentRuntime](corbindtocurrentruntime-function.md)。</span><span class="sxs-lookup"><span data-stu-id="6bf7c-106">To initialize the common language runtime, use either [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) or [CorBindToCurrentRuntime](corbindtocurrentruntime-function.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6bf7c-107">要求</span><span class="sxs-lookup"><span data-stu-id="6bf7c-107">Requirements</span></span>  
 <span data-ttu-id="6bf7c-108">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="6bf7c-108">**Header:** Cor.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bf7c-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6bf7c-109">See also</span></span>

- [<span data-ttu-id="6bf7c-110">元数据全局静态函数</span><span class="sxs-lookup"><span data-stu-id="6bf7c-110">Metadata Global Static Functions</span></span>](../metadata/metadata-global-static-functions.md)
