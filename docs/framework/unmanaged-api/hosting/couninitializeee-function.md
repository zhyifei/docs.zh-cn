---
title: CoUninitializeEE 函数
ms.date: 03/30/2017
api_name:
- CoUninitializeEE
api_location:
- mscoree.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CoUninitializeEE
helpviewer_keywords:
- CoUninitializeEE function [.NET Framework hosting]
ms.assetid: 5f5a311a-839a-465f-89d9-ff1c74da9736
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7b3712b4cb66facc105a03d7bfad235f09339056
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59193000"
---
# <a name="couninitializeee-function"></a><span data-ttu-id="96702-102">CoUninitializeEE 函数</span><span class="sxs-lookup"><span data-stu-id="96702-102">CoUninitializeEE Function</span></span>
`CoUninitializeEE` <span data-ttu-id="96702-103">已过时，不提供任何功能。</span><span class="sxs-lookup"><span data-stu-id="96702-103">is obsolete and provides no functionality.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96702-104">语法</span><span class="sxs-lookup"><span data-stu-id="96702-104">Syntax</span></span>  
  
```  
void CoUninitializeEE (  
    BOOL fFlags  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="96702-105">备注</span><span class="sxs-lookup"><span data-stu-id="96702-105">Remarks</span></span>  
 <span data-ttu-id="96702-106">公共语言运行时执行引擎不能从进程中卸载。</span><span class="sxs-lookup"><span data-stu-id="96702-106">The common language runtime execution engine cannot be unloaded from a process.</span></span> <span data-ttu-id="96702-107">若要关闭的情况下执行引擎调用[CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md)。</span><span class="sxs-lookup"><span data-stu-id="96702-107">To shut down the execution engine call [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96702-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="96702-108">See also</span></span>

- [<span data-ttu-id="96702-109">CoInitializeEE 函数</span><span class="sxs-lookup"><span data-stu-id="96702-109">CoInitializeEE Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md)
- [<span data-ttu-id="96702-110">元数据全局静态函数</span><span class="sxs-lookup"><span data-stu-id="96702-110">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
