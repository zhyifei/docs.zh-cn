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
ms.openlocfilehash: fdfa38a4cdbbaad2fc2c987a10a122af4a1fc9a9
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791037"
---
# <a name="icordebugvariablehomegetcode-method"></a><span data-ttu-id="ea4fb-102">ICorDebugVariableHome：： GetCode 方法</span><span class="sxs-lookup"><span data-stu-id="ea4fb-102">ICorDebugVariableHome::GetCode Method</span></span>
<span data-ttu-id="ea4fb-103">获取包含此[ICorDebugVariableHome](icordebugvariablehome-interface.md)对象的 "ICorDebugCode" 实例。</span><span class="sxs-lookup"><span data-stu-id="ea4fb-103">Gets the "ICorDebugCode" instance that contains this [ICorDebugVariableHome](icordebugvariablehome-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea4fb-104">语法</span><span class="sxs-lookup"><span data-stu-id="ea4fb-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCode(  
    [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ea4fb-105">参数</span><span class="sxs-lookup"><span data-stu-id="ea4fb-105">Parameters</span></span>  
 `ppCode`  
 <span data-ttu-id="ea4fb-106">弄一个指针，指向包含此[ICorDebugVariableHome](icordebugvariablehome-interface.md)对象的 "ICorDebugCode" 实例的地址。</span><span class="sxs-lookup"><span data-stu-id="ea4fb-106">[out] A pointer to the address of the "ICorDebugCode" instance that contains this [ICorDebugVariableHome](icordebugvariablehome-interface.md) object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ea4fb-107">需求</span><span class="sxs-lookup"><span data-stu-id="ea4fb-107">Requirements</span></span>  
 <span data-ttu-id="ea4fb-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ea4fb-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea4fb-109">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ea4fb-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ea4fb-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ea4fb-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ea4fb-111">**.NET Framework 版本：** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea4fb-111">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea4fb-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ea4fb-112">See also</span></span>

- [<span data-ttu-id="ea4fb-113">ICorDebugVariableHome 接口</span><span class="sxs-lookup"><span data-stu-id="ea4fb-113">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
