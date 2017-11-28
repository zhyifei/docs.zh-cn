---
title: "ICorThreadpool::CorCallOrQueueUserWorkItem 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorThreadpool.CorCallOrQueueUserWorkItem
api_location: mscoree.dll
api_type: COM
f1_keywords: CorCallOrQueueUserWorkItem
helpviewer_keywords:
- ICorThreadpool::CorCallOrQueueUserWorkItem method [.NET Framework hosting]
- CorCallOrQueueUserWorkItem method [.NET Framework hosting]
ms.assetid: a2081223-84ca-4331-a8d3-9352f422f3e7
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1834a710fa33e1860e0742cae805393d548b6c4b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icorthreadpoolcorcallorqueueuserworkitem-method"></a><span data-ttu-id="e4d8b-102">ICorThreadpool::CorCallOrQueueUserWorkItem 方法</span><span class="sxs-lookup"><span data-stu-id="e4d8b-102">ICorThreadpool::CorCallOrQueueUserWorkItem Method</span></span>
<span data-ttu-id="e4d8b-103">此方法支持 .NET Framework 基础结构，但不适合直接在代码中使用。</span><span class="sxs-lookup"><span data-stu-id="e4d8b-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4d8b-104">语法</span><span class="sxs-lookup"><span data-stu-id="e4d8b-104">Syntax</span></span>  
  
```  
HRESULT CorCallOrQueueUserWorkItem (  
    [in] LPTHREAD_START_ROUTINE Function,  
    [in] PVOID                  Context,  
    [out] BOOL*                 result  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="e4d8b-105">要求</span><span class="sxs-lookup"><span data-stu-id="e4d8b-105">Requirements</span></span>  
 <span data-ttu-id="e4d8b-106">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e4d8b-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e4d8b-107">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e4d8b-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e4d8b-108">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="e4d8b-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e4d8b-109">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e4d8b-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4d8b-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e4d8b-110">See Also</span></span>  
 [<span data-ttu-id="e4d8b-111">ICorThreadpool 接口</span><span class="sxs-lookup"><span data-stu-id="e4d8b-111">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)
