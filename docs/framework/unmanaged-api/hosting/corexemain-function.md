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
ms.openlocfilehash: 935ac478fb966315e81fdcc004761038b28e3178
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616583"
---
# <a name="_corexemain-function"></a><span data-ttu-id="6cc1f-102">_CorExeMain 函数</span><span class="sxs-lookup"><span data-stu-id="6cc1f-102">_CorExeMain Function</span></span>
<span data-ttu-id="6cc1f-103">初始化公共语言运行时（CLR），定位可执行程序集的 CLR 头中的托管入口点，然后开始执行。</span><span class="sxs-lookup"><span data-stu-id="6cc1f-103">Initializes the common language runtime (CLR), locates the managed entry point in the executable assembly's CLR header, and begins execution.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6cc1f-104">语法</span><span class="sxs-lookup"><span data-stu-id="6cc1f-104">Syntax</span></span>  
  
```cpp  
__int32 STDMETHODCALLTYPE _CorExeMain ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="6cc1f-105">备注</span><span class="sxs-lookup"><span data-stu-id="6cc1f-105">Remarks</span></span>  
 <span data-ttu-id="6cc1f-106">此函数由加载程序在从托管可执行程序集创建的进程中调用。</span><span class="sxs-lookup"><span data-stu-id="6cc1f-106">This function is called by the loader in processes created from managed executable assemblies.</span></span> <span data-ttu-id="6cc1f-107">对于 DLL 程序集，加载程序将改为调用[_CorDllMain](cordllmain-function.md)函数。</span><span class="sxs-lookup"><span data-stu-id="6cc1f-107">For DLL assemblies, the loader calls the [_CorDllMain](cordllmain-function.md) function instead.</span></span>  
  
 <span data-ttu-id="6cc1f-108">操作系统加载程序将调用此方法，而不考虑映像文件中指定的入口点。</span><span class="sxs-lookup"><span data-stu-id="6cc1f-108">The operating system loader calls this method regardless of the entry point specified in the image file.</span></span>  
  
 <span data-ttu-id="6cc1f-109">在 Windows 98、Windows ME、Windows NT 和 Windows 2000 中， `_CorExeMain` 通过操作系统加载程序中的修正间接调用该函数。</span><span class="sxs-lookup"><span data-stu-id="6cc1f-109">In Windows 98, Windows ME, Windows NT, and Windows 2000, the `_CorExeMain` function is called indirectly through a fixup in the operating system loader.</span></span> <span data-ttu-id="6cc1f-110">在所有其他版本的 Windows 中，操作系统加载程序直接调用它。</span><span class="sxs-lookup"><span data-stu-id="6cc1f-110">In all other versions of Windows, it is called directly by the operating system loader.</span></span>  
  
 <span data-ttu-id="6cc1f-111">有关其他信息，请参阅[_CorValidateImage](corvalidateimage-function.md)主题中的 "备注" 部分。</span><span class="sxs-lookup"><span data-stu-id="6cc1f-111">For additional information, see the Remarks section in the [_CorValidateImage](corvalidateimage-function.md) topic.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6cc1f-112">要求</span><span class="sxs-lookup"><span data-stu-id="6cc1f-112">Requirements</span></span>  
 <span data-ttu-id="6cc1f-113">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6cc1f-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6cc1f-114">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="6cc1f-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6cc1f-115">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="6cc1f-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6cc1f-116">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6cc1f-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6cc1f-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6cc1f-117">See also</span></span>

- [<span data-ttu-id="6cc1f-118">元数据全局静态函数</span><span class="sxs-lookup"><span data-stu-id="6cc1f-118">Metadata Global Static Functions</span></span>](../metadata/metadata-global-static-functions.md)
