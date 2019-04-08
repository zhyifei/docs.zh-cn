---
title: ICorPublishAppDomain::GetName 方法
ms.date: 03/30/2017
api_name:
- ICorPublishAppDomain.GetName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishAppDomain::GetName
helpviewer_keywords:
- GetName method, ICorPublishAppDomain interface [.NET Framework debugging]
- ICorPublishAppDomain::GetName method [.NET Framework debugging]
ms.assetid: 6ef8ac9b-9803-4b65-8b13-25f3e0b1bc6b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5de74b52caee27a1a12cff4a7f9165a07e961ce7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59072778"
---
# <a name="icorpublishappdomaingetname-method"></a><span data-ttu-id="18f24-102">ICorPublishAppDomain::GetName 方法</span><span class="sxs-lookup"><span data-stu-id="18f24-102">ICorPublishAppDomain::GetName Method</span></span>
<span data-ttu-id="18f24-103">获取表示此应用程序域的名称[ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)。</span><span class="sxs-lookup"><span data-stu-id="18f24-103">Gets the name of the application domain that is represented by this [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18f24-104">语法</span><span class="sxs-lookup"><span data-stu-id="18f24-104">Syntax</span></span>  
  
```  
HRESULT GetName (  
    [in]  ULONG32   cchName,   
    [out] ULONG32   *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]   
        WCHAR       *szName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="18f24-105">参数</span><span class="sxs-lookup"><span data-stu-id="18f24-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="18f24-106">[in] `szName` 数组的大小。</span><span class="sxs-lookup"><span data-stu-id="18f24-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="18f24-107">[out]指向宽字符，包括在返回的 null 字符数的`szName`数组。</span><span class="sxs-lookup"><span data-stu-id="18f24-107">[out] A pointer to the number of wide characters, including the null character, returned in the `szName` array.</span></span>  
  
 `szName`  
 <span data-ttu-id="18f24-108">[out]要在其中存储名称数组。</span><span class="sxs-lookup"><span data-stu-id="18f24-108">[out] An array in which to store the name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="18f24-109">备注</span><span class="sxs-lookup"><span data-stu-id="18f24-109">Remarks</span></span>  
 <span data-ttu-id="18f24-110">如果`szName`为非 null`GetName`方法将最多复制`cchName`字符 （包括 null 终止符） 到`szName`。</span><span class="sxs-lookup"><span data-stu-id="18f24-110">If `szName` is non-null, the `GetName` method copies up to `cchName` characters (including the null terminator) into `szName`.</span></span> <span data-ttu-id="18f24-111">如果返回了非 null `pcchName`，实际名称 （包括 null 终止符） 中的字符数存储在`szName`数组。</span><span class="sxs-lookup"><span data-stu-id="18f24-111">If a non-null is returned in `pcchName`, the actual number of characters in the name (including the null terminator) is stored in the `szName` array.</span></span>  
  
 <span data-ttu-id="18f24-112">`GetName`方法返回 S_OK HRESULT 而不考虑已复制的字符数。</span><span class="sxs-lookup"><span data-stu-id="18f24-112">The `GetName` method returns an S_OK HRESULT regardless of how many characters were copied.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="18f24-113">要求</span><span class="sxs-lookup"><span data-stu-id="18f24-113">Requirements</span></span>  
 <span data-ttu-id="18f24-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="18f24-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="18f24-115">**标头：** CorPub.idl CorPub.h</span><span class="sxs-lookup"><span data-stu-id="18f24-115">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="18f24-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="18f24-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="18f24-117">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="18f24-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="18f24-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="18f24-118">See also</span></span>

- [<span data-ttu-id="18f24-119">ICorPublishAppDomain 接口</span><span class="sxs-lookup"><span data-stu-id="18f24-119">ICorPublishAppDomain Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)
