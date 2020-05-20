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
ms.openlocfilehash: fa6297e926d53c02bb0d1af7b59b45b8ee152399
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616458"
---
# <a name="couninitializeee-function"></a><span data-ttu-id="7d127-102">CoUninitializeEE 函数</span><span class="sxs-lookup"><span data-stu-id="7d127-102">CoUninitializeEE Function</span></span>
<span data-ttu-id="7d127-103">`CoUninitializeEE`已过时，不提供任何功能。</span><span class="sxs-lookup"><span data-stu-id="7d127-103">`CoUninitializeEE` is obsolete and provides no functionality.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d127-104">语法</span><span class="sxs-lookup"><span data-stu-id="7d127-104">Syntax</span></span>  
  
```cpp  
void CoUninitializeEE (  
    BOOL fFlags  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="7d127-105">备注</span><span class="sxs-lookup"><span data-stu-id="7d127-105">Remarks</span></span>  
 <span data-ttu-id="7d127-106">不能从进程中卸载公共语言运行时的执行引擎。</span><span class="sxs-lookup"><span data-stu-id="7d127-106">The common language runtime execution engine cannot be unloaded from a process.</span></span> <span data-ttu-id="7d127-107">若要关闭执行引擎，请调用[CorExitProcess](corexitprocess-function.md)。</span><span class="sxs-lookup"><span data-stu-id="7d127-107">To shut down the execution engine call [CorExitProcess](corexitprocess-function.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d127-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7d127-108">See also</span></span>

- [<span data-ttu-id="7d127-109">CoInitializeEE 函数</span><span class="sxs-lookup"><span data-stu-id="7d127-109">CoInitializeEE Function</span></span>](coinitializeee-function.md)
- [<span data-ttu-id="7d127-110">元数据全局静态函数</span><span class="sxs-lookup"><span data-stu-id="7d127-110">Metadata Global Static Functions</span></span>](../metadata/metadata-global-static-functions.md)
