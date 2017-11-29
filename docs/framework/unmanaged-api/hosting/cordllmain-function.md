---
title: "_CorDllMain 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: _CorDllMain
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: _CorDllMain
helpviewer_keywords: _CorDllMain function [.NET Framework hosting]
ms.assetid: bc7b51cf-39d3-48ec-a5cb-2f179fbefff8
topic_type: apiref
caps.latest.revision: "23"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d2e4188f8b95141118e4bbb2df2a702ff04c2adf
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="cordllmain-function"></a><span data-ttu-id="fb7d0-102">_CorDllMain 函数</span><span class="sxs-lookup"><span data-stu-id="fb7d0-102">_CorDllMain Function</span></span>
<span data-ttu-id="fb7d0-103">初始化公共语言运行时 (CLR)、 查找托管的入口点 DLL 程序集的 CLR 头中，并开始执行。</span><span class="sxs-lookup"><span data-stu-id="fb7d0-103">Initializes the common language runtime (CLR), locates the managed entry point in the DLL assembly's CLR header, and begins execution.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb7d0-104">语法</span><span class="sxs-lookup"><span data-stu-id="fb7d0-104">Syntax</span></span>  
  
```  
BOOL STDMETHODCALLTYPE _CorDllMain (  
   [in] HINSTANCE hInst,  
   [in] DWORD     dwReason,  
   [in] LPVOID    lpReserved  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fb7d0-105">参数</span><span class="sxs-lookup"><span data-stu-id="fb7d0-105">Parameters</span></span>  
 `hInst`  
 <span data-ttu-id="fb7d0-106">[in]加载的模块的实例句柄。</span><span class="sxs-lookup"><span data-stu-id="fb7d0-106">[in] The instance handle of the loaded module.</span></span>  
  
 `dwReason`  
 <span data-ttu-id="fb7d0-107">[in]指示调用的 DLL 入口点函数。</span><span class="sxs-lookup"><span data-stu-id="fb7d0-107">[in]Indicates why the DLL entry-point function is being called.</span></span> <span data-ttu-id="fb7d0-108">此参数可以是以下值之一： DLL_PROCESS_ATTACH、 DLL_THREAD_ATTACH、 DLL_THREAD_ATTACH 或 DLL_PROCESS_DETACH。</span><span class="sxs-lookup"><span data-stu-id="fb7d0-108">This parameter can be one of the following values: DLL_PROCESS_ATTACH, DLL_THREAD_ATTACH, DLL_THREAD_ATTACH, or DLL_PROCESS_DETACH.</span></span> <span data-ttu-id="fb7d0-109">有关这些值的说明，请参阅`DllMain`平台 SDK 中的文档。</span><span class="sxs-lookup"><span data-stu-id="fb7d0-109">For descriptions of these values, see the `DllMain` documentation in the Platform SDK.</span></span>  
  
 `lpReserved`  
 <span data-ttu-id="fb7d0-110">[in]未使用。</span><span class="sxs-lookup"><span data-stu-id="fb7d0-110">[in] Unused.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fb7d0-111">返回值</span><span class="sxs-lookup"><span data-stu-id="fb7d0-111">Return Value</span></span>  
 <span data-ttu-id="fb7d0-112">此方法返回`true`成功和`false`如果发生错误。</span><span class="sxs-lookup"><span data-stu-id="fb7d0-112">This method returns `true` for success and `false` if an error occurs.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fb7d0-113">备注</span><span class="sxs-lookup"><span data-stu-id="fb7d0-113">Remarks</span></span>  
 <span data-ttu-id="fb7d0-114">为 DLL 程序集，操作系统加载程序调用此函数。</span><span class="sxs-lookup"><span data-stu-id="fb7d0-114">This function is called by the operating system loader for DLL assemblies.</span></span> <span data-ttu-id="fb7d0-115">对于可执行程序集，加载程序调用[_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md)函数。</span><span class="sxs-lookup"><span data-stu-id="fb7d0-115">For executable assemblies, the loader calls the [_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) function instead.</span></span>  
  
 <span data-ttu-id="fb7d0-116">操作系统加载程序调用此方法而不考虑 DLL 文件中指定的入口点。</span><span class="sxs-lookup"><span data-stu-id="fb7d0-116">The operating system loader calls this method regardless of the entry point specified in the DLL file.</span></span>  
  
 <span data-ttu-id="fb7d0-117">在 Windows 98、 Windows ME、 Windows NT 和 Windows 2000`_CorDllMain`通过调用函数间接 fixupin 操作系统加载程序。</span><span class="sxs-lookup"><span data-stu-id="fb7d0-117">In Windows 98, Windows ME, Windows NT, and Windows 2000, the `_CorDllMain` function is called indirectly through a fixupin the operating system loader.</span></span> <span data-ttu-id="fb7d0-118">在所有其他版本的 Windows，它是直接由操作系统加载程序进行调用。</span><span class="sxs-lookup"><span data-stu-id="fb7d0-118">In all other versions of Windows, it is called directly by the operating system loader.</span></span>  
  
 <span data-ttu-id="fb7d0-119">有关其他信息，请参阅备注部分中的[_CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md)主题。</span><span class="sxs-lookup"><span data-stu-id="fb7d0-119">For additional information, see the Remarks section in the [_CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md) topic.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb7d0-120">要求</span><span class="sxs-lookup"><span data-stu-id="fb7d0-120">Requirements</span></span>  
 <span data-ttu-id="fb7d0-121">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fb7d0-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb7d0-122">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="fb7d0-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fb7d0-123">**库：**作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="fb7d0-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fb7d0-124">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fb7d0-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb7d0-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fb7d0-125">See Also</span></span>  
 [<span data-ttu-id="fb7d0-126">元数据全局静态函数</span><span class="sxs-lookup"><span data-stu-id="fb7d0-126">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
