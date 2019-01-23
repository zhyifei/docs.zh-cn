---
title: CoUninitializeEE 函数
ms.date: 03/30/2017
api_name:
- CoUninitializeEE
api_location:
- mscoree.dll
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
ms.openlocfilehash: ef5faff6682ed6c043e81212f2cb27d4cfbd813d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54601852"
---
# <a name="couninitializeee-function"></a><span data-ttu-id="1b11a-102">CoUninitializeEE 函数</span><span class="sxs-lookup"><span data-stu-id="1b11a-102">CoUninitializeEE Function</span></span>
<span data-ttu-id="1b11a-103">`CoUninitializeEE` 已过时，不提供任何功能。</span><span class="sxs-lookup"><span data-stu-id="1b11a-103">`CoUninitializeEE` is obsolete and provides no functionality.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b11a-104">语法</span><span class="sxs-lookup"><span data-stu-id="1b11a-104">Syntax</span></span>  
  
```  
void CoUninitializeEE (  
    BOOL fFlags  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="1b11a-105">备注</span><span class="sxs-lookup"><span data-stu-id="1b11a-105">Remarks</span></span>  
 <span data-ttu-id="1b11a-106">公共语言运行时执行引擎不能从进程中卸载。</span><span class="sxs-lookup"><span data-stu-id="1b11a-106">The common language runtime execution engine cannot be unloaded from a process.</span></span> <span data-ttu-id="1b11a-107">若要关闭的情况下执行引擎调用[CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md)。</span><span class="sxs-lookup"><span data-stu-id="1b11a-107">To shut down the execution engine call [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b11a-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="1b11a-108">See also</span></span>
- [<span data-ttu-id="1b11a-109">CoInitializeEE 函数</span><span class="sxs-lookup"><span data-stu-id="1b11a-109">CoInitializeEE Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md)
- [<span data-ttu-id="1b11a-110">元数据全局静态函数</span><span class="sxs-lookup"><span data-stu-id="1b11a-110">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
