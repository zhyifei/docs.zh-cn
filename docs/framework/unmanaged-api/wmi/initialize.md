---
title: "Initialize 函数 （非托管 API 参考）"
description: "Initialize 函数执行 WMI 初始化。"
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: Initialize
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: Initialize
helpviewer_keywords: Initialize function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d62d959c5dfeac237abb20b86df87ae07a077dbd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="initialize-function"></a><span data-ttu-id="00265-103">Initialize 函数</span><span class="sxs-lookup"><span data-stu-id="00265-103">Initialize function</span></span>
<span data-ttu-id="00265-104">执行 WMI 初始化。</span><span class="sxs-lookup"><span data-stu-id="00265-104">Performs WMI initialization.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="00265-105">语法</span><span class="sxs-lookup"><span data-stu-id="00265-105">Syntax</span></span> 
```  
HRESULT Initialize(
   [in] boolean bAllowIManagementObjectQI
); 
```  
## <a name="parameters"></a><span data-ttu-id="00265-106">参数</span><span class="sxs-lookup"><span data-stu-id="00265-106">Parameters</span></span>

`bAllowIManagementObjectQI`   
<span data-ttu-id="00265-107">[in]`true`指明，允许调用 WMI 对象上的 QueryInterface;`false`否则为。</span><span class="sxs-lookup"><span data-stu-id="00265-107">[in] `true` to indicate that calls to QueryInterface on WMI objects are allowed; `false` otherwise.</span></span>

## <a name="return-value"></a><span data-ttu-id="00265-108">返回值</span><span class="sxs-lookup"><span data-stu-id="00265-108">Return value</span></span>

<span data-ttu-id="00265-109">函数始终返回`S_OK`(0)。</span><span class="sxs-lookup"><span data-stu-id="00265-109">The function always returns `S_OK` (0).</span></span>
  
## <a name="requirements"></a><span data-ttu-id="00265-110">惠?</span><span class="sxs-lookup"><span data-stu-id="00265-110">Requirements</span></span>  
 <span data-ttu-id="00265-111">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="00265-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00265-112">**标头：** WMINet_Utils.def</span><span class="sxs-lookup"><span data-stu-id="00265-112">**Header:** WMINet_Utils.def</span></span>  
  
 <span data-ttu-id="00265-113">**.NET framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="00265-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00265-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="00265-114">See also</span></span>  
[<span data-ttu-id="00265-115">WMI 和性能计数器 （非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="00265-115">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
