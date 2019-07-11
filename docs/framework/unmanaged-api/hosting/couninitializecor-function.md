---
title: CoUninitializeCor 函数
ms.date: 03/30/2017
api_name:
- CoUninitializeCor
api_location:
- mscoree.dll
- mscorsvr.dll
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
ms.openlocfilehash: e3ce0b9a40d5375f563662d73964d28724209dcd
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67758292"
---
# <a name="couninitializecor-function"></a><span data-ttu-id="65a99-102">CoUninitializeCor 函数</span><span class="sxs-lookup"><span data-stu-id="65a99-102">CoUninitializeCor Function</span></span>
<span data-ttu-id="65a99-103">`CoUninitializeCor` 已过时。</span><span class="sxs-lookup"><span data-stu-id="65a99-103">`CoUninitializeCor` is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65a99-104">语法</span><span class="sxs-lookup"><span data-stu-id="65a99-104">Syntax</span></span>  
  
```cpp  
STDAPI_(void) CoUninitializeCor(void);  
```  
  
## <a name="remarks"></a><span data-ttu-id="65a99-105">备注</span><span class="sxs-lookup"><span data-stu-id="65a99-105">Remarks</span></span>  
 <span data-ttu-id="65a99-106">公共语言运行时不能从进程中卸载。</span><span class="sxs-lookup"><span data-stu-id="65a99-106">The common language runtime cannot be unloaded from a process.</span></span> <span data-ttu-id="65a99-107">若要从正在运行的进程中完全删除运行时，必须关闭该进程。</span><span class="sxs-lookup"><span data-stu-id="65a99-107">To completely remove the runtime from a running process, you must shut down that process.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65a99-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="65a99-108">See also</span></span>

- [<span data-ttu-id="65a99-109">元数据全局静态函数</span><span class="sxs-lookup"><span data-stu-id="65a99-109">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
