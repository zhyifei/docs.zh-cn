---
title: ICorDebugStepper2::SetJMC 方法
ms.date: 03/30/2017
api_name:
- ICorDebugStepper2.SetJMC
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper2::SetJMC
helpviewer_keywords:
- ICorDebugStepper2::SetJMC method [.NET Framework debugging]
- SetJMC method [.NET Framework debugging]
ms.assetid: f5cdc135-6db4-4b32-9dd1-260ec58b774f
topic_type:
- apiref
ms.openlocfilehash: 6c076dd2912a22e4f9492492a2d7a9fb73db88e8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139043"
---
# <a name="icordebugstepper2setjmc-method"></a><span data-ttu-id="06779-102">ICorDebugStepper2::SetJMC 方法</span><span class="sxs-lookup"><span data-stu-id="06779-102">ICorDebugStepper2::SetJMC Method</span></span>
<span data-ttu-id="06779-103">设置一个值，该值指定此 ICorDebugStepper 是否仅通过应用程序开发人员编写的代码执行步骤。</span><span class="sxs-lookup"><span data-stu-id="06779-103">Sets a value that specifies whether this ICorDebugStepper steps only through code that is authored by an application's developer.</span></span> <span data-ttu-id="06779-104">此过程也称为 "仅我的代码" （JMC）调试。</span><span class="sxs-lookup"><span data-stu-id="06779-104">This process is also known as just my code (JMC) debugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06779-105">语法</span><span class="sxs-lookup"><span data-stu-id="06779-105">Syntax</span></span>  
  
```cpp  
HRESULT SetJMC (  
    [in] BOOL    fIsJMCStepper  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="06779-106">参数</span><span class="sxs-lookup"><span data-stu-id="06779-106">Parameters</span></span>  
 `fIsJMCStepper`  
 <span data-ttu-id="06779-107">中设置为仅在应用程序开发人员编写的代码中 `true`否则，设置为 `false`。</span><span class="sxs-lookup"><span data-stu-id="06779-107">[in] Set to `true` to step only through code that is authored by an application's developer; otherwise, set to `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06779-108">要求</span><span class="sxs-lookup"><span data-stu-id="06779-108">Requirements</span></span>  
 <span data-ttu-id="06779-109">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="06779-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06779-110">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="06779-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="06779-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="06779-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="06779-112">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06779-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
