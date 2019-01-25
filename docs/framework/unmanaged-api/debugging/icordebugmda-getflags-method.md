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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d127cecedb128ea5253b079d484fe8e084a81bae
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54637341"
---
# <a name="icordebugmdagetflags-method"></a><span data-ttu-id="1c2c4-102">ICorDebugMDA::GetFlags 方法</span><span class="sxs-lookup"><span data-stu-id="1c2c4-102">ICorDebugMDA::GetFlags Method</span></span>
<span data-ttu-id="1c2c4-103">获取与由表示托管调试助手 (MDA) 相关联的标志[ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)。</span><span class="sxs-lookup"><span data-stu-id="1c2c4-103">Gets the flags associated with the managed debugging assistant (MDA) represented by [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c2c4-104">语法</span><span class="sxs-lookup"><span data-stu-id="1c2c4-104">Syntax</span></span>  
  
```  
HRESULT GetFlags (  
    [in] CorDebugMDAFlags *pFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1c2c4-105">参数</span><span class="sxs-lookup"><span data-stu-id="1c2c4-105">Parameters</span></span>  
 `pFlags`  
 <span data-ttu-id="1c2c4-106">[in]按位组合[CorDebugMDAFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugmdaflags-enumeration.md)用于指定此 MDA 的设置的标志的枚举值。</span><span class="sxs-lookup"><span data-stu-id="1c2c4-106">[in] A bitwise combination of the [CorDebugMDAFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugmdaflags-enumeration.md) enumeration values that specify the settings of the flags for this MDA.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c2c4-107">要求</span><span class="sxs-lookup"><span data-stu-id="1c2c4-107">Requirements</span></span>  
 <span data-ttu-id="1c2c4-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1c2c4-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c2c4-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1c2c4-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1c2c4-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1c2c4-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1c2c4-111">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c2c4-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c2c4-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="1c2c4-112">See also</span></span>
- [<span data-ttu-id="1c2c4-113">ICorDebugMDA 接口</span><span class="sxs-lookup"><span data-stu-id="1c2c4-113">ICorDebugMDA Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)
- [<span data-ttu-id="1c2c4-114">使用托管调试助手诊断错误</span><span class="sxs-lookup"><span data-stu-id="1c2c4-114">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
