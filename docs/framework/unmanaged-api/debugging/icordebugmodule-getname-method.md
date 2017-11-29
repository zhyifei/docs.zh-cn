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
ms.openlocfilehash: 0b10e0eed3c2df8781aa7085cc43157894cc6e2c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugmodulegetname-method"></a><span data-ttu-id="38a86-102">ICorDebugModule::GetName 方法</span><span class="sxs-lookup"><span data-stu-id="38a86-102">ICorDebugModule::GetName Method</span></span>
<span data-ttu-id="38a86-103">获取模块的文件名。</span><span class="sxs-lookup"><span data-stu-id="38a86-103">Gets the file name of the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38a86-104">语法</span><span class="sxs-lookup"><span data-stu-id="38a86-104">Syntax</span></span>  
  
```  
HRESULT GetName(  
    [in] ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="38a86-105">参数</span><span class="sxs-lookup"><span data-stu-id="38a86-105">Parameters</span></span>  
 `cchname`  
 <span data-ttu-id="38a86-106">[in] `szName` 数组的大小。</span><span class="sxs-lookup"><span data-stu-id="38a86-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="38a86-107">[in]指向返回的名称的长度的指针。</span><span class="sxs-lookup"><span data-stu-id="38a86-107">[in] A pointer to the length of the returned name.</span></span>  
  
 `szName`  
 <span data-ttu-id="38a86-108">[out]一个数组，将存储返回的名称。</span><span class="sxs-lookup"><span data-stu-id="38a86-108">[out] An array that stores the returned name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="38a86-109">备注</span><span class="sxs-lookup"><span data-stu-id="38a86-109">Remarks</span></span>  
 <span data-ttu-id="38a86-110">`GetName`方法返回，则为 S_OK HRESULT，如果模块的文件名称与磁盘上的名称相匹配。</span><span class="sxs-lookup"><span data-stu-id="38a86-110">The `GetName` method returns an S_OK HRESULT if the module's file name matches the name on disk.</span></span> <span data-ttu-id="38a86-111">`GetName`如果名称为虚构，例如对于动态或内存中的模块，请返回一个 S_FALSE HRESULT。</span><span class="sxs-lookup"><span data-stu-id="38a86-111">`GetName` returns an S_FALSE HRESULT if the name is fabricated, such as for a dynamic or in-memory module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="38a86-112">要求</span><span class="sxs-lookup"><span data-stu-id="38a86-112">Requirements</span></span>  
 <span data-ttu-id="38a86-113">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="38a86-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38a86-114">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="38a86-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="38a86-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="38a86-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="38a86-116">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38a86-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38a86-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="38a86-117">See Also</span></span>  
    
 
