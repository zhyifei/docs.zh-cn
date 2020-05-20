---
title: _CorExeMain2 函数
ms.date: 03/30/2017
api_name:
- _CorExeMain2
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- _CorExeMain2
helpviewer_keywords:
- _CorExeMain2 function [.NET Framework hosting]
ms.assetid: 72ea68b4-689f-4733-9416-9664b75e8892
topic_type:
- apiref
ms.openlocfilehash: 8202fe4ec3ae6ef96440f203c5aea6db84744a72
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616575"
---
# <a name="_corexemain2-function"></a><span data-ttu-id="4a068-102">_CorExeMain2 函数</span><span class="sxs-lookup"><span data-stu-id="4a068-102">_CorExeMain2 Function</span></span>
<span data-ttu-id="4a068-103">执行指定的内存映射代码中的入口点。</span><span class="sxs-lookup"><span data-stu-id="4a068-103">Executes the entry point in the specified memory-mapped code.</span></span> <span data-ttu-id="4a068-104">此函数由操作系统加载程序调用。</span><span class="sxs-lookup"><span data-stu-id="4a068-104">This function is called by the operating system loader.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a068-105">语法</span><span class="sxs-lookup"><span data-stu-id="4a068-105">Syntax</span></span>  
  
```cpp  
__int32 STDMETHODCALLTYPE _CorExeMain2 (  
   [in] PBYTE           pUnmappedPE,  
   [in] DWORD           cUnmappedPE,  
   [in] __in LPWSTR     pImageNameIn,  
   [in] __in LPWSTR     pLoadersFileName,  
   [in] __in LPWSTR     pCmdLine  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4a068-106">参数</span><span class="sxs-lookup"><span data-stu-id="4a068-106">Parameters</span></span>  
 `pUnmappedPE`  
 <span data-ttu-id="4a068-107">中指向内存映射代码的指针。</span><span class="sxs-lookup"><span data-stu-id="4a068-107">[in] A pointer to the memory-mapped code.</span></span>  
  
 `cUnmappedPE`  
 <span data-ttu-id="4a068-108">中可以容纳的元素数 `pUnmappedPE` 。</span><span class="sxs-lookup"><span data-stu-id="4a068-108">[in] The number of elements `pUnmappedPE` can hold.</span></span>  
  
 `pImageNameIn`  
 <span data-ttu-id="4a068-109">中指向可执行图像的名称的指针。</span><span class="sxs-lookup"><span data-stu-id="4a068-109">[in] A pointer to the name of the executable image.</span></span>  
  
 `pLoadersFileName`  
 <span data-ttu-id="4a068-110">中加载程序文件的名称。</span><span class="sxs-lookup"><span data-stu-id="4a068-110">[in] The name of the loader file.</span></span>  
  
 `pCmdLine`  
 <span data-ttu-id="4a068-111">中命令行参数（如果有）。</span><span class="sxs-lookup"><span data-stu-id="4a068-111">[in] Command-line parameters, if any.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a068-112">要求</span><span class="sxs-lookup"><span data-stu-id="4a068-112">Requirements</span></span>  
 <span data-ttu-id="4a068-113">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4a068-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a068-114">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="4a068-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4a068-115">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="4a068-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4a068-116">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a068-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a068-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4a068-117">See also</span></span>

- [<span data-ttu-id="4a068-118">元数据全局静态函数</span><span class="sxs-lookup"><span data-stu-id="4a068-118">Metadata Global Static Functions</span></span>](../metadata/metadata-global-static-functions.md)
