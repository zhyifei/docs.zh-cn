---
title: ICorDebugModule::GetGlobalVariableValue 方法
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetGlobalVariableValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetGlobalVariableValue
helpviewer_keywords:
- ICorDebugModule::GetGlobalVariableValue method [.NET Framework debugging]
- GetGlobalVariableValue method [.NET Framework debugging]
ms.assetid: bbc0881c-6a59-41a0-b5ee-2f3d1b71684c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 00e747e43f67533771665313f4d420e4725945cd
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57485342"
---
# <a name="icordebugmodulegetglobalvariablevalue-method"></a><span data-ttu-id="d0b72-102">ICorDebugModule::GetGlobalVariableValue 方法</span><span class="sxs-lookup"><span data-stu-id="d0b72-102">ICorDebugModule::GetGlobalVariableValue Method</span></span>
<span data-ttu-id="d0b72-103">获取指定的全局变量的值。</span><span class="sxs-lookup"><span data-stu-id="d0b72-103">Gets the value of the specified global variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0b72-104">语法</span><span class="sxs-lookup"><span data-stu-id="d0b72-104">Syntax</span></span>  
  
```  
HRESULT GetGlobalVariableValue(  
    [in]  mdFieldDef      fieldDef,  
    [out] ICorDebugValue  **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d0b72-105">参数</span><span class="sxs-lookup"><span data-stu-id="d0b72-105">Parameters</span></span>  
 `fieldDef`  
 <span data-ttu-id="d0b72-106">[in]`mdFieldDef`引用描述全局变量的元数据的令牌。</span><span class="sxs-lookup"><span data-stu-id="d0b72-106">[in] An `mdFieldDef` token that references the metadata describing the global variable.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="d0b72-107">[out]指向一个 ICorDebugValue 对象，表示指定的全局变量的值的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="d0b72-107">[out] A pointer to the address of an ICorDebugValue object that represents the value of the specified global variable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d0b72-108">要求</span><span class="sxs-lookup"><span data-stu-id="d0b72-108">Requirements</span></span>  
 <span data-ttu-id="d0b72-109">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d0b72-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d0b72-110">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d0b72-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d0b72-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d0b72-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d0b72-112">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d0b72-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
