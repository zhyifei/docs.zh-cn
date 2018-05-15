---
title: CoUninitializeCor 函数
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 305a8d7b5a800c46ed814b1e654947859dc9bd03
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="couninitializecor-function"></a><span data-ttu-id="6f0b5-102">CoUninitializeCor 函数</span><span class="sxs-lookup"><span data-stu-id="6f0b5-102">CoUninitializeCor Function</span></span>
<span data-ttu-id="6f0b5-103">`CoUninitializeCor` 已过时。</span><span class="sxs-lookup"><span data-stu-id="6f0b5-103">`CoUninitializeCor` is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f0b5-104">语法</span><span class="sxs-lookup"><span data-stu-id="6f0b5-104">Syntax</span></span>  
  
```  
STDAPI_(void) CoUninitializeCor(void);  
```  
  
## <a name="remarks"></a><span data-ttu-id="6f0b5-105">备注</span><span class="sxs-lookup"><span data-stu-id="6f0b5-105">Remarks</span></span>  
 <span data-ttu-id="6f0b5-106">公共语言运行时不能为从进程中卸载。</span><span class="sxs-lookup"><span data-stu-id="6f0b5-106">The common language runtime cannot be unloaded from a process.</span></span> <span data-ttu-id="6f0b5-107">若要完全删除从正在运行的进程的运行时，必须关闭该进程。</span><span class="sxs-lookup"><span data-stu-id="6f0b5-107">To completely remove the runtime from a running process, you must shut down that process.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f0b5-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="6f0b5-108">See Also</span></span>  
 [<span data-ttu-id="6f0b5-109">元数据全局静态函数</span><span class="sxs-lookup"><span data-stu-id="6f0b5-109">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
