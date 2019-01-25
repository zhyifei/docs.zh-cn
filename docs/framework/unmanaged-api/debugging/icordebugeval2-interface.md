---
title: ICorDebugEval2 接口 1
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7c50dc8e40b6565ae1bf3a5d83f4deb80d2bf0a8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54712978"
---
# <a name="icordebugeval2-interface1"></a><span data-ttu-id="cb8ed-102">ICorDebugEval2 接口 1</span><span class="sxs-lookup"><span data-stu-id="cb8ed-102">ICorDebugEval2 Interface1</span></span>
<span data-ttu-id="cb8ed-103">扩展了"ICorDebugEval"为泛型类型提供支持。</span><span class="sxs-lookup"><span data-stu-id="cb8ed-103">Extends "ICorDebugEval" to provide support for generic types.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cb8ed-104">方法</span><span class="sxs-lookup"><span data-stu-id="cb8ed-104">Methods</span></span>  
  
|<span data-ttu-id="cb8ed-105">方法</span><span class="sxs-lookup"><span data-stu-id="cb8ed-105">Method</span></span>|<span data-ttu-id="cb8ed-106">描述</span><span class="sxs-lookup"><span data-stu-id="cb8ed-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cb8ed-107">CallParameterizedFunction 方法</span><span class="sxs-lookup"><span data-stu-id="cb8ed-107">CallParameterizedFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-callparameterizedfunction-method.md)|<span data-ttu-id="cb8ed-108">设置指定"ICorDebugFunction"，这可以嵌套在其构造函数采用类型参数或本身可以接受类型参数的类型内部调用。</span><span class="sxs-lookup"><span data-stu-id="cb8ed-108">Sets up a call to the specified "ICorDebugFunction", which can be nested inside a type whose constructor takes type parameters, or can itself take type parameters.</span></span>|  
|[<span data-ttu-id="cb8ed-109">CreateValueForType 方法</span><span class="sxs-lookup"><span data-stu-id="cb8ed-109">CreateValueForType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md)|<span data-ttu-id="cb8ed-110">获取一个指向新的"ICorDebugValue"的指定类型，其初始值为 null 或零。</span><span class="sxs-lookup"><span data-stu-id="cb8ed-110">Gets a pointer to a new "ICorDebugValue" of the specified type, with an initial value of null or zero.</span></span>|  
|[<span data-ttu-id="cb8ed-111">NewParameterizedArray 方法</span><span class="sxs-lookup"><span data-stu-id="cb8ed-111">NewParameterizedArray Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedarray-method.md)|<span data-ttu-id="cb8ed-112">分配的指定的元素类型和维度的一个新数组。</span><span class="sxs-lookup"><span data-stu-id="cb8ed-112">Allocates a new array of the specified element type and dimensions.</span></span>|  
|[<span data-ttu-id="cb8ed-113">NewParameterizedObject 方法</span><span class="sxs-lookup"><span data-stu-id="cb8ed-113">NewParameterizedObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobject-method.md)|<span data-ttu-id="cb8ed-114">实例化一个新的参数化的类型对象并调用该对象的构造函数方法。</span><span class="sxs-lookup"><span data-stu-id="cb8ed-114">Instantiates a new parameterized type object and calls the object's constructor method.</span></span>|  
|[<span data-ttu-id="cb8ed-115">NewParameterizedObjectNoConstructor 方法</span><span class="sxs-lookup"><span data-stu-id="cb8ed-115">NewParameterizedObjectNoConstructor Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobjectnoconstructor-method.md)|<span data-ttu-id="cb8ed-116">而不会尝试调用构造函数方法实例化指定的类的新参数化的类型对象</span><span class="sxs-lookup"><span data-stu-id="cb8ed-116">Instantiates a new parameterized type object of the specified class without attempting to call a constructor method</span></span>|  
|[<span data-ttu-id="cb8ed-117">NewStringWithLength 方法</span><span class="sxs-lookup"><span data-stu-id="cb8ed-117">NewStringWithLength Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newstringwithlength-method.md)|<span data-ttu-id="cb8ed-118">使用指定的内容创建指定长度的一个新字符串。</span><span class="sxs-lookup"><span data-stu-id="cb8ed-118">Creates a new string of the specified length with the specified contents.</span></span>|  
|[<span data-ttu-id="cb8ed-119">RudeAbort 方法</span><span class="sxs-lookup"><span data-stu-id="cb8ed-119">RudeAbort Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-rudeabort-method.md)|<span data-ttu-id="cb8ed-120">中止计算此`ICorDebugEval2`当前正在执行。</span><span class="sxs-lookup"><span data-stu-id="cb8ed-120">Aborts the computation that this `ICorDebugEval2` is currently performing.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cb8ed-121">备注</span><span class="sxs-lookup"><span data-stu-id="cb8ed-121">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cb8ed-122">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="cb8ed-122">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cb8ed-123">要求</span><span class="sxs-lookup"><span data-stu-id="cb8ed-123">Requirements</span></span>  
 <span data-ttu-id="cb8ed-124">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="cb8ed-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cb8ed-125">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cb8ed-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cb8ed-126">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cb8ed-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cb8ed-127">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cb8ed-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb8ed-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="cb8ed-128">See also</span></span>
- [<span data-ttu-id="cb8ed-129">调试接口</span><span class="sxs-lookup"><span data-stu-id="cb8ed-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
