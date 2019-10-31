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
ms.openlocfilehash: 46cd8b5c22f48ba45c4da7fa8876d6807a21f2b3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124143"
---
# <a name="resolvetypelib-method"></a><span data-ttu-id="bb3bb-102">ResolveTypeLib 方法</span><span class="sxs-lookup"><span data-stu-id="bb3bb-102">ResolveTypeLib Method</span></span>
<span data-ttu-id="bb3bb-103">通过返回类型库的完全限定路径来解析该类型库的简单名称。</span><span class="sxs-lookup"><span data-stu-id="bb3bb-103">Resolves the simple name of a type library by returning its fully qualified path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb3bb-104">语法</span><span class="sxs-lookup"><span data-stu-id="bb3bb-104">Syntax</span></span>  
  
```cpp  
HRESULT ResolveTypeLib(  
    [in]  BSTR      bstrSimpleName,  
    [in]  GUID      tlbid,  
    [in]  LCID      lcid,  
    [in]  USHORT    wMajorVersion,  
    [in]  USHORT    wMinorVersion,  
    [in]  SYSKIND   syskind,  
    [out] BSTR     *pbstrResolvedTlbName);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bb3bb-105">参数</span><span class="sxs-lookup"><span data-stu-id="bb3bb-105">Parameters</span></span>  
 `bstrSimpleName`  
 <span data-ttu-id="bb3bb-106">中一个[BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) ，其中包含类型库的简单名称。</span><span class="sxs-lookup"><span data-stu-id="bb3bb-106">[in] A [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) that contains the simple name of the type library.</span></span>  
  
 `tlbid`  
 <span data-ttu-id="bb3bb-107">中分配给注册表中的类型库的 GUID。</span><span class="sxs-lookup"><span data-stu-id="bb3bb-107">[in] The GUID assigned to the type library in the registry.</span></span>  
  
 `lcid`  
 <span data-ttu-id="bb3bb-108">中类型库的本地化 ID。</span><span class="sxs-lookup"><span data-stu-id="bb3bb-108">[in] The localization ID of the type library.</span></span>  
  
 `wMajorVersion`  
 <span data-ttu-id="bb3bb-109">中类型库的主版本号。</span><span class="sxs-lookup"><span data-stu-id="bb3bb-109">[in] The major version number of the type library.</span></span> <span data-ttu-id="bb3bb-110">例如，对于版本*x. y*，主版本号是*x*。</span><span class="sxs-lookup"><span data-stu-id="bb3bb-110">For example, for version *x.y*, the major version number is *x*.</span></span>  
  
 `wMinorVersion`  
 <span data-ttu-id="bb3bb-111">中类型库的次版本号。</span><span class="sxs-lookup"><span data-stu-id="bb3bb-111">[in] The minor version number of the type library.</span></span> <span data-ttu-id="bb3bb-112">例如，对于版本*x. y*，次版本号为*y*。</span><span class="sxs-lookup"><span data-stu-id="bb3bb-112">For example, for version *x.y*, the minor version number is *y*.</span></span>  
  
 `syskind`  
 <span data-ttu-id="bb3bb-113">中标识操作环境的[SYSKIND](https://docs.microsoft.com/windows/win32/api/oaidl/ne-oaidl-syskind)标志。</span><span class="sxs-lookup"><span data-stu-id="bb3bb-113">[in] A [SYSKIND](https://docs.microsoft.com/windows/win32/api/oaidl/ne-oaidl-syskind) flag that identifies the operating environment.</span></span> <span data-ttu-id="bb3bb-114">常见值为 SYS_WIN32 和 SYS_WIN64。</span><span class="sxs-lookup"><span data-stu-id="bb3bb-114">Common values are SYS_WIN32 and SYS_WIN64.</span></span>  
  
 `pbstrResolvedTlbName`  
 <span data-ttu-id="bb3bb-115">弄指向包含在 `bstrSimpleName` 参数中命名的类型库的完整路径的[BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr)的指针。</span><span class="sxs-lookup"><span data-stu-id="bb3bb-115">[out] A pointer to a [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) that contains the full path of the type library named in the `bstrSimpleName` parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bb3bb-116">备注</span><span class="sxs-lookup"><span data-stu-id="bb3bb-116">Remarks</span></span>  
 <span data-ttu-id="bb3bb-117">`ResolveTypeLib` 方法由[LoadTypeLibWithResolver 函数](loadtypelibwithresolver-function.md)在[Tlbexp.exe （类型库导出程序）](../../tools/tlbexp-exe-type-library-exporter.md)处理期间调用。</span><span class="sxs-lookup"><span data-stu-id="bb3bb-117">The `ResolveTypeLib` method is called by the [LoadTypeLibWithResolver function](loadtypelibwithresolver-function.md) during [Tlbexp.exe (Type Library Exporter)](../../tools/tlbexp-exe-type-library-exporter.md) processing.</span></span>  
  
 <span data-ttu-id="bb3bb-118">此接口的自定义实现必须返回包含 `bstrSimpleName` 参数中名为的类型库的完整路径的[BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) 。</span><span class="sxs-lookup"><span data-stu-id="bb3bb-118">Custom implementations of this interface must return a [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) that contains the full path of the type library named in the `bstrSimpleName` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb3bb-119">要求</span><span class="sxs-lookup"><span data-stu-id="bb3bb-119">Requirements</span></span>  
 <span data-ttu-id="bb3bb-120">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="bb3bb-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb3bb-121">**标头：** TlbRef，TlbRef</span><span class="sxs-lookup"><span data-stu-id="bb3bb-121">**Header:** TlbRef.idl, TlbRef.h</span></span>  
  
 <span data-ttu-id="bb3bb-122">**库：** TlbRef</span><span class="sxs-lookup"><span data-stu-id="bb3bb-122">**Library:** TlbRef.lib</span></span>  
  
 <span data-ttu-id="bb3bb-123">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb3bb-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb3bb-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="bb3bb-124">See also</span></span>

- [<span data-ttu-id="bb3bb-125">Tlbexp Helper 函数</span><span class="sxs-lookup"><span data-stu-id="bb3bb-125">Tlbexp Helper Functions</span></span>](index.md)
- [<span data-ttu-id="bb3bb-126">LoadTypeLibEx</span><span class="sxs-lookup"><span data-stu-id="bb3bb-126">LoadTypeLibEx</span></span>](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)
