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
ms.openlocfilehash: d41216eb7da57d29d67ce17372f746328204649e
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976169"
---
# <a name="icordebugevalnewobjectnoconstructor-method"></a><span data-ttu-id="faa46-102">ICorDebugEval::NewObjectNoConstructor 方法</span><span class="sxs-lookup"><span data-stu-id="faa46-102">ICorDebugEval::NewObjectNoConstructor Method</span></span>
<span data-ttu-id="faa46-103">分配指定类型的新对象实例，而不尝试调用构造函数方法。</span><span class="sxs-lookup"><span data-stu-id="faa46-103">Allocates a new object instance of the specified type, without attempting to call a constructor method.</span></span>  
  
 <span data-ttu-id="faa46-104">此方法在 .NET Framework 版本2.0 中已过时。</span><span class="sxs-lookup"><span data-stu-id="faa46-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="faa46-105">改[为使用 ICorDebugEval2：： NewParameterizedObjectNoConstructor](icordebugeval2-newparameterizedobjectnoconstructor-method.md) 。</span><span class="sxs-lookup"><span data-stu-id="faa46-105">Use [ICorDebugEval2::NewParameterizedObjectNoConstructor](icordebugeval2-newparameterizedobjectnoconstructor-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="faa46-106">语法</span><span class="sxs-lookup"><span data-stu-id="faa46-106">Syntax</span></span>  
  
```cpp  
HRESULT NewObjectNoConstructor (  
    [in] ICorDebugClass     *pClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="faa46-107">参数</span><span class="sxs-lookup"><span data-stu-id="faa46-107">Parameters</span></span>  
 `pClass`  
 <span data-ttu-id="faa46-108">中指向 ICorDebugClass 对象的指针，该对象表示要实例化的对象的类型。</span><span class="sxs-lookup"><span data-stu-id="faa46-108">[in] Pointer to an ICorDebugClass object that represents the type of object to be instantiated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="faa46-109">要求</span><span class="sxs-lookup"><span data-stu-id="faa46-109">Requirements</span></span>  
 <span data-ttu-id="faa46-110">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="faa46-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="faa46-111">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="faa46-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="faa46-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="faa46-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="faa46-113">**.NET Framework 版本：** 1.1、1。0</span><span class="sxs-lookup"><span data-stu-id="faa46-113">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="faa46-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="faa46-114">See also</span></span>

- [<span data-ttu-id="faa46-115">NewParameterizedObjectNoConstructor 方法</span><span class="sxs-lookup"><span data-stu-id="faa46-115">NewParameterizedObjectNoConstructor Method</span></span>](icordebugeval2-newparameterizedobjectnoconstructor-method.md)
