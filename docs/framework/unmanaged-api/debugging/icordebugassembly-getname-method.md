---
title: ICorDebugAssembly::GetName 方法
ms.date: 03/30/2017
api_name:
- ICorDebugAssembly.GetName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly::GetName
helpviewer_keywords:
- ICorDebugAssembly::GetName method [.NET Framework debugging]
- GetName method, ICorDebugAssembly interface [.NET Framework debugging]
ms.assetid: cdeda721-b214-4503-a291-c70b68b5f36b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3077e0494816a083d97839d66d06b18130e5dac8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645573"
---
# <a name="icordebugassemblygetname-method"></a><span data-ttu-id="267c4-102">ICorDebugAssembly::GetName 方法</span><span class="sxs-lookup"><span data-stu-id="267c4-102">ICorDebugAssembly::GetName Method</span></span>
<span data-ttu-id="267c4-103">获取程序集的名称，这`ICorDebugAssembly`实例所表示。</span><span class="sxs-lookup"><span data-stu-id="267c4-103">Gets the name of the assembly that this `ICorDebugAssembly` instance represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="267c4-104">语法</span><span class="sxs-lookup"><span data-stu-id="267c4-104">Syntax</span></span>  
  
```  
HRESULT GetName (  
    [in] ULONG32  cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="267c4-105">参数</span><span class="sxs-lookup"><span data-stu-id="267c4-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="267c4-106">[in] `szName` 数组的大小。</span><span class="sxs-lookup"><span data-stu-id="267c4-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="267c4-107">[out]指向一个整数，指定名称的实际长度的指针。</span><span class="sxs-lookup"><span data-stu-id="267c4-107">[out] A pointer to an integer that specifies the actual length of the name.</span></span>  
  
 `szName`  
 <span data-ttu-id="267c4-108">[out]存储的名称数组。</span><span class="sxs-lookup"><span data-stu-id="267c4-108">[out] An array that stores the name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="267c4-109">备注</span><span class="sxs-lookup"><span data-stu-id="267c4-109">Remarks</span></span>  
 <span data-ttu-id="267c4-110">`GetName`方法返回的程序集的完整路径和文件名称。</span><span class="sxs-lookup"><span data-stu-id="267c4-110">The `GetName` method returns the full path and file name of the assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="267c4-111">要求</span><span class="sxs-lookup"><span data-stu-id="267c4-111">Requirements</span></span>  
 <span data-ttu-id="267c4-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="267c4-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="267c4-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="267c4-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="267c4-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="267c4-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="267c4-115">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="267c4-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
