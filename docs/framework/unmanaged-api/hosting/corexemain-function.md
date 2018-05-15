---
title: _CorExeMain 函数
ms.date: 03/30/2017
api_name:
- _CorExeMain
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- _CorExeMain
helpviewer_keywords:
- _CorExeMain function [.NET Framework hosting]
ms.assetid: 898f76e2-16f4-4a63-b7d9-dad2d3824d8a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 63af5979b113f81c01c9c68d6cccdfa10811265a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="corexemain-function"></a><span data-ttu-id="416c1-102">_CorExeMain 函数</span><span class="sxs-lookup"><span data-stu-id="416c1-102">_CorExeMain Function</span></span>
<span data-ttu-id="416c1-103">初始化公共语言运行时 (CLR)，查找可执行程序集的 CLR 标头中的托管的入口点并开始执行。</span><span class="sxs-lookup"><span data-stu-id="416c1-103">Initializes the common language runtime (CLR), locates the managed entry point in the executable assembly's CLR header, and begins execution.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="416c1-104">语法</span><span class="sxs-lookup"><span data-stu-id="416c1-104">Syntax</span></span>  
  
```  
__int32 STDMETHODCALLTYPE _CorExeMain ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="416c1-105">备注</span><span class="sxs-lookup"><span data-stu-id="416c1-105">Remarks</span></span>  
 <span data-ttu-id="416c1-106">从托管的可执行程序集创建的进程中加载程序调用此函数。</span><span class="sxs-lookup"><span data-stu-id="416c1-106">This function is called by the loader in processes created from managed executable assemblies.</span></span> <span data-ttu-id="416c1-107">对于 DLL 程序集，加载程序调用[_CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md)函数。</span><span class="sxs-lookup"><span data-stu-id="416c1-107">For DLL assemblies, the loader calls the [_CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md) function instead.</span></span>  
  
 <span data-ttu-id="416c1-108">操作系统加载程序调用此方法而不考虑图像文件中指定的入口点。</span><span class="sxs-lookup"><span data-stu-id="416c1-108">The operating system loader calls this method regardless of the entry point specified in the image file.</span></span>  
  
 <span data-ttu-id="416c1-109">在 Windows 98、 Windows ME、 Windows NT 和 Windows 2000`_CorExeMain`通过操作系统加载程序在修正间接调用函数。</span><span class="sxs-lookup"><span data-stu-id="416c1-109">In Windows 98, Windows ME, Windows NT, and Windows 2000, the `_CorExeMain` function is called indirectly through a fixup in the operating system loader.</span></span> <span data-ttu-id="416c1-110">在所有其他版本的 Windows，它是直接由操作系统加载程序进行调用。</span><span class="sxs-lookup"><span data-stu-id="416c1-110">In all other versions of Windows, it is called directly by the operating system loader.</span></span>  
  
 <span data-ttu-id="416c1-111">有关其他信息，请参阅备注部分中的[_CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md)主题。</span><span class="sxs-lookup"><span data-stu-id="416c1-111">For additional information, see the Remarks section in the [_CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md) topic.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="416c1-112">要求</span><span class="sxs-lookup"><span data-stu-id="416c1-112">Requirements</span></span>  
 <span data-ttu-id="416c1-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="416c1-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="416c1-114">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="416c1-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="416c1-115">**库：** 作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="416c1-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="416c1-116">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="416c1-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="416c1-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="416c1-117">See Also</span></span>  
 [<span data-ttu-id="416c1-118">元数据全局静态函数</span><span class="sxs-lookup"><span data-stu-id="416c1-118">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
