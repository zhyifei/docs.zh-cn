---
title: LoadTypeLibWithResolver 函数
ms.date: 03/30/2017
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
ms.openlocfilehash: adbb5eca3b7ffa36d0c963d0dacc3b2afdb664d4
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/14/2020
ms.locfileid: "75935565"
---
# <a name="loadtypelibwithresolver-function"></a><span data-ttu-id="735cc-102">LoadTypeLibWithResolver 函数</span><span class="sxs-lookup"><span data-stu-id="735cc-102">LoadTypeLibWithResolver Function</span></span>
<span data-ttu-id="735cc-103">加载类型库，并使用提供的[ITypeLibResolver 接口](itypelibresolver-interface.md)解析任何内部引用的类型库。</span><span class="sxs-lookup"><span data-stu-id="735cc-103">Loads a type library and uses the supplied [ITypeLibResolver interface](itypelibresolver-interface.md) to resolve any internally referenced type libraries.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="735cc-104">语法</span><span class="sxs-lookup"><span data-stu-id="735cc-104">Syntax</span></span>  
  
```cpp  
HRESULT LoadTypeLibWithResolver(  
    [in]  LPCOLESTR           szFile,  
    [in]  REGKIND             regkind,  
    [in]  ITypeLibResolver   *pTlbResolver,  
    [out] ITypeLib          **pptlib);  
```  
  
## <a name="parameters"></a><span data-ttu-id="735cc-105">参数</span><span class="sxs-lookup"><span data-stu-id="735cc-105">Parameters</span></span>  
 `szFile`  
 <span data-ttu-id="735cc-106">中类型库的文件路径。</span><span class="sxs-lookup"><span data-stu-id="735cc-106">[in] The file path of the type library.</span></span>  
  
 `regkind`  
 <span data-ttu-id="735cc-107">中用于控制如何注册类型库的[REGKIND 枚举](/windows/win32/api/oleauto/ne-oleauto-regkind)标志。</span><span class="sxs-lookup"><span data-stu-id="735cc-107">[in] A [REGKIND enumeration](/windows/win32/api/oleauto/ne-oleauto-regkind) flag that controls how the type library is registered.</span></span> <span data-ttu-id="735cc-108">其可能的值为：</span><span class="sxs-lookup"><span data-stu-id="735cc-108">Its possible values are:</span></span>  
  
- <span data-ttu-id="735cc-109">`REGKIND_DEFAULT`：使用默认注册行为。</span><span class="sxs-lookup"><span data-stu-id="735cc-109">`REGKIND_DEFAULT`: Use default registration behavior.</span></span>  
  
- <span data-ttu-id="735cc-110">`REGKIND_REGISTER`：注册此类型库。</span><span class="sxs-lookup"><span data-stu-id="735cc-110">`REGKIND_REGISTER`: Register this type library.</span></span>  
  
- <span data-ttu-id="735cc-111">`REGKIND_NONE`：不注册此类型库。</span><span class="sxs-lookup"><span data-stu-id="735cc-111">`REGKIND_NONE`: Do not register this type library.</span></span>  
  
 `pTlbResolver`  
 <span data-ttu-id="735cc-112">中指向[ITypeLibResolver 接口](itypelibresolver-interface.md)的实现的指针。</span><span class="sxs-lookup"><span data-stu-id="735cc-112">[in] A pointer to the implementation of the [ITypeLibResolver interface](itypelibresolver-interface.md).</span></span>  
  
 `pptlib`  
 <span data-ttu-id="735cc-113">弄对正在加载的类型库的引用。</span><span class="sxs-lookup"><span data-stu-id="735cc-113">[out] A reference to the type library that is being loaded.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="735cc-114">返回值</span><span class="sxs-lookup"><span data-stu-id="735cc-114">Return Value</span></span>  
 <span data-ttu-id="735cc-115">下表中列出的其中一个 HRESULT 值。</span><span class="sxs-lookup"><span data-stu-id="735cc-115">One of the HRESULT values listed in the following table.</span></span>  
  
