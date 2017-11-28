---
title: "ICorDebugEval2::NewParameterizedObject 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugEval2.NewParameterizedObject
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugEval2::NewParameterizedObject
helpviewer_keywords:
- NewParameterizedObject method [.NET Framework debugging]
- ICorDebugEval2::NewParameterizedObject method [.NET Framework debugging]
ms.assetid: 3d705463-e640-4249-8036-4e8206d03cfe
topic_type: apiref
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 29b2470f50e96307ad91428fe1c712e7340baa32
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugeval2newparameterizedobject-method"></a><span data-ttu-id="91839-102">ICorDebugEval2::NewParameterizedObject 方法</span><span class="sxs-lookup"><span data-stu-id="91839-102">ICorDebugEval2::NewParameterizedObject Method</span></span>
<span data-ttu-id="91839-103">实例化一个新的参数化的类型对象并调用对象的构造函数方法。</span><span class="sxs-lookup"><span data-stu-id="91839-103">Instantiates a new parameterized type object and calls the object's constructor method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91839-104">语法</span><span class="sxs-lookup"><span data-stu-id="91839-104">Syntax</span></span>  
  
```  
HRESULT NewParameterizedObject (  
    [in] ICorDebugFunction     *pConstructor,  
    [in] ULONG32               nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType *ppTypeArgs[],  
    [in] ULONG32               nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="91839-105">参数</span><span class="sxs-lookup"><span data-stu-id="91839-105">Parameters</span></span>  
 `pConstructor`  
 <span data-ttu-id="91839-106">[in]指向一个 ICorDebugFunction 对象，表示要进行实例化的对象的构造函数的指针。</span><span class="sxs-lookup"><span data-stu-id="91839-106">[in] A pointer to an ICorDebugFunction object that represents the constructor of the object to be instantiated.</span></span>  
  
 `nTypeArgs`  
 <span data-ttu-id="91839-107">[in]传递的类型自变量数目。</span><span class="sxs-lookup"><span data-stu-id="91839-107">[in] The number of type arguments passed.</span></span>  
  
 `ppTypeArgs`  
 <span data-ttu-id="91839-108">[in]一个指针数组，其中每个指向对象的表示进行实例化的对象的类型自变量。</span><span class="sxs-lookup"><span data-stu-id="91839-108">[in] An array of pointers, each of which points to an ICorDebugType object that represents a type argument for the object that is being instantiated.</span></span>  
  
 `nArgs`  
 <span data-ttu-id="91839-109">[in]传递给构造函数的参数数目。</span><span class="sxs-lookup"><span data-stu-id="91839-109">[in] The number of arguments passed to the constructor.</span></span>  
  
 `ppArgs`  
 <span data-ttu-id="91839-110">[in]一个指针数组，其中每个指向 ICorDebugValue 对象，表示传递给构造函数自变量值。</span><span class="sxs-lookup"><span data-stu-id="91839-110">[in] An array of pointers, each of which points to an ICorDebugValue object that represents an argument value that is passed to the constructor.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="91839-111">备注</span><span class="sxs-lookup"><span data-stu-id="91839-111">Remarks</span></span>  
 <span data-ttu-id="91839-112">对象的构造函数可能需要<xref:System.Type>参数。</span><span class="sxs-lookup"><span data-stu-id="91839-112">The object's constructor may take <xref:System.Type> parameters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="91839-113">要求</span><span class="sxs-lookup"><span data-stu-id="91839-113">Requirements</span></span>  
 <span data-ttu-id="91839-114">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="91839-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="91839-115">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="91839-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="91839-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="91839-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="91839-117">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="91839-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
