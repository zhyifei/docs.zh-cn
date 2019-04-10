---
title: ICorDebugModule::GetName 方法
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetName
helpviewer_keywords:
- ICorDebugModule::GetName method [.NET Framework debugging]
- GetName method, ICorDebugModule interface [.NET Framework debugging]
ms.assetid: db499637-7ba9-421e-b8b1-35856995e80b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b39467c067e50f2d553b35a41b0f783e0fc82156
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59176639"
---
# <a name="icordebugmodulegetname-method"></a><span data-ttu-id="34da4-102">ICorDebugModule::GetName 方法</span><span class="sxs-lookup"><span data-stu-id="34da4-102">ICorDebugModule::GetName Method</span></span>
<span data-ttu-id="34da4-103">获取模块的文件名。</span><span class="sxs-lookup"><span data-stu-id="34da4-103">Gets the file name of the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34da4-104">语法</span><span class="sxs-lookup"><span data-stu-id="34da4-104">Syntax</span></span>  
  
```  
HRESULT GetName(  
    [in] ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="34da4-105">参数</span><span class="sxs-lookup"><span data-stu-id="34da4-105">Parameters</span></span>  
 `cchname`  
 <span data-ttu-id="34da4-106">[in] `szName` 数组的大小。</span><span class="sxs-lookup"><span data-stu-id="34da4-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="34da4-107">[in]指向返回的名称的长度的指针。</span><span class="sxs-lookup"><span data-stu-id="34da4-107">[in] A pointer to the length of the returned name.</span></span>  
  
 `szName`  
 <span data-ttu-id="34da4-108">[out]将存储返回的名称数组。</span><span class="sxs-lookup"><span data-stu-id="34da4-108">[out] An array that stores the returned name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="34da4-109">备注</span><span class="sxs-lookup"><span data-stu-id="34da4-109">Remarks</span></span>  
 <span data-ttu-id="34da4-110">`GetName`方法返回 S_OK HRESULT，如果模块的文件名称与磁盘上的名称相匹配。</span><span class="sxs-lookup"><span data-stu-id="34da4-110">The `GetName` method returns an S_OK HRESULT if the module's file name matches the name on disk.</span></span> `GetName` <span data-ttu-id="34da4-111">如果名称为虚构，例如用于动态或内存中的模块，则返回 S_FALSE HRESULT。</span><span class="sxs-lookup"><span data-stu-id="34da4-111">returns an S_FALSE HRESULT if the name is fabricated, such as for a dynamic or in-memory module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34da4-112">要求</span><span class="sxs-lookup"><span data-stu-id="34da4-112">Requirements</span></span>  
 <span data-ttu-id="34da4-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="34da4-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34da4-114">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="34da4-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="34da4-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="34da4-115">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="34da4-116">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="34da4-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="34da4-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="34da4-117">See also</span></span>
