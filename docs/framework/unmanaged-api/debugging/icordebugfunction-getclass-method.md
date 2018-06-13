---
title: ICorDebugFunction::GetClass 方法
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetClass
helpviewer_keywords:
- GetClass method, ICorDebugFunction interface [.NET Framework debugging]
- ICorDebugFunction::GetClass method [.NET Framework debugging]
ms.assetid: 27967230-144f-40d3-9e23-961d0241abd9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 184e578efb549a1dc2e9ec1e30a29ff289b68719
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33411698"
---
# <a name="icordebugfunctiongetclass-method"></a><span data-ttu-id="8d3a3-102">ICorDebugFunction::GetClass 方法</span><span class="sxs-lookup"><span data-stu-id="8d3a3-102">ICorDebugFunction::GetClass Method</span></span>
<span data-ttu-id="8d3a3-103">获取表示此函数是的成员的类的 ICorDebugClass 对象。</span><span class="sxs-lookup"><span data-stu-id="8d3a3-103">Gets an ICorDebugClass object that represents the class this function is a member of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d3a3-104">语法</span><span class="sxs-lookup"><span data-stu-id="8d3a3-104">Syntax</span></span>  
  
```  
HRESULT GetClass (  
    [out] ICorDebugClass **ppClass  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8d3a3-105">参数</span><span class="sxs-lookup"><span data-stu-id="8d3a3-105">Parameters</span></span>  
 `ppClass`  
 <span data-ttu-id="8d3a3-106">[out]指向的地址的指针`ICorDebugClass`表示的对象的类或为 null，如果此函数不是类的成员。</span><span class="sxs-lookup"><span data-stu-id="8d3a3-106">[out] A pointer to the address of the `ICorDebugClass` object that represents the class, or null, if this function is not a member of a class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d3a3-107">要求</span><span class="sxs-lookup"><span data-stu-id="8d3a3-107">Requirements</span></span>  
 <span data-ttu-id="8d3a3-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8d3a3-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d3a3-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8d3a3-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8d3a3-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8d3a3-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8d3a3-111">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d3a3-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
