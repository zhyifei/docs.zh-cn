---
title: "ICorDebugEval2 接口 1"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugEval2
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugEval2
helpviewer_keywords: ICorDebugEval2 interface [.NET Framework debugging]
ms.assetid: fce34531-2687-406d-9131-d6ad94f2ce0e
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: fbcf36ff7aca84299c55083b4ae135ce0a9ec4f3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugeval2-interface1"></a><span data-ttu-id="ec361-102">ICorDebugEval2 接口 1</span><span class="sxs-lookup"><span data-stu-id="ec361-102">ICorDebugEval2 Interface1</span></span>
<span data-ttu-id="ec361-103">扩展"ICorDebugEval"以对泛型类型提供支持。</span><span class="sxs-lookup"><span data-stu-id="ec361-103">Extends "ICorDebugEval" to provide support for generic types.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ec361-104">方法</span><span class="sxs-lookup"><span data-stu-id="ec361-104">Methods</span></span>  
  
|<span data-ttu-id="ec361-105">方法</span><span class="sxs-lookup"><span data-stu-id="ec361-105">Method</span></span>|<span data-ttu-id="ec361-106">描述</span><span class="sxs-lookup"><span data-stu-id="ec361-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ec361-107">CallParameterizedFunction 方法</span><span class="sxs-lookup"><span data-stu-id="ec361-107">CallParameterizedFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-callparameterizedfunction-method.md)|<span data-ttu-id="ec361-108">设置指定"ICorDebugFunction"，这可以嵌套在其构造函数采用类型参数或本身可以采用类型参数的类型调用。</span><span class="sxs-lookup"><span data-stu-id="ec361-108">Sets up a call to the specified "ICorDebugFunction", which can be nested inside a type whose constructor takes type parameters, or can itself take type parameters.</span></span>|  
|[<span data-ttu-id="ec361-109">CreateValueForType 方法</span><span class="sxs-lookup"><span data-stu-id="ec361-109">CreateValueForType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md)|<span data-ttu-id="ec361-110">获取一个指向新的"ICorDebugValue"的指定类型，使用的初始值为 null 或零。</span><span class="sxs-lookup"><span data-stu-id="ec361-110">Gets a pointer to a new "ICorDebugValue" of the specified type, with an initial value of null or zero.</span></span>|  
|[<span data-ttu-id="ec361-111">NewParameterizedArray 方法</span><span class="sxs-lookup"><span data-stu-id="ec361-111">NewParameterizedArray Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedarray-method.md)|<span data-ttu-id="ec361-112">分配的指定的元素类型和维度的一个新数组。</span><span class="sxs-lookup"><span data-stu-id="ec361-112">Allocates a new array of the specified element type and dimensions.</span></span>|  
|[<span data-ttu-id="ec361-113">NewParameterizedObject 方法</span><span class="sxs-lookup"><span data-stu-id="ec361-113">NewParameterizedObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobject-method.md)|<span data-ttu-id="ec361-114">实例化一个新的参数化的类型对象并调用对象的构造函数方法。</span><span class="sxs-lookup"><span data-stu-id="ec361-114">Instantiates a new parameterized type object and calls the object's constructor method.</span></span>|  
|[<span data-ttu-id="ec361-115">NewParameterizedObjectNoConstructor 方法</span><span class="sxs-lookup"><span data-stu-id="ec361-115">NewParameterizedObjectNoConstructor Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobjectnoconstructor-method.md)|<span data-ttu-id="ec361-116">要指定的类的新参数化的类型对象但不尝试调用构造函数方法实例化</span><span class="sxs-lookup"><span data-stu-id="ec361-116">Instantiates a new parameterized type object of the specified class without attempting to call a constructor method</span></span>|  
|[<span data-ttu-id="ec361-117">NewStringWithLength 方法</span><span class="sxs-lookup"><span data-stu-id="ec361-117">NewStringWithLength Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newstringwithlength-method.md)|<span data-ttu-id="ec361-118">具有指定内容创建新字符串，指定的长度。</span><span class="sxs-lookup"><span data-stu-id="ec361-118">Creates a new string of the specified length with the specified contents.</span></span>|  
|[<span data-ttu-id="ec361-119">RudeAbort 方法</span><span class="sxs-lookup"><span data-stu-id="ec361-119">RudeAbort Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-rudeabort-method.md)|<span data-ttu-id="ec361-120">中止计算此`ICorDebugEval2`当前正在执行。</span><span class="sxs-lookup"><span data-stu-id="ec361-120">Aborts the computation that this `ICorDebugEval2` is currently performing.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ec361-121">备注</span><span class="sxs-lookup"><span data-stu-id="ec361-121">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ec361-122">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="ec361-122">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec361-123">要求</span><span class="sxs-lookup"><span data-stu-id="ec361-123">Requirements</span></span>  
 <span data-ttu-id="ec361-124">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ec361-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec361-125">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ec361-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ec361-126">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ec361-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ec361-127">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec361-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec361-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ec361-128">See Also</span></span>  
 [<span data-ttu-id="ec361-129">调试接口</span><span class="sxs-lookup"><span data-stu-id="ec361-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
