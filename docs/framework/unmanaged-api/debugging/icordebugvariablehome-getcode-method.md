---
title: ICorDebugVariableHome::GetCode 方法
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6a4cadae7a43d0cd965e51535eae2c95e59900d0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59130008"
---
# <a name="icordebugvariablehomegetcode-method"></a><span data-ttu-id="f9354-102">ICorDebugVariableHome::GetCode 方法</span><span class="sxs-lookup"><span data-stu-id="f9354-102">ICorDebugVariableHome::GetCode Method</span></span>
<span data-ttu-id="f9354-103">获取包含此"ICorDebugCode"实例[ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)对象。</span><span class="sxs-lookup"><span data-stu-id="f9354-103">Gets the "ICorDebugCode" instance that contains this [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9354-104">语法</span><span class="sxs-lookup"><span data-stu-id="f9354-104">Syntax</span></span>  
  
```  
HRESULT GetCode(  
    [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f9354-105">参数</span><span class="sxs-lookup"><span data-stu-id="f9354-105">Parameters</span></span>  
 `ppCode`  
 <span data-ttu-id="f9354-106">[out]指向包含此"ICorDebugCode"实例的地址的指针[ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)对象。</span><span class="sxs-lookup"><span data-stu-id="f9354-106">[out] A pointer to the address of the "ICorDebugCode" instance that contains this [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f9354-107">要求</span><span class="sxs-lookup"><span data-stu-id="f9354-107">Requirements</span></span>  
 <span data-ttu-id="f9354-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f9354-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f9354-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f9354-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f9354-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f9354-110">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="f9354-111">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="f9354-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f9354-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="f9354-112">See also</span></span>

- [<span data-ttu-id="f9354-113">ICorDebugVariableHome 接口</span><span class="sxs-lookup"><span data-stu-id="f9354-113">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
