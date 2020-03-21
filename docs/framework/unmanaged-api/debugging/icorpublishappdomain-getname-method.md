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
ms.openlocfilehash: 762c637696fdf79ccab6702918b5bf962ea55903
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178405"
---
# <a name="icorpublishappdomaingetname-method"></a><span data-ttu-id="41bf6-102">ICorPublishAppDomain::GetName 方法</span><span class="sxs-lookup"><span data-stu-id="41bf6-102">ICorPublishAppDomain::GetName Method</span></span>
<span data-ttu-id="41bf6-103">获取此[ICorPublishAppDomain](icorpublishappdomain-interface.md)表示的应用程序域的名称。</span><span class="sxs-lookup"><span data-stu-id="41bf6-103">Gets the name of the application domain that is represented by this [ICorPublishAppDomain](icorpublishappdomain-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41bf6-104">语法</span><span class="sxs-lookup"><span data-stu-id="41bf6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName (  
    [in]  ULONG32   cchName,
    [out] ULONG32   *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]
        WCHAR       *szName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="41bf6-105">parameters</span><span class="sxs-lookup"><span data-stu-id="41bf6-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="41bf6-106">[in] `szName` 数组的大小。</span><span class="sxs-lookup"><span data-stu-id="41bf6-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="41bf6-107">[出]数组中返回的指向宽字符数（包括空字符）的`szName`指针。</span><span class="sxs-lookup"><span data-stu-id="41bf6-107">[out] A pointer to the number of wide characters, including the null character, returned in the `szName` array.</span></span>  
  
 `szName`  
 <span data-ttu-id="41bf6-108">[出]要在其中存储名称的数组。</span><span class="sxs-lookup"><span data-stu-id="41bf6-108">[out] An array in which to store the name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="41bf6-109">备注</span><span class="sxs-lookup"><span data-stu-id="41bf6-109">Remarks</span></span>  
 <span data-ttu-id="41bf6-110">如果`szName`为非空，`GetName`则该方法将最多复制到`cchName`字符（包括空终止符）到`szName`中。</span><span class="sxs-lookup"><span data-stu-id="41bf6-110">If `szName` is non-null, the `GetName` method copies up to `cchName` characters (including the null terminator) into `szName`.</span></span> <span data-ttu-id="41bf6-111">如果在 中`pcchName`返回非 null，则名称中（包括空终止符）中的实际字符数存储在数组中`szName`。</span><span class="sxs-lookup"><span data-stu-id="41bf6-111">If a non-null is returned in `pcchName`, the actual number of characters in the name (including the null terminator) is stored in the `szName` array.</span></span>  
  
 <span data-ttu-id="41bf6-112">无论`GetName`复制的字符数如何，该方法都会返回S_OK HRESULT。</span><span class="sxs-lookup"><span data-stu-id="41bf6-112">The `GetName` method returns an S_OK HRESULT regardless of how many characters were copied.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41bf6-113">要求</span><span class="sxs-lookup"><span data-stu-id="41bf6-113">Requirements</span></span>  
 <span data-ttu-id="41bf6-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="41bf6-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41bf6-115">**标题：** 科尔普布.idl， 科尔普布.h</span><span class="sxs-lookup"><span data-stu-id="41bf6-115">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="41bf6-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="41bf6-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="41bf6-117">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="41bf6-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41bf6-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="41bf6-118">See also</span></span>

- [<span data-ttu-id="41bf6-119">ICorPublishAppDomain 接口</span><span class="sxs-lookup"><span data-stu-id="41bf6-119">ICorPublishAppDomain Interface</span></span>](icorpublishappdomain-interface.md)
