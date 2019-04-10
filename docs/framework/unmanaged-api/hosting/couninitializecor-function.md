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
ms.openlocfilehash: 0845c4d493cb3c750931a0ae2ad92b628a255c0c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59202711"
---
# <a name="couninitializecor-function"></a><span data-ttu-id="a338d-102">CoUninitializeCor 函数</span><span class="sxs-lookup"><span data-stu-id="a338d-102">CoUninitializeCor Function</span></span>
`CoUninitializeCor` <span data-ttu-id="a338d-103">已过时。</span><span class="sxs-lookup"><span data-stu-id="a338d-103">is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a338d-104">语法</span><span class="sxs-lookup"><span data-stu-id="a338d-104">Syntax</span></span>  
  
```  
STDAPI_(void) CoUninitializeCor(void);  
```  
  
## <a name="remarks"></a><span data-ttu-id="a338d-105">备注</span><span class="sxs-lookup"><span data-stu-id="a338d-105">Remarks</span></span>  
 <span data-ttu-id="a338d-106">公共语言运行时不能从进程中卸载。</span><span class="sxs-lookup"><span data-stu-id="a338d-106">The common language runtime cannot be unloaded from a process.</span></span> <span data-ttu-id="a338d-107">若要从正在运行的进程中完全删除运行时，必须关闭该进程。</span><span class="sxs-lookup"><span data-stu-id="a338d-107">To completely remove the runtime from a running process, you must shut down that process.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a338d-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="a338d-108">See also</span></span>

- [<span data-ttu-id="a338d-109">元数据全局静态函数</span><span class="sxs-lookup"><span data-stu-id="a338d-109">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
