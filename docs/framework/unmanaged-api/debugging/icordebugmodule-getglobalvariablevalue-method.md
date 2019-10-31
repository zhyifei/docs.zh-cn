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
ms.openlocfilehash: 3afefdc3d704044184ea20d061eb9449458b5060
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129568"
---
# <a name="icordebugmodulegetglobalvariablevalue-method"></a><span data-ttu-id="41b60-102">ICorDebugModule::GetGlobalVariableValue 方法</span><span class="sxs-lookup"><span data-stu-id="41b60-102">ICorDebugModule::GetGlobalVariableValue Method</span></span>
<span data-ttu-id="41b60-103">获取指定全局变量的值。</span><span class="sxs-lookup"><span data-stu-id="41b60-103">Gets the value of the specified global variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41b60-104">语法</span><span class="sxs-lookup"><span data-stu-id="41b60-104">Syntax</span></span>  
  
```cpp  
HRESULT GetGlobalVariableValue(  
    [in]  mdFieldDef      fieldDef,  
    [out] ICorDebugValue  **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="41b60-105">参数</span><span class="sxs-lookup"><span data-stu-id="41b60-105">Parameters</span></span>  
 `fieldDef`  
 <span data-ttu-id="41b60-106">中一个 `mdFieldDef` 标记，该标记引用描述全局变量的元数据。</span><span class="sxs-lookup"><span data-stu-id="41b60-106">[in] An `mdFieldDef` token that references the metadata describing the global variable.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="41b60-107">弄指向 ICorDebugValue 对象的地址的指针，该对象表示指定的全局变量的值。</span><span class="sxs-lookup"><span data-stu-id="41b60-107">[out] A pointer to the address of an ICorDebugValue object that represents the value of the specified global variable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41b60-108">要求</span><span class="sxs-lookup"><span data-stu-id="41b60-108">Requirements</span></span>  
 <span data-ttu-id="41b60-109">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="41b60-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41b60-110">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="41b60-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="41b60-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="41b60-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="41b60-112">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="41b60-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
