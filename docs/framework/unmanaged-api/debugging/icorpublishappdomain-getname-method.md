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
ms.openlocfilehash: 4325d61d12a66b17f88e5e368cbbc7806d0a3ec5
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790706"
---
# <a name="icorpublishappdomaingetname-method"></a><span data-ttu-id="73f3a-102">ICorPublishAppDomain::GetName 方法</span><span class="sxs-lookup"><span data-stu-id="73f3a-102">ICorPublishAppDomain::GetName Method</span></span>
<span data-ttu-id="73f3a-103">获取此[ICorPublishAppDomain](icorpublishappdomain-interface.md)所表示的应用程序域的名称。</span><span class="sxs-lookup"><span data-stu-id="73f3a-103">Gets the name of the application domain that is represented by this [ICorPublishAppDomain](icorpublishappdomain-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73f3a-104">语法</span><span class="sxs-lookup"><span data-stu-id="73f3a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName (  
    [in]  ULONG32   cchName,   
    [out] ULONG32   *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]   
        WCHAR       *szName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="73f3a-105">参数</span><span class="sxs-lookup"><span data-stu-id="73f3a-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="73f3a-106">[in] `szName` 数组的大小。</span><span class="sxs-lookup"><span data-stu-id="73f3a-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="73f3a-107">弄一个指针，指向在 `szName` 数组中返回的宽字符数，包括 null 字符。</span><span class="sxs-lookup"><span data-stu-id="73f3a-107">[out] A pointer to the number of wide characters, including the null character, returned in the `szName` array.</span></span>  
  
 `szName`  
 <span data-ttu-id="73f3a-108">弄要在其中存储名称的数组。</span><span class="sxs-lookup"><span data-stu-id="73f3a-108">[out] An array in which to store the name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="73f3a-109">备注</span><span class="sxs-lookup"><span data-stu-id="73f3a-109">Remarks</span></span>  
 <span data-ttu-id="73f3a-110">如果 `szName` 为非 null，则 `GetName` 方法会将最多 `cchName` 个字符（包括 null 结束符）复制到 `szName`中。</span><span class="sxs-lookup"><span data-stu-id="73f3a-110">If `szName` is non-null, the `GetName` method copies up to `cchName` characters (including the null terminator) into `szName`.</span></span> <span data-ttu-id="73f3a-111">如果在 `pcchName`中返回非 null，则名称中的实际字符数（包括 null 终止符）将存储在 `szName` 数组中。</span><span class="sxs-lookup"><span data-stu-id="73f3a-111">If a non-null is returned in `pcchName`, the actual number of characters in the name (including the null terminator) is stored in the `szName` array.</span></span>  
  
 <span data-ttu-id="73f3a-112">无论复制了多少个字符，`GetName` 方法都将返回一个 S_OK HRESULT。</span><span class="sxs-lookup"><span data-stu-id="73f3a-112">The `GetName` method returns an S_OK HRESULT regardless of how many characters were copied.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="73f3a-113">需求</span><span class="sxs-lookup"><span data-stu-id="73f3a-113">Requirements</span></span>  
 <span data-ttu-id="73f3a-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="73f3a-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="73f3a-115">**标头：** CorPub，CorPub</span><span class="sxs-lookup"><span data-stu-id="73f3a-115">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="73f3a-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="73f3a-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="73f3a-117">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73f3a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73f3a-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="73f3a-118">See also</span></span>

- [<span data-ttu-id="73f3a-119">ICorPublishAppDomain 接口</span><span class="sxs-lookup"><span data-stu-id="73f3a-119">ICorPublishAppDomain Interface</span></span>](icorpublishappdomain-interface.md)
