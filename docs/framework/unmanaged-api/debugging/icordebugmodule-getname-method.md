---
title: "ICorDebugModule::GetName 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugModule.GetName
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugModule::GetName
helpviewer_keywords:
- ICorDebugModule::GetName method [.NET Framework debugging]
- GetName method, ICorDebugModule interface [.NET Framework debugging]
ms.assetid: db499637-7ba9-421e-b8b1-35856995e80b
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 64be936277b0ebe04248ae2913a882b628ee363f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmodulegetname-method"></a><span data-ttu-id="ee916-102">ICorDebugModule::GetName 方法</span><span class="sxs-lookup"><span data-stu-id="ee916-102">ICorDebugModule::GetName Method</span></span>
<span data-ttu-id="ee916-103">获取模块的文件名。</span><span class="sxs-lookup"><span data-stu-id="ee916-103">Gets the file name of the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee916-104">语法</span><span class="sxs-lookup"><span data-stu-id="ee916-104">Syntax</span></span>  
  
```  
HRESULT GetName(  
    [in] ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ee916-105">参数</span><span class="sxs-lookup"><span data-stu-id="ee916-105">Parameters</span></span>  
 `cchname`  
 <span data-ttu-id="ee916-106">[in] `szName` 数组的大小。</span><span class="sxs-lookup"><span data-stu-id="ee916-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="ee916-107">[in]指向返回的名称的长度的指针。</span><span class="sxs-lookup"><span data-stu-id="ee916-107">[in] A pointer to the length of the returned name.</span></span>  
  
 `szName`  
 <span data-ttu-id="ee916-108">[out]一个数组，将存储返回的名称。</span><span class="sxs-lookup"><span data-stu-id="ee916-108">[out] An array that stores the returned name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ee916-109">备注</span><span class="sxs-lookup"><span data-stu-id="ee916-109">Remarks</span></span>  
 <span data-ttu-id="ee916-110">`GetName`方法返回，则为 S_OK HRESULT，如果模块的文件名称与磁盘上的名称相匹配。</span><span class="sxs-lookup"><span data-stu-id="ee916-110">The `GetName` method returns an S_OK HRESULT if the module's file name matches the name on disk.</span></span> <span data-ttu-id="ee916-111">`GetName`如果名称为虚构，例如对于动态或内存中的模块，请返回一个 S_FALSE HRESULT。</span><span class="sxs-lookup"><span data-stu-id="ee916-111">`GetName` returns an S_FALSE HRESULT if the name is fabricated, such as for a dynamic or in-memory module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee916-112">惠?</span><span class="sxs-lookup"><span data-stu-id="ee916-112">Requirements</span></span>  
 <span data-ttu-id="ee916-113">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ee916-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee916-114">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ee916-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ee916-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ee916-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ee916-116">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ee916-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee916-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="ee916-117">See Also</span></span>  
    
 
