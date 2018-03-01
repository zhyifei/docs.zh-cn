---
title: "LoadTypeLibWithResolver 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- LoadTypeLibWithResolver
api_location:
- TlbRef.dll
api_type:
- DLLExport
f1_keywords:
- LoadTypeLibWithResolver
helpviewer_keywords:
- LoadTypeLibWithResolver function [.NET Framework]
ms.assetid: 7123a89b-eb9b-463a-a552-a081e33b0a3a
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f069d09f25575c39db097024384ad1bf14eaaf02
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="loadtypelibwithresolver-function"></a><span data-ttu-id="e1b97-102">LoadTypeLibWithResolver 函数</span><span class="sxs-lookup"><span data-stu-id="e1b97-102">LoadTypeLibWithResolver Function</span></span>
<span data-ttu-id="e1b97-103">加载类型库中并使用所提供[ITypeLibResolver 接口](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md)若要解决任何内部引用的类型库。</span><span class="sxs-lookup"><span data-stu-id="e1b97-103">Loads a type library and uses the supplied [ITypeLibResolver interface](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) to resolve any internally referenced type libraries.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1b97-104">语法</span><span class="sxs-lookup"><span data-stu-id="e1b97-104">Syntax</span></span>  
  
```  
HRESULT LoadTypeLibWithResolver(  
    [in]  LPCOLESTR           szFile,  
    [in]  REGKIND             regkind,  
    [in]  ITypeLibResolver   *pTlbResolver,  
    [out] ITypeLib          **pptlib);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e1b97-105">参数</span><span class="sxs-lookup"><span data-stu-id="e1b97-105">Parameters</span></span>  
 `szFile`  
 <span data-ttu-id="e1b97-106">[in]类型库文件路径。</span><span class="sxs-lookup"><span data-stu-id="e1b97-106">[in] The file path of the type library.</span></span>  
  
 `regkind`  
 <span data-ttu-id="e1b97-107">[in]A [REGKIND 枚举](https://msdn.microsoft.com/library/windows/desktop/ms221159.aspx)控制如何注册类型库的标志。</span><span class="sxs-lookup"><span data-stu-id="e1b97-107">[in] A [REGKIND enumeration](https://msdn.microsoft.com/library/windows/desktop/ms221159.aspx) flag that controls how the type library is registered.</span></span> <span data-ttu-id="e1b97-108">其可能的值有：</span><span class="sxs-lookup"><span data-stu-id="e1b97-108">Its possible values are:</span></span>  
  
-   <span data-ttu-id="e1b97-109">`REGKIND_DEFAULT`： 使用默认注册行为。</span><span class="sxs-lookup"><span data-stu-id="e1b97-109">`REGKIND_DEFAULT`: Use default registration behavior.</span></span>  
  
-   <span data-ttu-id="e1b97-110">`REGKIND_REGISTER`： 注册此类型库。</span><span class="sxs-lookup"><span data-stu-id="e1b97-110">`REGKIND_REGISTER`: Register this type library.</span></span>  
  
-   <span data-ttu-id="e1b97-111">`REGKIND_NONE`： 请勿注册此类型库。</span><span class="sxs-lookup"><span data-stu-id="e1b97-111">`REGKIND_NONE`: Do not register this type library.</span></span>  
  
 `pTlbResolver`  
 <span data-ttu-id="e1b97-112">[in]指向的实现的[ITypeLibResolver 接口](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md)。</span><span class="sxs-lookup"><span data-stu-id="e1b97-112">[in] A pointer to the implementation of the [ITypeLibResolver interface](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md).</span></span>  
  
 `pptlib`  
 <span data-ttu-id="e1b97-113">[out]对正在加载的类型库的引用。</span><span class="sxs-lookup"><span data-stu-id="e1b97-113">[out] A reference to the type library that is being loaded.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e1b97-114">返回值</span><span class="sxs-lookup"><span data-stu-id="e1b97-114">Return Value</span></span>  
 <span data-ttu-id="e1b97-115">下表中列出的 HRESULT 值之一。</span><span class="sxs-lookup"><span data-stu-id="e1b97-115">One of the HRESULT values listed in the following table.</span></span>  
  
|<span data-ttu-id="e1b97-116">返回值</span><span class="sxs-lookup"><span data-stu-id="e1b97-116">Return value</span></span>|<span data-ttu-id="e1b97-117">含义</span><span class="sxs-lookup"><span data-stu-id="e1b97-117">Meaning</span></span>|  
|------------------|-------------|  
|`S_OK`|<span data-ttu-id="e1b97-118">成功。</span><span class="sxs-lookup"><span data-stu-id="e1b97-118">Success.</span></span>|  
|`E_OUTOFMEMORY`|<span data-ttu-id="e1b97-119">内存不足。</span><span class="sxs-lookup"><span data-stu-id="e1b97-119">Out of memory.</span></span>|  
|`E_POINTER`|<span data-ttu-id="e1b97-120">一个或多个指针均无效。</span><span class="sxs-lookup"><span data-stu-id="e1b97-120">One or more of the pointers are invalid.</span></span>|  
|`E_INVALIDARG`|<span data-ttu-id="e1b97-121">无效的一个或多个参数。</span><span class="sxs-lookup"><span data-stu-id="e1b97-121">One or more of the arguments are invalid.</span></span>|  
|`TYPE_E_IOERROR`|<span data-ttu-id="e1b97-122">函数无法写入到文件中。</span><span class="sxs-lookup"><span data-stu-id="e1b97-122">The function could not write to the file.</span></span>|  
|`TYPE_E_REGISTRYACCESS`|<span data-ttu-id="e1b97-123">无法打开系统注册数据库。</span><span class="sxs-lookup"><span data-stu-id="e1b97-123">The system registration database could not be opened.</span></span>|  
|`TYPE_E_INVALIDSTATE`|<span data-ttu-id="e1b97-124">无法打开类型库。</span><span class="sxs-lookup"><span data-stu-id="e1b97-124">The type library could not be opened.</span></span>|  
|`TYPE_E_CANTLOADLIBRARY`|<span data-ttu-id="e1b97-125">无法加载类型库或 DLL。</span><span class="sxs-lookup"><span data-stu-id="e1b97-125">The type library or DLL could not be loaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e1b97-126">备注</span><span class="sxs-lookup"><span data-stu-id="e1b97-126">Remarks</span></span>  
 <span data-ttu-id="e1b97-127">[Tlbexp.exe （类型库导出程序）](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md)调用`LoadTypeLibWithResolver`在程序集到类型库转换过程中的函数。</span><span class="sxs-lookup"><span data-stu-id="e1b97-127">The [Tlbexp.exe (Type Library Exporter)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) calls the `LoadTypeLibWithResolver` function during the assembly-to-type-library conversion process.</span></span>  
  
 <span data-ttu-id="e1b97-128">此函数将加载指定的类型库具有对注册表的最低访问权限。</span><span class="sxs-lookup"><span data-stu-id="e1b97-128">This function loads the specified type library with minimal access to the registry.</span></span> <span data-ttu-id="e1b97-129">然后，该函数将检查内部引用的类型库，其中每个必须加载和添加到父类型库的类型库。</span><span class="sxs-lookup"><span data-stu-id="e1b97-129">The function then examines the type library for internally referenced type libraries, each of which must be loaded and added to the parent type library.</span></span>  
  
 <span data-ttu-id="e1b97-130">可以加载引用的类型库之前，其引用文件路径必须解析为完整文件路径。</span><span class="sxs-lookup"><span data-stu-id="e1b97-130">Before a referenced type library can be loaded, its reference file path must be resolved to a full file path.</span></span> <span data-ttu-id="e1b97-131">这通过实现[ResolveTypeLib 方法](../../../../docs/framework/unmanaged-api/tlbexp/resolvetypelib-method.md)由提供[ITypeLibResolver 接口](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md)，后者在传递`pTlbResolver`参数。</span><span class="sxs-lookup"><span data-stu-id="e1b97-131">This is accomplished through the [ResolveTypeLib method](../../../../docs/framework/unmanaged-api/tlbexp/resolvetypelib-method.md) that is provided by the [ITypeLibResolver interface](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md), which is passed in the `pTlbResolver` parameter.</span></span>  
  
 <span data-ttu-id="e1b97-132">当已知的引用的类型库的完整文件路径时，`LoadTypeLibWithResolver`函数加载，并将引用的类型库添加到父类型库中，创建合并的主类型库。</span><span class="sxs-lookup"><span data-stu-id="e1b97-132">When the full file path of the referenced type library is known, the `LoadTypeLibWithResolver` function loads and adds the referenced type library to the parent type library, creating a combined master type library.</span></span>  
  
 <span data-ttu-id="e1b97-133">该函数解析并加载了所有内部引用的类型库后，它将返回到主解析的类型库中的引用`pptlib`参数。</span><span class="sxs-lookup"><span data-stu-id="e1b97-133">After the function resolves and loads all internally referenced type libraries, it returns a reference to the master resolved type library in the `pptlib` parameter.</span></span>  
  
 <span data-ttu-id="e1b97-134">`LoadTypeLibWithResolver`函数通常由[Tlbexp.exe （类型库导出程序）](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md)，其中提供其自身内部[ITypeLibResolver 接口](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md)中的实现`pTlbResolver`参数。</span><span class="sxs-lookup"><span data-stu-id="e1b97-134">The `LoadTypeLibWithResolver` function is generally called by the [Tlbexp.exe (Type Library Exporter)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md), which supplies its own internal [ITypeLibResolver interface](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) implementation in the `pTlbResolver` parameter.</span></span>  
  
 <span data-ttu-id="e1b97-135">如果调用`LoadTypeLibWithResolver`直接，则必须提供你自己[ITypeLibResolver 接口](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md)实现。</span><span class="sxs-lookup"><span data-stu-id="e1b97-135">If you call `LoadTypeLibWithResolver` directly, you must supply your own [ITypeLibResolver interface](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) implementation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e1b97-136">惠?</span><span class="sxs-lookup"><span data-stu-id="e1b97-136">Requirements</span></span>  
 <span data-ttu-id="e1b97-137">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e1b97-137">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1b97-138">**标头：** TlbRef.h</span><span class="sxs-lookup"><span data-stu-id="e1b97-138">**Header:** TlbRef.h</span></span>  
  
 <span data-ttu-id="e1b97-139">**库：** TlbRef.lib</span><span class="sxs-lookup"><span data-stu-id="e1b97-139">**Library:** TlbRef.lib</span></span>  
  
 <span data-ttu-id="e1b97-140">**.NET framework 版本：** 3.5、 3.0、 2.0</span><span class="sxs-lookup"><span data-stu-id="e1b97-140">**.NET Framework Version:** 3.5, 3.0, 2.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1b97-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="e1b97-141">See Also</span></span>  
 [<span data-ttu-id="e1b97-142">Tlbexp Helper 函数</span><span class="sxs-lookup"><span data-stu-id="e1b97-142">Tlbexp Helper Functions</span></span>](../../../../docs/framework/unmanaged-api/tlbexp/index.md)  
 <span data-ttu-id="e1b97-143">[LoadTypeLibEx 函数](https://msdn.microsoft.com/library/windows/desktop/ms221249\(v=vs.85\).aspx)</span><span class="sxs-lookup"><span data-stu-id="e1b97-143">[LoadTypeLibEx Function](https://msdn.microsoft.com/library/windows/desktop/ms221249\(v=vs.85\).aspx)</span></span>
