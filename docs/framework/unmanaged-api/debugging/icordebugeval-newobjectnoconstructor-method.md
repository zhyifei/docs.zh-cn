---
title: ICorDebugEval::NewObjectNoConstructor 方法
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6846b866fd47674ca6b5fd187b580fd28e080fd0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61995925"
---
# <a name="icordebugevalnewobjectnoconstructor-method"></a><span data-ttu-id="7cfb5-102">ICorDebugEval::NewObjectNoConstructor 方法</span><span class="sxs-lookup"><span data-stu-id="7cfb5-102">ICorDebugEval::NewObjectNoConstructor Method</span></span>
<span data-ttu-id="7cfb5-103">分配新的对象实例的指定类型，而不尝试调用构造函数方法。</span><span class="sxs-lookup"><span data-stu-id="7cfb5-103">Allocates a new object instance of the specified type, without attempting to call a constructor method.</span></span>  
  
 <span data-ttu-id="7cfb5-104">此方法是在.NET Framework 2.0 版中已过时。</span><span class="sxs-lookup"><span data-stu-id="7cfb5-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="7cfb5-105">使用[ICorDebugEval2::NewParameterizedObjectNoConstructor](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobjectnoconstructor-method.md)相反。</span><span class="sxs-lookup"><span data-stu-id="7cfb5-105">Use [ICorDebugEval2::NewParameterizedObjectNoConstructor](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobjectnoconstructor-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7cfb5-106">语法</span><span class="sxs-lookup"><span data-stu-id="7cfb5-106">Syntax</span></span>  
  
```  
HRESULT NewObjectNoConstructor (  
    [in] ICorDebugClass     *pClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7cfb5-107">参数</span><span class="sxs-lookup"><span data-stu-id="7cfb5-107">Parameters</span></span>  
 `pClass`  
 <span data-ttu-id="7cfb5-108">[in]ICorDebugClass 对象，表示要进行实例化的对象类型的指针。</span><span class="sxs-lookup"><span data-stu-id="7cfb5-108">[in] Pointer to an ICorDebugClass object that represents the type of object to be instantiated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7cfb5-109">要求</span><span class="sxs-lookup"><span data-stu-id="7cfb5-109">Requirements</span></span>  
 <span data-ttu-id="7cfb5-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7cfb5-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7cfb5-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7cfb5-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7cfb5-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7cfb5-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7cfb5-113">**.NET framework 版本：** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="7cfb5-113">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7cfb5-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="7cfb5-114">See also</span></span>

- [<span data-ttu-id="7cfb5-115">NewParameterizedObjectNoConstructor 方法</span><span class="sxs-lookup"><span data-stu-id="7cfb5-115">NewParameterizedObjectNoConstructor Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobjectnoconstructor-method.md)
