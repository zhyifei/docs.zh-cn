---
title: ICorDebugEval2 接口
ms.date: 03/30/2017
api_name:
- ICorDebugEval2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2
helpviewer_keywords:
- ICorDebugEval2 interface [.NET Framework debugging]
ms.assetid: fce34531-2687-406d-9131-d6ad94f2ce0e
topic_type:
- apiref
ms.openlocfilehash: 49c1b97540644fb48509be3bb988c51c5d11fd8b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73084861"
---
# <a name="icordebugeval2-interface"></a><span data-ttu-id="54b36-102">ICorDebugEval2 接口</span><span class="sxs-lookup"><span data-stu-id="54b36-102">ICorDebugEval2 Interface</span></span>

<span data-ttu-id="54b36-103">扩展 "ICorDebugEval" 以提供对泛型类型的支持。</span><span class="sxs-lookup"><span data-stu-id="54b36-103">Extends "ICorDebugEval" to provide support for generic types.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="54b36-104">方法</span><span class="sxs-lookup"><span data-stu-id="54b36-104">Methods</span></span>  
  
|<span data-ttu-id="54b36-105">方法</span><span class="sxs-lookup"><span data-stu-id="54b36-105">Method</span></span>|<span data-ttu-id="54b36-106">描述</span><span class="sxs-lookup"><span data-stu-id="54b36-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="54b36-107">CallParameterizedFunction 方法</span><span class="sxs-lookup"><span data-stu-id="54b36-107">CallParameterizedFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-callparameterizedfunction-method.md)|<span data-ttu-id="54b36-108">设置对指定的 "ICorDebugFunction" 的调用，该调用可以嵌套在其构造函数采用类型参数的类型内，也可以采用类型参数。</span><span class="sxs-lookup"><span data-stu-id="54b36-108">Sets up a call to the specified "ICorDebugFunction", which can be nested inside a type whose constructor takes type parameters, or can itself take type parameters.</span></span>|  
|[<span data-ttu-id="54b36-109">CreateValueForType 方法</span><span class="sxs-lookup"><span data-stu-id="54b36-109">CreateValueForType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md)|<span data-ttu-id="54b36-110">获取一个指针，该指针指向指定类型的新 "ICorDebugValue"，其初始值为 null 或零。</span><span class="sxs-lookup"><span data-stu-id="54b36-110">Gets a pointer to a new "ICorDebugValue" of the specified type, with an initial value of null or zero.</span></span>|  
|[<span data-ttu-id="54b36-111">NewParameterizedArray 方法</span><span class="sxs-lookup"><span data-stu-id="54b36-111">NewParameterizedArray Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedarray-method.md)|<span data-ttu-id="54b36-112">分配指定元素类型和维度的新数组。</span><span class="sxs-lookup"><span data-stu-id="54b36-112">Allocates a new array of the specified element type and dimensions.</span></span>|  
|[<span data-ttu-id="54b36-113">NewParameterizedObject 方法</span><span class="sxs-lookup"><span data-stu-id="54b36-113">NewParameterizedObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobject-method.md)|<span data-ttu-id="54b36-114">实例化一个新的参数化类型对象，并调用该对象的构造函数方法。</span><span class="sxs-lookup"><span data-stu-id="54b36-114">Instantiates a new parameterized type object and calls the object's constructor method.</span></span>|  
|[<span data-ttu-id="54b36-115">NewParameterizedObjectNoConstructor 方法</span><span class="sxs-lookup"><span data-stu-id="54b36-115">NewParameterizedObjectNoConstructor Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobjectnoconstructor-method.md)|<span data-ttu-id="54b36-116">实例化指定类的一个新参数化类型对象，而不尝试调用构造函数方法</span><span class="sxs-lookup"><span data-stu-id="54b36-116">Instantiates a new parameterized type object of the specified class without attempting to call a constructor method</span></span>|  
|[<span data-ttu-id="54b36-117">NewStringWithLength 方法</span><span class="sxs-lookup"><span data-stu-id="54b36-117">NewStringWithLength Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newstringwithlength-method.md)|<span data-ttu-id="54b36-118">使用指定的内容创建指定长度的新字符串。</span><span class="sxs-lookup"><span data-stu-id="54b36-118">Creates a new string of the specified length with the specified contents.</span></span>|  
|[<span data-ttu-id="54b36-119">RudeAbort 方法</span><span class="sxs-lookup"><span data-stu-id="54b36-119">RudeAbort Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-rudeabort-method.md)|<span data-ttu-id="54b36-120">中止此 `ICorDebugEval2` 当前正在执行的计算。</span><span class="sxs-lookup"><span data-stu-id="54b36-120">Aborts the computation that this `ICorDebugEval2` is currently performing.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="54b36-121">备注</span><span class="sxs-lookup"><span data-stu-id="54b36-121">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="54b36-122">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="54b36-122">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="54b36-123">要求</span><span class="sxs-lookup"><span data-stu-id="54b36-123">Requirements</span></span>  
 <span data-ttu-id="54b36-124">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="54b36-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="54b36-125">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="54b36-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="54b36-126">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="54b36-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="54b36-127">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="54b36-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54b36-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="54b36-128">See also</span></span>

- [<span data-ttu-id="54b36-129">调试接口</span><span class="sxs-lookup"><span data-stu-id="54b36-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
