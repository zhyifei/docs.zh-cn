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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 556d26ac7e4fb8847f132d19bd2e749aff345abf
ms.sourcegitcommit: 79066169e93d9d65203028b21983574ad9dcf6b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/01/2019
ms.locfileid: "57211840"
---
# <a name="coinitializecor-function"></a><span data-ttu-id="8b906-102">CoInitializeCor 函数</span><span class="sxs-lookup"><span data-stu-id="8b906-102">CoInitializeCor Function</span></span>
<span data-ttu-id="8b906-103">`CoInitializeCor` 已过时。</span><span class="sxs-lookup"><span data-stu-id="8b906-103">`CoInitializeCor` is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b906-104">语法</span><span class="sxs-lookup"><span data-stu-id="8b906-104">Syntax</span></span>  
  
```  
STDAPI CoInitializeCor (  
    DWORD fFlags  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="8b906-105">备注</span><span class="sxs-lookup"><span data-stu-id="8b906-105">Remarks</span></span>  
 <span data-ttu-id="8b906-106">若要初始化公共语言运行时，使用[CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)或[CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)。</span><span class="sxs-lookup"><span data-stu-id="8b906-106">To initialize the common language runtime, use either [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) or [CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8b906-107">要求</span><span class="sxs-lookup"><span data-stu-id="8b906-107">Requirements</span></span>  
 <span data-ttu-id="8b906-108">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="8b906-108">**Header:** Cor.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b906-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="8b906-109">See also</span></span>
- [<span data-ttu-id="8b906-110">元数据全局静态函数</span><span class="sxs-lookup"><span data-stu-id="8b906-110">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
