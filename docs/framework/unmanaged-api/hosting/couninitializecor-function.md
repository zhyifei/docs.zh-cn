---
title: "CoUninitializeCor 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- CoUninitializeCor
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- CoUninitializeCor
helpviewer_keywords:
- CoUninitializeCor function [.NET Framework hosting]
ms.assetid: 50a95b8b-9766-470e-bb29-2c7ecddfd4a1
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b9f50892b44cf8ce22cc126fe22323c8b0bbe6be
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="couninitializecor-function"></a><span data-ttu-id="b70cc-102">CoUninitializeCor 函数</span><span class="sxs-lookup"><span data-stu-id="b70cc-102">CoUninitializeCor Function</span></span>
<span data-ttu-id="b70cc-103">`CoUninitializeCor` 已过时。</span><span class="sxs-lookup"><span data-stu-id="b70cc-103">`CoUninitializeCor` is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b70cc-104">语法</span><span class="sxs-lookup"><span data-stu-id="b70cc-104">Syntax</span></span>  
  
```  
STDAPI_(void) CoUninitializeCor(void);  
```  
  
## <a name="remarks"></a><span data-ttu-id="b70cc-105">备注</span><span class="sxs-lookup"><span data-stu-id="b70cc-105">Remarks</span></span>  
 <span data-ttu-id="b70cc-106">公共语言运行时不能为从进程中卸载。</span><span class="sxs-lookup"><span data-stu-id="b70cc-106">The common language runtime cannot be unloaded from a process.</span></span> <span data-ttu-id="b70cc-107">若要完全删除从正在运行的进程的运行时，必须关闭该进程。</span><span class="sxs-lookup"><span data-stu-id="b70cc-107">To completely remove the runtime from a running process, you must shut down that process.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b70cc-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="b70cc-108">See Also</span></span>  
 [<span data-ttu-id="b70cc-109">元数据全局静态函数</span><span class="sxs-lookup"><span data-stu-id="b70cc-109">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