|<span data-ttu-id="735cc-116">返回值</span><span class="sxs-lookup"><span data-stu-id="735cc-116">Return value</span></span>|<span data-ttu-id="735cc-117">含义</span><span class="sxs-lookup"><span data-stu-id="735cc-117">Meaning</span></span>|  
|------------------|-------------|  
|`S_OK`|<span data-ttu-id="735cc-118">成功。</span><span class="sxs-lookup"><span data-stu-id="735cc-118">Success.</span></span>|  
|`E_OUTOFMEMORY`|<span data-ttu-id="735cc-119">内存不足。</span><span class="sxs-lookup"><span data-stu-id="735cc-119">Out of memory.</span></span>|  
|`E_POINTER`|<span data-ttu-id="735cc-120">一个或多个指针无效。</span><span class="sxs-lookup"><span data-stu-id="735cc-120">One or more of the pointers are invalid.</span></span>|  
|`E_INVALIDARG`|<span data-ttu-id="735cc-121">一个或多个参数无效。</span><span class="sxs-lookup"><span data-stu-id="735cc-121">One or more of the arguments are invalid.</span></span>|  
|`TYPE_E_IOERROR`|<span data-ttu-id="735cc-122">函数无法写入文件。</span><span class="sxs-lookup"><span data-stu-id="735cc-122">The function could not write to the file.</span></span>|  
|`TYPE_E_REGISTRYACCESS`|<span data-ttu-id="735cc-123">无法打开系统注册数据库。</span><span class="sxs-lookup"><span data-stu-id="735cc-123">The system registration database could not be opened.</span></span>|  
|`TYPE_E_INVALIDSTATE`|<span data-ttu-id="735cc-124">无法打开类型库。</span><span class="sxs-lookup"><span data-stu-id="735cc-124">The type library could not be opened.</span></span>|  
|`TYPE_E_CANTLOADLIBRARY`|<span data-ttu-id="735cc-125">未能加载类型库或 DLL。</span><span class="sxs-lookup"><span data-stu-id="735cc-125">The type library or DLL could not be loaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="735cc-126">备注</span><span class="sxs-lookup"><span data-stu-id="735cc-126">Remarks</span></span>  
 <span data-ttu-id="735cc-127">[Tlbexp.exe （类型库导出程序）](../../tools/tlbexp-exe-type-library-exporter.md)在程序集到类型库转换过程中调用 `LoadTypeLibWithResolver` 函数。</span><span class="sxs-lookup"><span data-stu-id="735cc-127">The [Tlbexp.exe (Type Library Exporter)](../../tools/tlbexp-exe-type-library-exporter.md) calls the `LoadTypeLibWithResolver` function during the assembly-to-type-library conversion process.</span></span>  
  
 <span data-ttu-id="735cc-128">此函数加载指定的类型库，并对注册表的访问权限降至最低。</span><span class="sxs-lookup"><span data-stu-id="735cc-128">This function loads the specified type library with minimal access to the registry.</span></span> <span data-ttu-id="735cc-129">然后，该函数检查类型库以查找内部引用的类型库，其中每个库必须加载并添加到父类型库中。</span><span class="sxs-lookup"><span data-stu-id="735cc-129">The function then examines the type library for internally referenced type libraries, each of which must be loaded and added to the parent type library.</span></span>  
  
 <span data-ttu-id="735cc-130">在可以加载引用的类型库之前，必须将其引用文件路径解析为完整文件路径。</span><span class="sxs-lookup"><span data-stu-id="735cc-130">Before a referenced type library can be loaded, its reference file path must be resolved to a full file path.</span></span> <span data-ttu-id="735cc-131">这是通过[ITypeLibResolver 接口](itypelibresolver-interface.md)提供的[ResolveTypeLib 方法](resolvetypelib-method.md)实现的，该方法在 `pTlbResolver` 参数中传递。</span><span class="sxs-lookup"><span data-stu-id="735cc-131">This is accomplished through the [ResolveTypeLib method](resolvetypelib-method.md) that is provided by the [ITypeLibResolver interface](itypelibresolver-interface.md), which is passed in the `pTlbResolver` parameter.</span></span>  
  
 <span data-ttu-id="735cc-132">当所引用的类型库的完整文件路径已知时，`LoadTypeLibWithResolver` 函数将加载引用的类型库并将其添加到父类型库，从而创建组合的主类型库。</span><span class="sxs-lookup"><span data-stu-id="735cc-132">When the full file path of the referenced type library is known, the `LoadTypeLibWithResolver` function loads and adds the referenced type library to the parent type library, creating a combined master type library.</span></span>  
  
 <span data-ttu-id="735cc-133">函数解析并加载所有内部引用的类型库后，它会在 `pptlib` 参数中返回对主解析类型库的引用。</span><span class="sxs-lookup"><span data-stu-id="735cc-133">After the function resolves and loads all internally referenced type libraries, it returns a reference to the master resolved type library in the `pptlib` parameter.</span></span>  
  
 <span data-ttu-id="735cc-134">`LoadTypeLibWithResolver` 函数通常由[tlbexp.exe （类型库导出程序）](../../tools/tlbexp-exe-type-library-exporter.md)调用，它在 `pTlbResolver` 参数中提供自己的内部[ITypeLibResolver 接口](itypelibresolver-interface.md)实现。</span><span class="sxs-lookup"><span data-stu-id="735cc-134">The `LoadTypeLibWithResolver` function is generally called by the [Tlbexp.exe (Type Library Exporter)](../../tools/tlbexp-exe-type-library-exporter.md), which supplies its own internal [ITypeLibResolver interface](itypelibresolver-interface.md) implementation in the `pTlbResolver` parameter.</span></span>  
  
 <span data-ttu-id="735cc-135">如果直接调用 `LoadTypeLibWithResolver`，则必须提供自己的[ITypeLibResolver 接口](itypelibresolver-interface.md)实现。</span><span class="sxs-lookup"><span data-stu-id="735cc-135">If you call `LoadTypeLibWithResolver` directly, you must supply your own [ITypeLibResolver interface](itypelibresolver-interface.md) implementation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="735cc-136">需求</span><span class="sxs-lookup"><span data-stu-id="735cc-136">Requirements</span></span>  
 <span data-ttu-id="735cc-137">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="735cc-137">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="735cc-138">**标头：** TlbRef</span><span class="sxs-lookup"><span data-stu-id="735cc-138">**Header:** TlbRef.h</span></span>  
  
 <span data-ttu-id="735cc-139">**库：** TlbRef</span><span class="sxs-lookup"><span data-stu-id="735cc-139">**Library:** TlbRef.lib</span></span>  
  
 <span data-ttu-id="735cc-140">**.NET Framework 版本：** 3.5、3.0、2.0</span><span class="sxs-lookup"><span data-stu-id="735cc-140">**.NET Framework Version:** 3.5, 3.0, 2.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="735cc-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="735cc-141">See also</span></span>

- [<span data-ttu-id="735cc-142">Tlbexp Helper 函数</span><span class="sxs-lookup"><span data-stu-id="735cc-142">Tlbexp Helper Functions</span></span>](index.md)
- [<span data-ttu-id="735cc-143">LoadTypeLibEx 函数</span><span class="sxs-lookup"><span data-stu-id="735cc-143">LoadTypeLibEx Function</span></span>](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)
