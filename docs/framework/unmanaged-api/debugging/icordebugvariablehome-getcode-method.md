---
title: ICorDebugVariableHome：： GetCode 方法
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetCode
helpviewer_keywords:
- ICorDebugVariableHome::GetCode method [.NET Framework debugging]
- GetCode method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: ef002890-4a7b-4a5d-abbf-16c60083f794
topic_type:
- apiref
ms.openlocfilehash: 4770eb3e93104dd3862eb2163faf1dc7fe9008ba
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125139"
---
# <a name="icordebugvariablehomegetcode-method"></a><span data-ttu-id="1de44-102">ICorDebugVariableHome：： GetCode 方法</span><span class="sxs-lookup"><span data-stu-id="1de44-102">ICorDebugVariableHome::GetCode Method</span></span>
<span data-ttu-id="1de44-103">获取包含此[ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)对象的 "ICorDebugCode" 实例。</span><span class="sxs-lookup"><span data-stu-id="1de44-103">Gets the "ICorDebugCode" instance that contains this [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1de44-104">语法</span><span class="sxs-lookup"><span data-stu-id="1de44-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCode(  
    [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1de44-105">参数</span><span class="sxs-lookup"><span data-stu-id="1de44-105">Parameters</span></span>  
 `ppCode`  
 <span data-ttu-id="1de44-106">弄一个指针，指向包含此[ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)对象的 "ICorDebugCode" 实例的地址。</span><span class="sxs-lookup"><span data-stu-id="1de44-106">[out] A pointer to the address of the "ICorDebugCode" instance that contains this [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1de44-107">要求</span><span class="sxs-lookup"><span data-stu-id="1de44-107">Requirements</span></span>  
 <span data-ttu-id="1de44-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1de44-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1de44-109">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1de44-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1de44-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1de44-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1de44-111">**.NET Framework 版本：** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1de44-111">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1de44-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="1de44-112">See also</span></span>

- [<span data-ttu-id="1de44-113">ICorDebugVariableHome 接口</span><span class="sxs-lookup"><span data-stu-id="1de44-113">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
