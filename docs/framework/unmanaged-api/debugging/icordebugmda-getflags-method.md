---
title: ICorDebugMDA::GetFlags 方法
ms.date: 03/30/2017
api_name:
- ICorDebugMDA.GetFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA::GetFlags
helpviewer_keywords:
- ICorDebugMDA::GetFlags method [.NET Framework debugging]
- GetFlags method [.NET Framework debugging]
ms.assetid: 87ce7c5b-fd82-453e-bf55-c8a32150b183
topic_type:
- apiref
ms.openlocfilehash: 4e5939e9e74899a33f28927c4fda09d0a8fb30a0
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209729"
---
# <a name="icordebugmdagetflags-method"></a><span data-ttu-id="46935-102">ICorDebugMDA::GetFlags 方法</span><span class="sxs-lookup"><span data-stu-id="46935-102">ICorDebugMDA::GetFlags Method</span></span>
<span data-ttu-id="46935-103">获取与[ICorDebugMDA](icordebugmda-interface.md)表示的托管调试助手（MDA）关联的标志。</span><span class="sxs-lookup"><span data-stu-id="46935-103">Gets the flags associated with the managed debugging assistant (MDA) represented by [ICorDebugMDA](icordebugmda-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46935-104">语法</span><span class="sxs-lookup"><span data-stu-id="46935-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFlags (  
    [in] CorDebugMDAFlags *pFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="46935-105">参数</span><span class="sxs-lookup"><span data-stu-id="46935-105">Parameters</span></span>  
 `pFlags`  
 <span data-ttu-id="46935-106">中[CorDebugMDAFlags](cordebugmdaflags-enumeration.md)枚举值的按位组合，这些值指定此 MDA 的标志的设置。</span><span class="sxs-lookup"><span data-stu-id="46935-106">[in] A bitwise combination of the [CorDebugMDAFlags](cordebugmdaflags-enumeration.md) enumeration values that specify the settings of the flags for this MDA.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="46935-107">要求</span><span class="sxs-lookup"><span data-stu-id="46935-107">Requirements</span></span>  
 <span data-ttu-id="46935-108">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="46935-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="46935-109">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="46935-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="46935-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="46935-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="46935-111">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="46935-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46935-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="46935-112">See also</span></span>

- [<span data-ttu-id="46935-113">ICorDebugMDA 接口</span><span class="sxs-lookup"><span data-stu-id="46935-113">ICorDebugMDA Interface</span></span>](icordebugmda-interface.md)
- [<span data-ttu-id="46935-114">使用托管调试助手诊断错误</span><span class="sxs-lookup"><span data-stu-id="46935-114">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
