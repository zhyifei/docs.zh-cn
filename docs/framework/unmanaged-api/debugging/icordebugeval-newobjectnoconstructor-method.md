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
ms.openlocfilehash: 45efa1939813a319e996a72fef62ada167b877c2
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788697"
---
# <a name="icordebugevalnewobjectnoconstructor-method"></a><span data-ttu-id="3009a-102">ICorDebugEval::NewObjectNoConstructor 方法</span><span class="sxs-lookup"><span data-stu-id="3009a-102">ICorDebugEval::NewObjectNoConstructor Method</span></span>
<span data-ttu-id="3009a-103">分配指定类型的新对象实例，而不尝试调用构造函数方法。</span><span class="sxs-lookup"><span data-stu-id="3009a-103">Allocates a new object instance of the specified type, without attempting to call a constructor method.</span></span>  
  
 <span data-ttu-id="3009a-104">此方法在 .NET Framework 版本2.0 中已过时。</span><span class="sxs-lookup"><span data-stu-id="3009a-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="3009a-105">改[为使用 ICorDebugEval2：： NewParameterizedObjectNoConstructor](icordebugeval2-newparameterizedobjectnoconstructor-method.md) 。</span><span class="sxs-lookup"><span data-stu-id="3009a-105">Use [ICorDebugEval2::NewParameterizedObjectNoConstructor](icordebugeval2-newparameterizedobjectnoconstructor-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3009a-106">语法</span><span class="sxs-lookup"><span data-stu-id="3009a-106">Syntax</span></span>  
  
```cpp  
HRESULT NewObjectNoConstructor (  
    [in] ICorDebugClass     *pClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3009a-107">参数</span><span class="sxs-lookup"><span data-stu-id="3009a-107">Parameters</span></span>  
 `pClass`  
 <span data-ttu-id="3009a-108">中指向 ICorDebugClass 对象的指针，该对象表示要实例化的对象的类型。</span><span class="sxs-lookup"><span data-stu-id="3009a-108">[in] Pointer to an ICorDebugClass object that represents the type of object to be instantiated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3009a-109">需求</span><span class="sxs-lookup"><span data-stu-id="3009a-109">Requirements</span></span>  
 <span data-ttu-id="3009a-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3009a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3009a-111">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3009a-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3009a-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3009a-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3009a-113">**.NET Framework 版本：** 1.1、1.0</span><span class="sxs-lookup"><span data-stu-id="3009a-113">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3009a-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3009a-114">See also</span></span>

- [<span data-ttu-id="3009a-115">NewParameterizedObjectNoConstructor 方法</span><span class="sxs-lookup"><span data-stu-id="3009a-115">NewParameterizedObjectNoConstructor Method</span></span>](icordebugeval2-newparameterizedobjectnoconstructor-method.md)
