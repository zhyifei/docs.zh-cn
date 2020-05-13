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
ms.openlocfilehash: ab1351af042aba5042cc7a04614bc3cf14f7d7ae
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379464"
---
# <a name="icordebugstepper2setjmc-method"></a><span data-ttu-id="b7f42-102">ICorDebugStepper2::SetJMC 方法</span><span class="sxs-lookup"><span data-stu-id="b7f42-102">ICorDebugStepper2::SetJMC Method</span></span>
<span data-ttu-id="b7f42-103">设置一个值，该值指定此 ICorDebugStepper 是否仅通过应用程序开发人员编写的代码执行步骤。</span><span class="sxs-lookup"><span data-stu-id="b7f42-103">Sets a value that specifies whether this ICorDebugStepper steps only through code that is authored by an application's developer.</span></span> <span data-ttu-id="b7f42-104">此过程也称为 "仅我的代码" （JMC）调试。</span><span class="sxs-lookup"><span data-stu-id="b7f42-104">This process is also known as just my code (JMC) debugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7f42-105">语法</span><span class="sxs-lookup"><span data-stu-id="b7f42-105">Syntax</span></span>  
  
```cpp  
HRESULT SetJMC (  
    [in] BOOL    fIsJMCStepper  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b7f42-106">参数</span><span class="sxs-lookup"><span data-stu-id="b7f42-106">Parameters</span></span>  
 `fIsJMCStepper`  
 <span data-ttu-id="b7f42-107">中如果设置为， `true` 则仅通过由应用程序开发人员编写的代码执行，否则设置为 `false` 。</span><span class="sxs-lookup"><span data-stu-id="b7f42-107">[in] Set to `true` to step only through code that is authored by an application's developer; otherwise, set to `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7f42-108">要求</span><span class="sxs-lookup"><span data-stu-id="b7f42-108">Requirements</span></span>  
 <span data-ttu-id="b7f42-109">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b7f42-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7f42-110">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b7f42-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b7f42-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b7f42-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b7f42-112">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7f42-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
