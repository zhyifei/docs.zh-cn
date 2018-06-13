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
ms.openlocfilehash: 796f8ea42cc5cbe13729f7b92e15bc214d62734d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33423853"
---
# <a name="icorpublishappdomaingetname-method"></a><span data-ttu-id="58f07-102">ICorPublishAppDomain::GetName 方法</span><span class="sxs-lookup"><span data-stu-id="58f07-102">ICorPublishAppDomain::GetName Method</span></span>
<span data-ttu-id="58f07-103">获取表示此应用程序域的名称[ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)。</span><span class="sxs-lookup"><span data-stu-id="58f07-103">Gets the name of the application domain that is represented by this [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58f07-104">语法</span><span class="sxs-lookup"><span data-stu-id="58f07-104">Syntax</span></span>  
  
```  
HRESULT GetName (  
    [in]  ULONG32   cchName,   
    [out] ULONG32   *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]   
        WCHAR       *szName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="58f07-105">参数</span><span class="sxs-lookup"><span data-stu-id="58f07-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="58f07-106">[in] `szName` 数组的大小。</span><span class="sxs-lookup"><span data-stu-id="58f07-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="58f07-107">[out]指向的宽字符，包括 null 字符，在中返回数的指针`szName`数组。</span><span class="sxs-lookup"><span data-stu-id="58f07-107">[out] A pointer to the number of wide characters, including the null character, returned in the `szName` array.</span></span>  
  
 `szName`  
 <span data-ttu-id="58f07-108">[out]在其中存储名称的数组。</span><span class="sxs-lookup"><span data-stu-id="58f07-108">[out] An array in which to store the name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="58f07-109">备注</span><span class="sxs-lookup"><span data-stu-id="58f07-109">Remarks</span></span>  
 <span data-ttu-id="58f07-110">如果`szName`为非 null`GetName`方法复制达`cchName`字符 （包括 null 终止符） 到`szName`。</span><span class="sxs-lookup"><span data-stu-id="58f07-110">If `szName` is non-null, the `GetName` method copies up to `cchName` characters (including the null terminator) into `szName`.</span></span> <span data-ttu-id="58f07-111">如果非 null 返回在`pcchName`的实际名称 （包括 null 终止符） 中的字符数存储在`szName`数组。</span><span class="sxs-lookup"><span data-stu-id="58f07-111">If a non-null is returned in `pcchName`, the actual number of characters in the name (including the null terminator) is stored in the `szName` array.</span></span>  
  
 <span data-ttu-id="58f07-112">`GetName`方法将返回而不考虑多少个字符已复制的则为 S_OK HRESULT。</span><span class="sxs-lookup"><span data-stu-id="58f07-112">The `GetName` method returns an S_OK HRESULT regardless of how many characters were copied.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58f07-113">要求</span><span class="sxs-lookup"><span data-stu-id="58f07-113">Requirements</span></span>  
 <span data-ttu-id="58f07-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="58f07-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58f07-115">**标头：** CorPub.idl、 CorPub.h</span><span class="sxs-lookup"><span data-stu-id="58f07-115">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="58f07-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="58f07-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="58f07-117">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58f07-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58f07-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="58f07-118">See Also</span></span>  
 [<span data-ttu-id="58f07-119">ICorPublishAppDomain 接口</span><span class="sxs-lookup"><span data-stu-id="58f07-119">ICorPublishAppDomain Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)
