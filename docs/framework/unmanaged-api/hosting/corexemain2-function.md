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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f968d84ae695eb1da127538ebdc5e4f55d6ebf39
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59183152"
---
# <a name="corexemain2-function"></a><span data-ttu-id="18d3d-102">_CorExeMain2 函数</span><span class="sxs-lookup"><span data-stu-id="18d3d-102">_CorExeMain2 Function</span></span>
<span data-ttu-id="18d3d-103">在指定的内存映射代码中执行的入口点。</span><span class="sxs-lookup"><span data-stu-id="18d3d-103">Executes the entry point in the specified memory-mapped code.</span></span> <span data-ttu-id="18d3d-104">由操作系统加载程序调用此函数。</span><span class="sxs-lookup"><span data-stu-id="18d3d-104">This function is called by the operating system loader.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18d3d-105">语法</span><span class="sxs-lookup"><span data-stu-id="18d3d-105">Syntax</span></span>  
  
```  
__int32 STDMETHODCALLTYPE _CorExeMain2 (  
   [in] PBYTE           pUnmappedPE,  
   [in] DWORD           cUnmappedPE,  
   [in] __in LPWSTR     pImageNameIn,  
   [in] __in LPWSTR     pLoadersFileName,  
   [in] __in LPWSTR     pCmdLine  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="18d3d-106">参数</span><span class="sxs-lookup"><span data-stu-id="18d3d-106">Parameters</span></span>  
 `pUnmappedPE`  
 <span data-ttu-id="18d3d-107">[in]指向内存映射代码的指针。</span><span class="sxs-lookup"><span data-stu-id="18d3d-107">[in] A pointer to the memory-mapped code.</span></span>  
  
 `cUnmappedPE`  
 <span data-ttu-id="18d3d-108">[in]元素数`pUnmappedPE`可以容纳。</span><span class="sxs-lookup"><span data-stu-id="18d3d-108">[in] The number of elements `pUnmappedPE` can hold.</span></span>  
  
 `pImageNameIn`  
 <span data-ttu-id="18d3d-109">[in]指向可执行映像的名称的指针。</span><span class="sxs-lookup"><span data-stu-id="18d3d-109">[in] A pointer to the name of the executable image.</span></span>  
  
 `pLoadersFileName`  
 <span data-ttu-id="18d3d-110">[in]加载程序文件的名称。</span><span class="sxs-lookup"><span data-stu-id="18d3d-110">[in] The name of the loader file.</span></span>  
  
 `pCmdLine`  
 <span data-ttu-id="18d3d-111">[in]命令行参数，如果有的话。</span><span class="sxs-lookup"><span data-stu-id="18d3d-111">[in] Command-line parameters, if any.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="18d3d-112">要求</span><span class="sxs-lookup"><span data-stu-id="18d3d-112">Requirements</span></span>  
 <span data-ttu-id="18d3d-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="18d3d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="18d3d-114">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="18d3d-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="18d3d-115">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="18d3d-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="18d3d-116">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="18d3d-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="18d3d-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="18d3d-117">See also</span></span>

- [<span data-ttu-id="18d3d-118">元数据全局静态函数</span><span class="sxs-lookup"><span data-stu-id="18d3d-118">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
