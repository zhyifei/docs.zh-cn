---
title: ICorDebugEval2::CreateValueForType 方法
ms.date: 03/30/2017
api_name:
- ICorDebugEval2.CreateValueForType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::CreateValueForType
helpviewer_keywords:
- CreateValueForType method [.NET Framework debugging]
- ICorDebugEval2::CreateValueForType method [.NET Framework debugging]
ms.assetid: ea38ae20-7e0a-427a-be77-d78fae719d82
topic_type:
- apiref
ms.openlocfilehash: 20315dfc426b63f2d526f3481756e165b388b41e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137613"
---
# <a name="icordebugeval2createvaluefortype-method"></a><span data-ttu-id="4442f-102">ICorDebugEval2::CreateValueForType 方法</span><span class="sxs-lookup"><span data-stu-id="4442f-102">ICorDebugEval2::CreateValueForType Method</span></span>
<span data-ttu-id="4442f-103">获取一个指针，该指针指向指定类型的新 ICorDebugValue，其初始值为零或 null。</span><span class="sxs-lookup"><span data-stu-id="4442f-103">Gets a pointer to a new ICorDebugValue of the specified type, with an initial value of zero or null.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4442f-104">语法</span><span class="sxs-lookup"><span data-stu-id="4442f-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateValueForType (  
    [in] ICorDebugType         *pType,  
    [out] ICorDebugValue       **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4442f-105">参数</span><span class="sxs-lookup"><span data-stu-id="4442f-105">Parameters</span></span>  
 `pType`  
 <span data-ttu-id="4442f-106">中指向表示该类型的 ICorDebugType 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="4442f-106">[in] Pointer to an ICorDebugType object that represents the type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="4442f-107">弄指向表示值的 `ICorDebugValue` 对象的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="4442f-107">[out] Pointer to the address of an `ICorDebugValue` object that represents the value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4442f-108">备注</span><span class="sxs-lookup"><span data-stu-id="4442f-108">Remarks</span></span>  
 <span data-ttu-id="4442f-109">`CreateValueForType` 通用化[ICorDebugEval：： CreateValue](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-createvalue-method.md) ，允许指定任意对象类型，包括构造类型，如 `List<int>`。</span><span class="sxs-lookup"><span data-stu-id="4442f-109">`CreateValueForType` generalizes [ICorDebugEval::CreateValue](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-createvalue-method.md) by allowing you to specify an arbitrary object type, including constructed types such as `List<int>`.</span></span> <span data-ttu-id="4442f-110">此方法的唯一目的是生成一个可传递给函数计算的值。</span><span class="sxs-lookup"><span data-stu-id="4442f-110">The only purpose of this method is to generate a value that can be passed to a function evaluation.</span></span>  
  
 <span data-ttu-id="4442f-111">类型必须是类或值类型。</span><span class="sxs-lookup"><span data-stu-id="4442f-111">The type must be a class or a value type.</span></span> <span data-ttu-id="4442f-112">不能使用此方法创建数组值或字符串值。</span><span class="sxs-lookup"><span data-stu-id="4442f-112">You cannot use this method to create array values or string values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4442f-113">要求</span><span class="sxs-lookup"><span data-stu-id="4442f-113">Requirements</span></span>  
 <span data-ttu-id="4442f-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4442f-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4442f-115">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4442f-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4442f-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4442f-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4442f-117">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4442f-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
