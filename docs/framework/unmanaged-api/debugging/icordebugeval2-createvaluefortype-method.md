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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 683457c249915708becadaeda9dec265666e2023
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33412102"
---
# <a name="icordebugeval2createvaluefortype-method"></a><span data-ttu-id="187c0-102">ICorDebugEval2::CreateValueForType 方法</span><span class="sxs-lookup"><span data-stu-id="187c0-102">ICorDebugEval2::CreateValueForType Method</span></span>
<span data-ttu-id="187c0-103">获取一个指向指定的类型中，新 ICorDebugValue 其初始值为零或 null。</span><span class="sxs-lookup"><span data-stu-id="187c0-103">Gets a pointer to a new ICorDebugValue of the specified type, with an initial value of zero or null.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="187c0-104">语法</span><span class="sxs-lookup"><span data-stu-id="187c0-104">Syntax</span></span>  
  
```  
HRESULT CreateValueForType (  
    [in] ICorDebugType         *pType,  
    [out] ICorDebugValue       **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="187c0-105">参数</span><span class="sxs-lookup"><span data-stu-id="187c0-105">Parameters</span></span>  
 `pType`  
 <span data-ttu-id="187c0-106">[in]指向 ICorDebugType 对象表示类型的指针。</span><span class="sxs-lookup"><span data-stu-id="187c0-106">[in] Pointer to an ICorDebugType object that represents the type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="187c0-107">[out]指向的地址指针`ICorDebugValue`表示的值的对象。</span><span class="sxs-lookup"><span data-stu-id="187c0-107">[out] Pointer to the address of an `ICorDebugValue` object that represents the value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="187c0-108">备注</span><span class="sxs-lookup"><span data-stu-id="187c0-108">Remarks</span></span>  
 <span data-ttu-id="187c0-109">`CreateValueForType` 通用化[icordebugeval:: Createvalue](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-createvalue-method.md)通过允许你指定的任意对象类型，包括构造类型如`List<int>`。</span><span class="sxs-lookup"><span data-stu-id="187c0-109">`CreateValueForType` generalizes [ICorDebugEval::CreateValue](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-createvalue-method.md) by allowing you to specify an arbitrary object type, including constructed types such as `List<int>`.</span></span> <span data-ttu-id="187c0-110">此方法的唯一目的是生成一个值，可以传递给函数求值。</span><span class="sxs-lookup"><span data-stu-id="187c0-110">The only purpose of this method is to generate a value that can be passed to a function evaluation.</span></span>  
  
 <span data-ttu-id="187c0-111">类型必须是一个类或值类型。</span><span class="sxs-lookup"><span data-stu-id="187c0-111">The type must be a class or a value type.</span></span> <span data-ttu-id="187c0-112">此方法不能用于创建数组值或字符串值。</span><span class="sxs-lookup"><span data-stu-id="187c0-112">You cannot use this method to create array values or string values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="187c0-113">要求</span><span class="sxs-lookup"><span data-stu-id="187c0-113">Requirements</span></span>  
 <span data-ttu-id="187c0-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="187c0-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="187c0-115">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="187c0-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="187c0-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="187c0-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="187c0-117">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="187c0-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
