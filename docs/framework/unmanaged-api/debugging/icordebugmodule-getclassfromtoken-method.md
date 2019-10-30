---
title: ICorDebugModule::GetClassFromToken 方法
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetClassFromToken
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetClassFromToken
helpviewer_keywords:
- GetClassFromToken method, ICorDebugModule interface [.NET Framework debugging]
- ICorDebugModule::GetClassFromToken method [.NET Framework debugging]
ms.assetid: 622a4d3c-0425-4c54-a7e4-0735377cdad2
topic_type:
- apiref
ms.openlocfilehash: 790999093f874a4d81dd5db74ef012b1d997a12f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73109647"
---
# <a name="icordebugmodulegetclassfromtoken-method"></a><span data-ttu-id="72b0e-102">ICorDebugModule::GetClassFromToken 方法</span><span class="sxs-lookup"><span data-stu-id="72b0e-102">ICorDebugModule::GetClassFromToken Method</span></span>
<span data-ttu-id="72b0e-103">获取元数据标记指定的类。</span><span class="sxs-lookup"><span data-stu-id="72b0e-103">Gets the class specified by the metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72b0e-104">语法</span><span class="sxs-lookup"><span data-stu-id="72b0e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClassFromToken(  
    [in]  mdTypeDef        typeDef,  
    [out] ICorDebugClass **ppClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="72b0e-105">参数</span><span class="sxs-lookup"><span data-stu-id="72b0e-105">Parameters</span></span>  
 `typedef`  
 <span data-ttu-id="72b0e-106">中引用类的元数据的 `mdTypeDef` 元数据标记。</span><span class="sxs-lookup"><span data-stu-id="72b0e-106">[in] An `mdTypeDef` metadata token that references the metadata of a class.</span></span>  
  
 `ppClass`  
 <span data-ttu-id="72b0e-107">弄指向表示类的 ICorDebugClass 对象地址的指针。</span><span class="sxs-lookup"><span data-stu-id="72b0e-107">[out] A pointer to the address of an ICorDebugClass object that represents the class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72b0e-108">要求</span><span class="sxs-lookup"><span data-stu-id="72b0e-108">Requirements</span></span>  
 <span data-ttu-id="72b0e-109">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="72b0e-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72b0e-110">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="72b0e-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="72b0e-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="72b0e-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="72b0e-112">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="72b0e-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
