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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 413e56a65f4966467f487787172973834ac4a65a
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57496867"
---
# <a name="icordebugmodulegetclassfromtoken-method"></a><span data-ttu-id="39d36-102">ICorDebugModule::GetClassFromToken 方法</span><span class="sxs-lookup"><span data-stu-id="39d36-102">ICorDebugModule::GetClassFromToken Method</span></span>
<span data-ttu-id="39d36-103">获取指定的元数据标记的类。</span><span class="sxs-lookup"><span data-stu-id="39d36-103">Gets the class specified by the metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39d36-104">语法</span><span class="sxs-lookup"><span data-stu-id="39d36-104">Syntax</span></span>  
  
```  
HRESULT GetClassFromToken(  
    [in]  mdTypeDef        typeDef,  
    [out] ICorDebugClass **ppClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="39d36-105">参数</span><span class="sxs-lookup"><span data-stu-id="39d36-105">Parameters</span></span>  
 `typedef`  
 <span data-ttu-id="39d36-106">[in]`mdTypeDef`元数据标记所引用的类的元数据。</span><span class="sxs-lookup"><span data-stu-id="39d36-106">[in] An `mdTypeDef` metadata token that references the metadata of a class.</span></span>  
  
 `ppClass`  
 <span data-ttu-id="39d36-107">[out]指向 ICorDebugClass 对象，表示的类地址的指针。</span><span class="sxs-lookup"><span data-stu-id="39d36-107">[out] A pointer to the address of an ICorDebugClass object that represents the class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39d36-108">要求</span><span class="sxs-lookup"><span data-stu-id="39d36-108">Requirements</span></span>  
 <span data-ttu-id="39d36-109">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="39d36-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39d36-110">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="39d36-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="39d36-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="39d36-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="39d36-112">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="39d36-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
