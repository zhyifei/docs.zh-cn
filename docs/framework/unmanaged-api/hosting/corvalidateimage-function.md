---
title: _CorValidateImage 函数
ms.date: 03/30/2017
api_name:
- _CorValidateImage
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- _CorValidateImage
helpviewer_keywords:
- _CorValidateImage function [.NET Framework hosting]
ms.assetid: 0117e080-05f9-4772-885d-e1847230947c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a84869281ec27aface96d722603186382c6e15e7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54730771"
---
# <a name="corvalidateimage-function"></a><span data-ttu-id="f816a-102">_CorValidateImage 函数</span><span class="sxs-lookup"><span data-stu-id="f816a-102">_CorValidateImage Function</span></span>
<span data-ttu-id="f816a-103">验证托管的模块映像，并已加载后通知操作系统加载程序。</span><span class="sxs-lookup"><span data-stu-id="f816a-103">Validates managed module images, and notifies the operating system loader after they have been loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f816a-104">语法</span><span class="sxs-lookup"><span data-stu-id="f816a-104">Syntax</span></span>  
  
```  
STDAPI _CorValidateImage (   
   [in] PVOID* ImageBase,  
   [in] LPCWSTR FileName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f816a-105">参数</span><span class="sxs-lookup"><span data-stu-id="f816a-105">Parameters</span></span>  
 `ImageBase`  
 <span data-ttu-id="f816a-106">[in]指向要作为验证的图像的起始位置的托管代码。</span><span class="sxs-lookup"><span data-stu-id="f816a-106">[in] A pointer to the starting location of the image to validate as managed code.</span></span> <span data-ttu-id="f816a-107">该映像必须已加载到内存中。</span><span class="sxs-lookup"><span data-stu-id="f816a-107">The image must already be loaded into memory.</span></span>  
  
 `FileName`  
 <span data-ttu-id="f816a-108">[in]图像的文件名。</span><span class="sxs-lookup"><span data-stu-id="f816a-108">[in] The file name of the image.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f816a-109">返回值</span><span class="sxs-lookup"><span data-stu-id="f816a-109">Return Value</span></span>  
 <span data-ttu-id="f816a-110">此函数返回的标准值`E_INVALIDARG`， `E_OUTOFMEMORY`， `E_UNEXPECTED`，和`E_FAIL`，以及以下值。</span><span class="sxs-lookup"><span data-stu-id="f816a-110">This function returns the standard values `E_INVALIDARG`, `E_OUTOFMEMORY`, `E_UNEXPECTED`, and `E_FAIL`, as well as the following values.</span></span>  
  
|<span data-ttu-id="f816a-111">返回值</span><span class="sxs-lookup"><span data-stu-id="f816a-111">Return value</span></span>|<span data-ttu-id="f816a-112">描述</span><span class="sxs-lookup"><span data-stu-id="f816a-112">Description</span></span>|  
|------------------|-----------------|  
|`STATUS_INVALID_IMAGE_FORMAT`|<span data-ttu-id="f816a-113">映像是无效的。</span><span class="sxs-lookup"><span data-stu-id="f816a-113">The image is invalid.</span></span> <span data-ttu-id="f816a-114">此值具有 HRESULT 0xC000007BL。</span><span class="sxs-lookup"><span data-stu-id="f816a-114">This value has the HRESULT 0xC000007BL.</span></span>|  
|`STATUS_SUCCESS`|<span data-ttu-id="f816a-115">映像是有效的。</span><span class="sxs-lookup"><span data-stu-id="f816a-115">The image is valid.</span></span> <span data-ttu-id="f816a-116">此值具有 HRESULT 0x00000000L。</span><span class="sxs-lookup"><span data-stu-id="f816a-116">This value has the HRESULT 0x00000000L.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f816a-117">备注</span><span class="sxs-lookup"><span data-stu-id="f816a-117">Remarks</span></span>  
 <span data-ttu-id="f816a-118">在 Windows XP 和更高版本中，操作系统加载程序通过检查通用对象文件格式 (COFF) 标头中的 COM 描述符目录位检查托管模块。</span><span class="sxs-lookup"><span data-stu-id="f816a-118">In Windows XP and later versions, the operating system loader checks for managed modules by examining the COM Descriptor Directory bit in the common object file format (COFF) header.</span></span> <span data-ttu-id="f816a-119">一个设置位指示托管的模块。</span><span class="sxs-lookup"><span data-stu-id="f816a-119">A set bit indicates a managed module.</span></span> <span data-ttu-id="f816a-120">如果加载程序检测到托管的模块时，它将加载 MsCorEE.dll 并调用`_CorValidateImage`，该文件将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="f816a-120">If the loader detects a managed module, it loads MsCorEE.dll and calls `_CorValidateImage`, which performs the following actions:</span></span>  
  
-   <span data-ttu-id="f816a-121">确认该图像是有效的托管的模块。</span><span class="sxs-lookup"><span data-stu-id="f816a-121">Confirms that the image is a valid managed module.</span></span>  
  
-   <span data-ttu-id="f816a-122">在图中的入口点更改为公共语言运行时 (CLR) 中的入口点。</span><span class="sxs-lookup"><span data-stu-id="f816a-122">Changes the entry point in the image to an entry point in the common language runtime (CLR).</span></span>  
  
-   <span data-ttu-id="f816a-123">对于 64 位版本的 Windows，修改在内存中是通过将其从 PE32 转换为 PE32 + 格式的图像。</span><span class="sxs-lookup"><span data-stu-id="f816a-123">For 64-bit versions of Windows, modifies the image that is in memory by transforming it from PE32 to PE32+ format.</span></span>  
  
-   <span data-ttu-id="f816a-124">返回到加载程序加载托管的模块映像时。</span><span class="sxs-lookup"><span data-stu-id="f816a-124">Returns to the loader when the managed module images are loaded.</span></span>  
  
 <span data-ttu-id="f816a-125">对于可执行映像，操作系统加载程序然后调用[_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md)函数，而不考虑可执行文件中指定的入口点。</span><span class="sxs-lookup"><span data-stu-id="f816a-125">For executable images, the operating system loader then calls the [_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) function, regardless of the entry point specified in the executable.</span></span> <span data-ttu-id="f816a-126">对于 DLL 程序集图像加载程序调用[_CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md)函数。</span><span class="sxs-lookup"><span data-stu-id="f816a-126">For DLL assembly images, the loader calls the [_CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md) function.</span></span>  
  
 <span data-ttu-id="f816a-127">`_CorExeMain` 或`_CorDllMain`将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="f816a-127">`_CorExeMain` or `_CorDllMain` performs the following actions:</span></span>  
  
-   <span data-ttu-id="f816a-128">初始化 CLR。</span><span class="sxs-lookup"><span data-stu-id="f816a-128">Initializes the CLR.</span></span>  
  
-   <span data-ttu-id="f816a-129">查找程序集的 CLR 标头中的托管的入口点。</span><span class="sxs-lookup"><span data-stu-id="f816a-129">Locates the managed entry point from the assembly's CLR header.</span></span>  
  
-   <span data-ttu-id="f816a-130">开始执行。</span><span class="sxs-lookup"><span data-stu-id="f816a-130">Begins execution.</span></span>  
  
 <span data-ttu-id="f816a-131">加载程序调用[_CorImageUnloading](../../../../docs/framework/unmanaged-api/hosting/corimageunloading-function.md)函数时托管模块映像都会被卸载。</span><span class="sxs-lookup"><span data-stu-id="f816a-131">The loader calls the [_CorImageUnloading](../../../../docs/framework/unmanaged-api/hosting/corimageunloading-function.md) function when managed module images are unloaded.</span></span> <span data-ttu-id="f816a-132">但是，此函数不执行任何操作;它只是返回。</span><span class="sxs-lookup"><span data-stu-id="f816a-132">However, this function does not perform any action; it just returns.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f816a-133">要求</span><span class="sxs-lookup"><span data-stu-id="f816a-133">Requirements</span></span>  
 <span data-ttu-id="f816a-134">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f816a-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f816a-135">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f816a-135">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f816a-136">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="f816a-136">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f816a-137">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f816a-137">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f816a-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="f816a-138">See also</span></span>
- [<span data-ttu-id="f816a-139">元数据全局静态函数</span><span class="sxs-lookup"><span data-stu-id="f816a-139">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
