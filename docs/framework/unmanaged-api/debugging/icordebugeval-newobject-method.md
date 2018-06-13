---
title: ICorDebugEval::NewObject 方法
ms.date: 03/30/2017
api_name:
- ICorDebugEval.NewObject
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::NewObject
helpviewer_keywords:
- NewObject method [.NET Framework debugging]
- ICorDebugEval::NewObject method [.NET Framework debugging]
ms.assetid: ce3025e8-defa-4c5e-8298-f49d71fa5736
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5ff378602fc7338263ef49aee6802d2138bab9d2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33413167"
---
# <a name="icordebugevalnewobject-method"></a><span data-ttu-id="65a3a-102">ICorDebugEval::NewObject 方法</span><span class="sxs-lookup"><span data-stu-id="65a3a-102">ICorDebugEval::NewObject Method</span></span>
<span data-ttu-id="65a3a-103">分配新的对象实例并调用的指定构造函数方法。</span><span class="sxs-lookup"><span data-stu-id="65a3a-103">Allocates a new object instance and calls the specified constructor method.</span></span>  
  
 <span data-ttu-id="65a3a-104">此方法是.NET Framework 2.0 版中过时。</span><span class="sxs-lookup"><span data-stu-id="65a3a-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="65a3a-105">使用[icordebugeval2:: Newparameterizedobject](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobject-method.md)相反。</span><span class="sxs-lookup"><span data-stu-id="65a3a-105">Use [ICorDebugEval2::NewParameterizedObject](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobject-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65a3a-106">语法</span><span class="sxs-lookup"><span data-stu-id="65a3a-106">Syntax</span></span>  
  
```  
HRESULT NewObject (  
    [in] ICorDebugFunction  *pConstructor,  
    [in] ULONG32            nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="65a3a-107">参数</span><span class="sxs-lookup"><span data-stu-id="65a3a-107">Parameters</span></span>  
 `pConstructor`  
 <span data-ttu-id="65a3a-108">[in]要调用构造函数。</span><span class="sxs-lookup"><span data-stu-id="65a3a-108">[in] The constructor to be called.</span></span>  
  
 `nArgs`  
 <span data-ttu-id="65a3a-109">[in] `ppArgs` 数组的大小。</span><span class="sxs-lookup"><span data-stu-id="65a3a-109">[in] The size of the `ppArgs` array.</span></span>  
  
 `ppArgs`  
 <span data-ttu-id="65a3a-110">[in]ICorDebugValue 对象数组，其中每个表示一个自变量传递给构造函数。</span><span class="sxs-lookup"><span data-stu-id="65a3a-110">[in] An array of ICorDebugValue objects, each of which represents an argument to be passed to the constructor.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="65a3a-111">要求</span><span class="sxs-lookup"><span data-stu-id="65a3a-111">Requirements</span></span>  
 <span data-ttu-id="65a3a-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="65a3a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="65a3a-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="65a3a-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="65a3a-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="65a3a-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="65a3a-115">**.NET framework 版本：** 1.1、 1.0</span><span class="sxs-lookup"><span data-stu-id="65a3a-115">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65a3a-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="65a3a-116">See Also</span></span>  
 [<span data-ttu-id="65a3a-117">NewParameterizedObject 方法</span><span class="sxs-lookup"><span data-stu-id="65a3a-117">NewParameterizedObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobject-method.md)
