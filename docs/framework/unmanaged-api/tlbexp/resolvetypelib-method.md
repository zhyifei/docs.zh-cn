---
title: ResolveTypeLib 方法
ms.date: 03/30/2017
api_name:
- ResolveTypeLib
api_location:
- tlbref.dll
f1_keywords:
- ResolveTypeLib
helpviewer_keywords:
- ITypeLibResolver::ResolveTypeLib method [.NET Framework]
- ResolveTypeLib method [.NET Framework]
ms.assetid: 95d2aa0d-8eeb-4a9f-a216-5249f7e2c167
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: be2558e760be8519e528baeff438273c8871f320
ms.sourcegitcommit: 412bbc2e43c3b6ca25b358cdf394be97336f0c24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2018
ms.locfileid: "42924464"
---
# <a name="resolvetypelib-method"></a><span data-ttu-id="3dde5-102">ResolveTypeLib 方法</span><span class="sxs-lookup"><span data-stu-id="3dde5-102">ResolveTypeLib Method</span></span>
<span data-ttu-id="3dde5-103">通过返回其完全限定的路径来解析类型库的简单名称。</span><span class="sxs-lookup"><span data-stu-id="3dde5-103">Resolves the simple name of a type library by returning its fully qualified path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3dde5-104">语法</span><span class="sxs-lookup"><span data-stu-id="3dde5-104">Syntax</span></span>  
  
```  
HRESULT ResolveTypeLib(  
    [in]  BSTR      bstrSimpleName,  
    [in]  GUID      tlbid,  
    [in]  LCID      lcid,  
    [in]  USHORT    wMajorVersion,  
    [in]  USHORT    wMinorVersion,  
    [in]  SYSKIND   syskind,  
    [out] BSTR     *pbstrResolvedTlbName);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3dde5-105">参数</span><span class="sxs-lookup"><span data-stu-id="3dde5-105">Parameters</span></span>  
 `bstrSimpleName`  
 <span data-ttu-id="3dde5-106">[in]一个[BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) ，其中包含类型库的简单名称。</span><span class="sxs-lookup"><span data-stu-id="3dde5-106">[in] A [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) that contains the simple name of the type library.</span></span>  
  
 `tlbid`  
 <span data-ttu-id="3dde5-107">[in]分配给在注册表中的类型库的 GUID。</span><span class="sxs-lookup"><span data-stu-id="3dde5-107">[in] The GUID assigned to the type library in the registry.</span></span>  
  
 `lcid`  
 <span data-ttu-id="3dde5-108">[in]类型库的本地化 ID。</span><span class="sxs-lookup"><span data-stu-id="3dde5-108">[in] The localization ID of the type library.</span></span>  
  
 `wMajorVersion`  
 <span data-ttu-id="3dde5-109">[in]类型库的主版本号。</span><span class="sxs-lookup"><span data-stu-id="3dde5-109">[in] The major version number of the type library.</span></span> <span data-ttu-id="3dde5-110">例如，对于版本*x.y*，主版本号是*x*。</span><span class="sxs-lookup"><span data-stu-id="3dde5-110">For example, for version *x.y*, the major version number is *x*.</span></span>  
  
 `wMinorVersion`  
 <span data-ttu-id="3dde5-111">[in]类型库的次版本号。</span><span class="sxs-lookup"><span data-stu-id="3dde5-111">[in] The minor version number of the type library.</span></span> <span data-ttu-id="3dde5-112">例如，对于版本*x.y*的次版本号是*y*。</span><span class="sxs-lookup"><span data-stu-id="3dde5-112">For example, for version *x.y*, the minor version number is *y*.</span></span>  
  
 `syskind`  
 <span data-ttu-id="3dde5-113">[in]一个[SYSKIND](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/ne-oaidl-tagsyskind)标志，用于标识操作的环境。</span><span class="sxs-lookup"><span data-stu-id="3dde5-113">[in] A [SYSKIND](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/ne-oaidl-tagsyskind) flag that identifies the operating environment.</span></span> <span data-ttu-id="3dde5-114">常见的值为 SYS_WIN32 和 SYS_WIN64。</span><span class="sxs-lookup"><span data-stu-id="3dde5-114">Common values are SYS_WIN32 and SYS_WIN64.</span></span>  
  
 `pbstrResolvedTlbName`  
 <span data-ttu-id="3dde5-115">[out]一个指向[BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) ，其中包含在名为的类型库的完整路径`bstrSimpleName`参数。</span><span class="sxs-lookup"><span data-stu-id="3dde5-115">[out] A pointer to a [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) that contains the full path of the type library named in the `bstrSimpleName` parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3dde5-116">备注</span><span class="sxs-lookup"><span data-stu-id="3dde5-116">Remarks</span></span>  
 <span data-ttu-id="3dde5-117">`ResolveTypeLib`调用方法[LoadTypeLibWithResolver 函数](../../../../docs/framework/unmanaged-api/tlbexp/loadtypelibwithresolver-function.md)期间[Tlbexp.exe （类型库导出程序）](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md)处理。</span><span class="sxs-lookup"><span data-stu-id="3dde5-117">The `ResolveTypeLib` method is called by the [LoadTypeLibWithResolver function](../../../../docs/framework/unmanaged-api/tlbexp/loadtypelibwithresolver-function.md) during [Tlbexp.exe (Type Library Exporter)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) processing.</span></span>  
  
 <span data-ttu-id="3dde5-118">自定义此接口的实现必须返回[BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) ，其中包含在名为的类型库的完整路径`bstrSimpleName`参数。</span><span class="sxs-lookup"><span data-stu-id="3dde5-118">Custom implementations of this interface must return a [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) that contains the full path of the type library named in the `bstrSimpleName` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3dde5-119">要求</span><span class="sxs-lookup"><span data-stu-id="3dde5-119">Requirements</span></span>  
 <span data-ttu-id="3dde5-120">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3dde5-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3dde5-121">**标头：** TlbRef.idl、 TlbRef.h</span><span class="sxs-lookup"><span data-stu-id="3dde5-121">**Header:** TlbRef.idl, TlbRef.h</span></span>  
  
 <span data-ttu-id="3dde5-122">**库：** TlbRef.lib</span><span class="sxs-lookup"><span data-stu-id="3dde5-122">**Library:** TlbRef.lib</span></span>  
  
 <span data-ttu-id="3dde5-123">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3dde5-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3dde5-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="3dde5-124">See Also</span></span>  
 [<span data-ttu-id="3dde5-125">Tlbexp Helper 函数</span><span class="sxs-lookup"><span data-stu-id="3dde5-125">Tlbexp Helper Functions</span></span>](../../../../docs/framework/unmanaged-api/tlbexp/index.md)  
 [<span data-ttu-id="3dde5-126">LoadTypeLibEx</span><span class="sxs-lookup"><span data-stu-id="3dde5-126">LoadTypeLibEx</span></span>](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)
