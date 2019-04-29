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
ms.openlocfilehash: b7407db297a827004c851b904b2da8652778cb08
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61756411"
---
# <a name="corexemain-function"></a><span data-ttu-id="e3aaf-102">_CorExeMain 函数</span><span class="sxs-lookup"><span data-stu-id="e3aaf-102">_CorExeMain Function</span></span>
<span data-ttu-id="e3aaf-103">初始化公共语言运行时 (CLR) 中，查找托管的入口点的可执行程序集 CLR 头中，并开始执行。</span><span class="sxs-lookup"><span data-stu-id="e3aaf-103">Initializes the common language runtime (CLR), locates the managed entry point in the executable assembly's CLR header, and begins execution.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3aaf-104">语法</span><span class="sxs-lookup"><span data-stu-id="e3aaf-104">Syntax</span></span>  
  
```  
__int32 STDMETHODCALLTYPE _CorExeMain ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="e3aaf-105">备注</span><span class="sxs-lookup"><span data-stu-id="e3aaf-105">Remarks</span></span>  
 <span data-ttu-id="e3aaf-106">从托管的可执行程序集创建的进程中加载程序调用此函数。</span><span class="sxs-lookup"><span data-stu-id="e3aaf-106">This function is called by the loader in processes created from managed executable assemblies.</span></span> <span data-ttu-id="e3aaf-107">对于 DLL 程序集加载程序调用[_CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md)函数。</span><span class="sxs-lookup"><span data-stu-id="e3aaf-107">For DLL assemblies, the loader calls the [_CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md) function instead.</span></span>  
  
 <span data-ttu-id="e3aaf-108">操作系统加载程序调用此方法而不考虑图像文件中指定的入口点。</span><span class="sxs-lookup"><span data-stu-id="e3aaf-108">The operating system loader calls this method regardless of the entry point specified in the image file.</span></span>  
  
 <span data-ttu-id="e3aaf-109">在 Windows 98、 Windows ME、 Windows NT 和 Windows 2000`_CorExeMain`通过操作系统加载程序中的修正间接调用函数。</span><span class="sxs-lookup"><span data-stu-id="e3aaf-109">In Windows 98, Windows ME, Windows NT, and Windows 2000, the `_CorExeMain` function is called indirectly through a fixup in the operating system loader.</span></span> <span data-ttu-id="e3aaf-110">在所有其他版本的 Windows，它是由操作系统加载程序直接进行调用。</span><span class="sxs-lookup"><span data-stu-id="e3aaf-110">In all other versions of Windows, it is called directly by the operating system loader.</span></span>  
  
 <span data-ttu-id="e3aaf-111">有关其他信息，请参阅中的备注部分[_CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md)主题。</span><span class="sxs-lookup"><span data-stu-id="e3aaf-111">For additional information, see the Remarks section in the [_CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md) topic.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e3aaf-112">要求</span><span class="sxs-lookup"><span data-stu-id="e3aaf-112">Requirements</span></span>  
 <span data-ttu-id="e3aaf-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e3aaf-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e3aaf-114">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e3aaf-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e3aaf-115">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="e3aaf-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e3aaf-116">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e3aaf-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3aaf-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="e3aaf-117">See also</span></span>

- [<span data-ttu-id="e3aaf-118">元数据全局静态函数</span><span class="sxs-lookup"><span data-stu-id="e3aaf-118">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
