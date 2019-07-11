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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5c6b53d23410dd310766dab44664c8cd865ee9ba
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67771681"
---
# <a name="icordebugstepper2setjmc-method"></a><span data-ttu-id="41430-102">ICorDebugStepper2::SetJMC 方法</span><span class="sxs-lookup"><span data-stu-id="41430-102">ICorDebugStepper2::SetJMC Method</span></span>
<span data-ttu-id="41430-103">设置一个值，指定是否有此 ICorDebugStepper 步骤只能通过由应用程序的开发人员编写的代码。</span><span class="sxs-lookup"><span data-stu-id="41430-103">Sets a value that specifies whether this ICorDebugStepper steps only through code that is authored by an application's developer.</span></span> <span data-ttu-id="41430-104">此过程也称为认为只我的代码 (JMC) 调试。</span><span class="sxs-lookup"><span data-stu-id="41430-104">This process is also known as just my code (JMC) debugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41430-105">语法</span><span class="sxs-lookup"><span data-stu-id="41430-105">Syntax</span></span>  
  
```cpp  
HRESULT SetJMC (  
    [in] BOOL    fIsJMCStepper  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="41430-106">参数</span><span class="sxs-lookup"><span data-stu-id="41430-106">Parameters</span></span>  
 `fIsJMCStepper`  
 <span data-ttu-id="41430-107">[in]设置为`true`逐句通过代码编写的应用程序的开发人员; 否则，将设置为仅`false`。</span><span class="sxs-lookup"><span data-stu-id="41430-107">[in] Set to `true` to step only through code that is authored by an application's developer; otherwise, set to `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41430-108">要求</span><span class="sxs-lookup"><span data-stu-id="41430-108">Requirements</span></span>  
 <span data-ttu-id="41430-109">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="41430-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41430-110">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="41430-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="41430-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="41430-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="41430-112">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="41430-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
