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
ms.openlocfilehash: 195cea23313d88b636479147faa512889ca94b17
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33413967"
---
# <a name="icordebugmodulegetclassfromtoken-method"></a><span data-ttu-id="140d1-102">ICorDebugModule::GetClassFromToken 方法</span><span class="sxs-lookup"><span data-stu-id="140d1-102">ICorDebugModule::GetClassFromToken Method</span></span>
<span data-ttu-id="140d1-103">获取指定的元数据标记的类。</span><span class="sxs-lookup"><span data-stu-id="140d1-103">Gets the class specified by the metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="140d1-104">语法</span><span class="sxs-lookup"><span data-stu-id="140d1-104">Syntax</span></span>  
  
```  
HRESULT GetClassFromToken(  
    [in]  mdTypeDef        typeDef,  
    [out] ICorDebugClass **ppClass  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="140d1-105">参数</span><span class="sxs-lookup"><span data-stu-id="140d1-105">Parameters</span></span>  
 `typedef`  
 <span data-ttu-id="140d1-106">[in]`mdTypeDef`引用类的元数据的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="140d1-106">[in] An `mdTypeDef` metadata token that references the metadata of a class.</span></span>  
  
 `ppClass`  
 <span data-ttu-id="140d1-107">[out]指向 ICorDebugClass 对象表示类地址的指针。</span><span class="sxs-lookup"><span data-stu-id="140d1-107">[out] A pointer to the address of an ICorDebugClass object that represents the class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="140d1-108">要求</span><span class="sxs-lookup"><span data-stu-id="140d1-108">Requirements</span></span>  
 <span data-ttu-id="140d1-109">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="140d1-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="140d1-110">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="140d1-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="140d1-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="140d1-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="140d1-112">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="140d1-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
