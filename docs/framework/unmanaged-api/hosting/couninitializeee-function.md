---
title: "CoUninitializeEE 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CoUninitializeEE
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: CoUninitializeEE
helpviewer_keywords: CoUninitializeEE function [.NET Framework hosting]
ms.assetid: 5f5a311a-839a-465f-89d9-ff1c74da9736
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d64064c29d2a03578305f71a37e759907814727e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="couninitializeee-function"></a><span data-ttu-id="e9663-102">CoUninitializeEE 函数</span><span class="sxs-lookup"><span data-stu-id="e9663-102">CoUninitializeEE Function</span></span>
<span data-ttu-id="e9663-103">`CoUninitializeEE`已过时，不提供任何功能。</span><span class="sxs-lookup"><span data-stu-id="e9663-103">`CoUninitializeEE` is obsolete and provides no functionality.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9663-104">语法</span><span class="sxs-lookup"><span data-stu-id="e9663-104">Syntax</span></span>  
  
```  
void CoUninitializeEE (  
    BOOL fFlags  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="e9663-105">备注</span><span class="sxs-lookup"><span data-stu-id="e9663-105">Remarks</span></span>  
 <span data-ttu-id="e9663-106">公共语言运行时执行引擎无法从进程中卸载。</span><span class="sxs-lookup"><span data-stu-id="e9663-106">The common language runtime execution engine cannot be unloaded from a process.</span></span> <span data-ttu-id="e9663-107">若要关闭的情况下执行引擎调用[CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md)。</span><span class="sxs-lookup"><span data-stu-id="e9663-107">To shut down the execution engine call [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9663-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e9663-108">See Also</span></span>  
 [<span data-ttu-id="e9663-109">CoInitializeEE 函数</span><span class="sxs-lookup"><span data-stu-id="e9663-109">CoInitializeEE Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md)  
 [<span data-ttu-id="e9663-110">元数据全局静态函数</span><span class="sxs-lookup"><span data-stu-id="e9663-110">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
