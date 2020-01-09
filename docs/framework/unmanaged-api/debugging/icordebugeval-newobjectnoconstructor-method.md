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
ms.openlocfilehash: 255d88dcdd880c73a7535cddcad410dcfdcf1d70
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132650"
---
# <a name="icordebugevalnewobjectnoconstructor-method"></a><span data-ttu-id="4b782-102">ICorDebugEval::NewObjectNoConstructor 方法</span><span class="sxs-lookup"><span data-stu-id="4b782-102">ICorDebugEval::NewObjectNoConstructor Method</span></span>
<span data-ttu-id="4b782-103">分配指定类型的新对象实例，而不尝试调用构造函数方法。</span><span class="sxs-lookup"><span data-stu-id="4b782-103">Allocates a new object instance of the specified type, without attempting to call a constructor method.</span></span>  
  
 <span data-ttu-id="4b782-104">此方法在 .NET Framework 版本2.0 中已过时。</span><span class="sxs-lookup"><span data-stu-id="4b782-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="4b782-105">改[为使用 ICorDebugEval2：： NewParameterizedObjectNoConstructor](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobjectnoconstructor-method.md) 。</span><span class="sxs-lookup"><span data-stu-id="4b782-105">Use [ICorDebugEval2::NewParameterizedObjectNoConstructor](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobjectnoconstructor-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b782-106">语法</span><span class="sxs-lookup"><span data-stu-id="4b782-106">Syntax</span></span>  
  
```cpp  
HRESULT NewObjectNoConstructor (  
    [in] ICorDebugClass     *pClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4b782-107">参数</span><span class="sxs-lookup"><span data-stu-id="4b782-107">Parameters</span></span>  
 `pClass`  
 <span data-ttu-id="4b782-108">中指向 ICorDebugClass 对象的指针，该对象表示要实例化的对象的类型。</span><span class="sxs-lookup"><span data-stu-id="4b782-108">[in] Pointer to an ICorDebugClass object that represents the type of object to be instantiated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b782-109">要求</span><span class="sxs-lookup"><span data-stu-id="4b782-109">Requirements</span></span>  
 <span data-ttu-id="4b782-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4b782-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4b782-111">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4b782-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4b782-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4b782-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4b782-113">**.NET Framework 版本：** 1.1、1.0</span><span class="sxs-lookup"><span data-stu-id="4b782-113">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b782-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="4b782-114">See also</span></span>

- [<span data-ttu-id="4b782-115">NewParameterizedObjectNoConstructor 方法</span><span class="sxs-lookup"><span data-stu-id="4b782-115">NewParameterizedObjectNoConstructor Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobjectnoconstructor-method.md)
