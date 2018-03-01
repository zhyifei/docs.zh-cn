---
title: "ICorDebugEval::NewObjectNoConstructor 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugEval.NewObjectNoConstructor
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::NewObjectNoConstructor
helpviewer_keywords:
- NewObjectNoConstructor method [.NET Framework debugging]
- ICorDebugEval::NewObjectNoConstructor method [.NET Framework debugging]
ms.assetid: 80d509ca-b5e3-4c46-9c14-800db73d9bf7
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ceb35781d4685e3576470da3b99a6666ba233e19
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugevalnewobjectnoconstructor-method"></a><span data-ttu-id="b9374-102">ICorDebugEval::NewObjectNoConstructor 方法</span><span class="sxs-lookup"><span data-stu-id="b9374-102">ICorDebugEval::NewObjectNoConstructor Method</span></span>
<span data-ttu-id="b9374-103">分配新的对象实例的指定类型，而不尝试调用构造函数方法。</span><span class="sxs-lookup"><span data-stu-id="b9374-103">Allocates a new object instance of the specified type, without attempting to call a constructor method.</span></span>  
  
 <span data-ttu-id="b9374-104">此方法是.NET Framework 2.0 版中过时。</span><span class="sxs-lookup"><span data-stu-id="b9374-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="b9374-105">使用[icordebugeval2:: Newparameterizedobjectnoconstructor](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobjectnoconstructor-method.md)相反。</span><span class="sxs-lookup"><span data-stu-id="b9374-105">Use [ICorDebugEval2::NewParameterizedObjectNoConstructor](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobjectnoconstructor-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9374-106">语法</span><span class="sxs-lookup"><span data-stu-id="b9374-106">Syntax</span></span>  
  
```  
HRESULT NewObjectNoConstructor (  
    [in] ICorDebugClass     *pClass  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b9374-107">参数</span><span class="sxs-lookup"><span data-stu-id="b9374-107">Parameters</span></span>  
 `pClass`  
 <span data-ttu-id="b9374-108">[in]指向一个 ICorDebugClass 对象，表示要进行实例化的对象类型的指针。</span><span class="sxs-lookup"><span data-stu-id="b9374-108">[in] Pointer to an ICorDebugClass object that represents the type of object to be instantiated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9374-109">惠?</span><span class="sxs-lookup"><span data-stu-id="b9374-109">Requirements</span></span>  
 <span data-ttu-id="b9374-110">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b9374-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9374-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b9374-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b9374-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b9374-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b9374-113">**.NET framework 版本：** 1.1、 1.0</span><span class="sxs-lookup"><span data-stu-id="b9374-113">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9374-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="b9374-114">See Also</span></span>  
 [<span data-ttu-id="b9374-115">NewParameterizedObjectNoConstructor 方法</span><span class="sxs-lookup"><span data-stu-id="b9374-115">NewParameterizedObjectNoConstructor Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobjectnoconstructor-method.md)
