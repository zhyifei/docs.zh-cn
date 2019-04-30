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
ms.openlocfilehash: ea71e984be42e3b1a7b4b9fa6df878aca911c412
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61995756"
---
# <a name="icordebugfunctiongetclass-method"></a><span data-ttu-id="90bc1-102">ICorDebugFunction::GetClass 方法</span><span class="sxs-lookup"><span data-stu-id="90bc1-102">ICorDebugFunction::GetClass Method</span></span>
<span data-ttu-id="90bc1-103">获取一个 ICorDebugClass 对象，表示此函数的类。</span><span class="sxs-lookup"><span data-stu-id="90bc1-103">Gets an ICorDebugClass object that represents the class this function is a member of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90bc1-104">语法</span><span class="sxs-lookup"><span data-stu-id="90bc1-104">Syntax</span></span>  
  
```  
HRESULT GetClass (  
    [out] ICorDebugClass **ppClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="90bc1-105">参数</span><span class="sxs-lookup"><span data-stu-id="90bc1-105">Parameters</span></span>  
 `ppClass`  
 <span data-ttu-id="90bc1-106">[out]指向的地址的指针`ICorDebugClass`对象，表示的类或为 null，如果此函数不是类的成员。</span><span class="sxs-lookup"><span data-stu-id="90bc1-106">[out] A pointer to the address of the `ICorDebugClass` object that represents the class, or null, if this function is not a member of a class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90bc1-107">要求</span><span class="sxs-lookup"><span data-stu-id="90bc1-107">Requirements</span></span>  
 <span data-ttu-id="90bc1-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="90bc1-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90bc1-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="90bc1-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="90bc1-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="90bc1-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="90bc1-111">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="90bc1-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
