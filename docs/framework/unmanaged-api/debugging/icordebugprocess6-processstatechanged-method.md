---
title: ICorDebugProcess6::ProcessStateChanged 方法
ms.date: 03/30/2017
ms.assetid: fb6d30d9-54f3-462b-8ebf-ce0440791ad5
ms.openlocfilehash: 6be216741e902b15efc3a3ece95cb4a4229960e3
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212837"
---
# <a name="icordebugprocess6processstatechanged-method"></a><span data-ttu-id="e0bda-102">ICorDebugProcess6::ProcessStateChanged 方法</span><span class="sxs-lookup"><span data-stu-id="e0bda-102">ICorDebugProcess6::ProcessStateChanged Method</span></span>
<span data-ttu-id="e0bda-103">通知[ICorDebug](icordebug-interface.md)进程正在运行。</span><span class="sxs-lookup"><span data-stu-id="e0bda-103">Notifies [ICorDebug](icordebug-interface.md) that the process is running.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0bda-104">语法</span><span class="sxs-lookup"><span data-stu-id="e0bda-104">Syntax</span></span>  
  
```cpp  
HRESULT ProcessStateChanged(   [in] CorDebugStateChange change);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e0bda-105">参数</span><span class="sxs-lookup"><span data-stu-id="e0bda-105">Parameters</span></span>  
 `change`  
 <span data-ttu-id="e0bda-106">中[ProcessStateChanged](icordebugprocess6-processstatechanged-method.md)枚举的成员</span><span class="sxs-lookup"><span data-stu-id="e0bda-106">[in] A member of the [ProcessStateChanged](icordebugprocess6-processstatechanged-method.md) enumeration</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e0bda-107">备注</span><span class="sxs-lookup"><span data-stu-id="e0bda-107">Remarks</span></span>  
 <span data-ttu-id="e0bda-108">调试器调用此方法来通知[ICorDebug](icordebug-interface.md)进程正在运行。</span><span class="sxs-lookup"><span data-stu-id="e0bda-108">The debugger calls this method to notify [ICorDebug](icordebug-interface.md) that the process is running.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e0bda-109">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="e0bda-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0bda-110">要求</span><span class="sxs-lookup"><span data-stu-id="e0bda-110">Requirements</span></span>  
 <span data-ttu-id="e0bda-111">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e0bda-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0bda-112">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e0bda-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e0bda-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e0bda-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e0bda-114">**.NET Framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e0bda-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0bda-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="e0bda-115">See also</span></span>

- [<span data-ttu-id="e0bda-116">“ICor调试进程6”接口</span><span class="sxs-lookup"><span data-stu-id="e0bda-116">ICorDebugProcess6 Interface</span></span>](icordebugprocess6-interface.md)
- [<span data-ttu-id="e0bda-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="e0bda-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
