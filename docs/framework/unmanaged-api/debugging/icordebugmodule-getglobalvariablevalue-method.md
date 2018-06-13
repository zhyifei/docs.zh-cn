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
ms.openlocfilehash: aa558bf58f3033cc39a2b52d99e3a5329d9e99bd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33413028"
---
# <a name="icordebugmodulegetglobalvariablevalue-method"></a><span data-ttu-id="1e388-102">ICorDebugModule::GetGlobalVariableValue 方法</span><span class="sxs-lookup"><span data-stu-id="1e388-102">ICorDebugModule::GetGlobalVariableValue Method</span></span>
<span data-ttu-id="1e388-103">获取指定的全局变量的值。</span><span class="sxs-lookup"><span data-stu-id="1e388-103">Gets the value of the specified global variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e388-104">语法</span><span class="sxs-lookup"><span data-stu-id="1e388-104">Syntax</span></span>  
  
```  
HRESULT GetGlobalVariableValue(  
    [in]  mdFieldDef      fieldDef,  
    [out] ICorDebugValue  **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1e388-105">参数</span><span class="sxs-lookup"><span data-stu-id="1e388-105">Parameters</span></span>  
 `fieldDef`  
 <span data-ttu-id="1e388-106">[in]`mdFieldDef`引用描述全局变量的元数据的令牌。</span><span class="sxs-lookup"><span data-stu-id="1e388-106">[in] An `mdFieldDef` token that references the metadata describing the global variable.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="1e388-107">[out]指向一个 ICorDebugValue 对象，表示指定的全局变量的值的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="1e388-107">[out] A pointer to the address of an ICorDebugValue object that represents the value of the specified global variable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1e388-108">要求</span><span class="sxs-lookup"><span data-stu-id="1e388-108">Requirements</span></span>  
 <span data-ttu-id="1e388-109">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1e388-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1e388-110">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1e388-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1e388-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1e388-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1e388-112">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1e388-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
