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
ms.openlocfilehash: 5a6e0b009674ff52595aaa0ae4a060f1cdfd1398
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73089049"
---
# <a name="icordebugappdomain2getfunctionpointertype-method"></a><span data-ttu-id="47a5a-102">ICorDebugAppDomain2::GetFunctionPointerType 方法</span><span class="sxs-lookup"><span data-stu-id="47a5a-102">ICorDebugAppDomain2::GetFunctionPointerType Method</span></span>
<span data-ttu-id="47a5a-103">获取一个指针，该指针指向具有给定签名的函数。</span><span class="sxs-lookup"><span data-stu-id="47a5a-103">Gets a pointer to a function that has a given signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47a5a-104">语法</span><span class="sxs-lookup"><span data-stu-id="47a5a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionPointerType (  
    [in] ULONG32                             nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType   *ppTypeArgs[],  
    [out] ICorDebugType                      **ppType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="47a5a-105">参数</span><span class="sxs-lookup"><span data-stu-id="47a5a-105">Parameters</span></span>  
 `nTypeArgs`  
 <span data-ttu-id="47a5a-106">中函数的类型参数的数目。</span><span class="sxs-lookup"><span data-stu-id="47a5a-106">[in] The number of type arguments for the function.</span></span>  
  
 `ppTypeArgs`  
 <span data-ttu-id="47a5a-107">中指针的数组，其中每个都指向表示函数类型参数的 ICorDebugType 对象。</span><span class="sxs-lookup"><span data-stu-id="47a5a-107">[in] An array of pointers, each of which points to an ICorDebugType object that represents a type argument of the function.</span></span> <span data-ttu-id="47a5a-108">第一个元素是返回类型;其他每个元素都是一个参数类型。</span><span class="sxs-lookup"><span data-stu-id="47a5a-108">The first element is the return type; each of the other elements is a parameter type.</span></span>  
  
 `ppType`  
 <span data-ttu-id="47a5a-109">弄指向表示指向函数的指针的 `ICorDebugType` 对象地址的指针。</span><span class="sxs-lookup"><span data-stu-id="47a5a-109">[out] A pointer to the address of an `ICorDebugType` object that represents the pointer to the function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="47a5a-110">要求</span><span class="sxs-lookup"><span data-stu-id="47a5a-110">Requirements</span></span>  
 <span data-ttu-id="47a5a-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="47a5a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47a5a-112">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="47a5a-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="47a5a-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="47a5a-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="47a5a-114">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="47a5a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
