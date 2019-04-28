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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61988073"
---
# <a name="icordebugmodulegetclassfromtoken-method"></a><span data-ttu-id="5cfd2-102">ICorDebugModule::GetClassFromToken 方法</span><span class="sxs-lookup"><span data-stu-id="5cfd2-102">ICorDebugModule::GetClassFromToken Method</span></span>
<span data-ttu-id="5cfd2-103">获取指定的元数据标记的类。</span><span class="sxs-lookup"><span data-stu-id="5cfd2-103">Gets the class specified by the metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5cfd2-104">语法</span><span class="sxs-lookup"><span data-stu-id="5cfd2-104">Syntax</span></span>  
  
```  
HRESULT GetClassFromToken(  
    [in]  mdTypeDef        typeDef,  
    [out] ICorDebugClass **ppClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5cfd2-105">参数</span><span class="sxs-lookup"><span data-stu-id="5cfd2-105">Parameters</span></span>  
 `typedef`  
 <span data-ttu-id="5cfd2-106">[in]`mdTypeDef`元数据标记所引用的类的元数据。</span><span class="sxs-lookup"><span data-stu-id="5cfd2-106">[in] An `mdTypeDef` metadata token that references the metadata of a class.</span></span>  
  
 `ppClass`  
 <span data-ttu-id="5cfd2-107">[out]指向 ICorDebugClass 对象，表示的类地址的指针。</span><span class="sxs-lookup"><span data-stu-id="5cfd2-107">[out] A pointer to the address of an ICorDebugClass object that represents the class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5cfd2-108">要求</span><span class="sxs-lookup"><span data-stu-id="5cfd2-108">Requirements</span></span>  
 <span data-ttu-id="5cfd2-109">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5cfd2-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5cfd2-110">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5cfd2-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5cfd2-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5cfd2-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5cfd2-112">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5cfd2-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
