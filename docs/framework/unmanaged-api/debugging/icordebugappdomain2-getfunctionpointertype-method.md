---
title: ICorDebugAppDomain2::GetFunctionPointerType 方法
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain2.GetFunctionPointerType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain2::GetFunctionPointerType
helpviewer_keywords:
- ICorDebugAppDomain2::GetFunctionPointerType method [.NET Framework debugging]
- GetFunctionPointerType method [.NET Framework debugging]
ms.assetid: 0aba6096-5b38-435c-a72a-86d35db4daef
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ec1a9968dbec10783c6f1383fb523e95ff79561e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61683896"
---
# <a name="icordebugappdomain2getfunctionpointertype-method"></a><span data-ttu-id="7bef7-102">ICorDebugAppDomain2::GetFunctionPointerType 方法</span><span class="sxs-lookup"><span data-stu-id="7bef7-102">ICorDebugAppDomain2::GetFunctionPointerType Method</span></span>
<span data-ttu-id="7bef7-103">获取一个指向具有给定的签名的函数。</span><span class="sxs-lookup"><span data-stu-id="7bef7-103">Gets a pointer to a function that has a given signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7bef7-104">语法</span><span class="sxs-lookup"><span data-stu-id="7bef7-104">Syntax</span></span>  
  
```  
HRESULT GetFunctionPointerType (  
    [in] ULONG32                             nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType   *ppTypeArgs[],  
    [out] ICorDebugType                      **ppType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7bef7-105">参数</span><span class="sxs-lookup"><span data-stu-id="7bef7-105">Parameters</span></span>  
 `nTypeArgs`  
 <span data-ttu-id="7bef7-106">[in]该函数的类型参数的数目。</span><span class="sxs-lookup"><span data-stu-id="7bef7-106">[in] The number of type arguments for the function.</span></span>  
  
 `ppTypeArgs`  
 <span data-ttu-id="7bef7-107">[in]一个指针数组，其中每个指向对象的表示函数的类型参数。</span><span class="sxs-lookup"><span data-stu-id="7bef7-107">[in] An array of pointers, each of which points to an ICorDebugType object that represents a type argument of the function.</span></span> <span data-ttu-id="7bef7-108">第一个元素是返回类型;每个其他元素是参数类型。</span><span class="sxs-lookup"><span data-stu-id="7bef7-108">The first element is the return type; each of the other elements is a parameter type.</span></span>  
  
 `ppType`  
 <span data-ttu-id="7bef7-109">[out]指向的地址的指针`ICorDebugType`对象表示该函数的指针。</span><span class="sxs-lookup"><span data-stu-id="7bef7-109">[out] A pointer to the address of an `ICorDebugType` object that represents the pointer to the function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7bef7-110">要求</span><span class="sxs-lookup"><span data-stu-id="7bef7-110">Requirements</span></span>  
 <span data-ttu-id="7bef7-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7bef7-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7bef7-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7bef7-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7bef7-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7bef7-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7bef7-114">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7bef7-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
