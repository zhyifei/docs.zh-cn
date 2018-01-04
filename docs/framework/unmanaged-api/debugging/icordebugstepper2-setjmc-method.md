---
title: "ICorDebugStepper2::SetJMC 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugStepper2.SetJMC
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugStepper2::SetJMC
helpviewer_keywords:
- ICorDebugStepper2::SetJMC method [.NET Framework debugging]
- SetJMC method [.NET Framework debugging]
ms.assetid: f5cdc135-6db4-4b32-9dd1-260ec58b774f
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7fbbe0d3e42df073a5718ca037b44f6f2f31ec23
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugstepper2setjmc-method"></a><span data-ttu-id="65234-102">ICorDebugStepper2::SetJMC 方法</span><span class="sxs-lookup"><span data-stu-id="65234-102">ICorDebugStepper2::SetJMC Method</span></span>
<span data-ttu-id="65234-103">设置一个值，指定是否有此 ICorDebugStepper 步骤只能通过由应用程序的开发人员创作的代码。</span><span class="sxs-lookup"><span data-stu-id="65234-103">Sets a value that specifies whether this ICorDebugStepper steps only through code that is authored by an application's developer.</span></span> <span data-ttu-id="65234-104">此过程也称为认为只我的代码 (JMC) 调试。</span><span class="sxs-lookup"><span data-stu-id="65234-104">This process is also known as just my code (JMC) debugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65234-105">语法</span><span class="sxs-lookup"><span data-stu-id="65234-105">Syntax</span></span>  
  
```  
HRESULT SetJMC (  
    [in] BOOL    fIsJMCStepper  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="65234-106">参数</span><span class="sxs-lookup"><span data-stu-id="65234-106">Parameters</span></span>  
 `fIsJMCStepper`  
 <span data-ttu-id="65234-107">[in]设置为`true`逐句通过代码是由应用程序的开发人员创作; 否则，设置为仅`false`。</span><span class="sxs-lookup"><span data-stu-id="65234-107">[in] Set to `true` to step only through code that is authored by an application's developer; otherwise, set to `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="65234-108">惠?</span><span class="sxs-lookup"><span data-stu-id="65234-108">Requirements</span></span>  
 <span data-ttu-id="65234-109">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="65234-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="65234-110">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="65234-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="65234-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="65234-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="65234-112">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="65234-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
