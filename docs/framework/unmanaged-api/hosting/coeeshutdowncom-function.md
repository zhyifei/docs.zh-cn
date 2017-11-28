---
title: "CoEEShutDownCOM 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CoEEShutDownCOM
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type: DLLExport
f1_keywords: CoEEShutDownCOM
helpviewer_keywords: CoEEShutDownCOM function [.NET Framework hosting]
ms.assetid: b634cae2-632f-4737-9be4-92d0652844d7
topic_type: apiref
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8d6d9e3d650f65ef084c63104980bca0ac77f1bd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="coeeshutdowncom-function"></a><span data-ttu-id="4df43-102">CoEEShutDownCOM 函数</span><span class="sxs-lookup"><span data-stu-id="4df43-102">CoEEShutDownCOM Function</span></span>
<span data-ttu-id="4df43-103">强制公共语言运行时 (CLR) 来释放它在运行时可调用包装 (RCW) 内包含的所有接口指针。</span><span class="sxs-lookup"><span data-stu-id="4df43-103">Forces the common language runtime (CLR) to release all interface pointers it holds inside runtime callable wrappers (RCW).</span></span> <span data-ttu-id="4df43-104">此操作将释放 RCW 的所有缓存。</span><span class="sxs-lookup"><span data-stu-id="4df43-104">This has the effect of releasing all RCW caches.</span></span> <span data-ttu-id="4df43-105">中已弃用此全局函数[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="4df43-105">This global function is deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="4df43-106">相反，针对特定运行时使用的入口点。</span><span class="sxs-lookup"><span data-stu-id="4df43-106">Instead, use the entry point for a specific runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4df43-107">语法</span><span class="sxs-lookup"><span data-stu-id="4df43-107">Syntax</span></span>  
  
```  
void CoEEShutDownCOM ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="4df43-108">备注</span><span class="sxs-lookup"><span data-stu-id="4df43-108">Remarks</span></span>  
 <span data-ttu-id="4df43-109">`CoEEShutDownCOM`函数首先释放所有 Rcw 所有上下文在和中的所有缓存，并将删除现有的安装程序中任何拆除通知。</span><span class="sxs-lookup"><span data-stu-id="4df43-109">The `CoEEShutDownCOM` function first releases all the RCWs in all contexts and in all caches, and then removes any tear-down notification existing in setup.</span></span> <span data-ttu-id="4df43-110">没有 DLL 卸载时发生。</span><span class="sxs-lookup"><span data-stu-id="4df43-110">No DLL unloading occurs.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="4df43-111">此函数会影响所有加载到进程的运行时。</span><span class="sxs-lookup"><span data-stu-id="4df43-111">This function affects all runtimes that are loaded into the process.</span></span>  
  
 <span data-ttu-id="4df43-112">开头[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]，调用此函数对你想要影响特定运行时的入口点。</span><span class="sxs-lookup"><span data-stu-id="4df43-112">Beginning with the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)], call the entry point for this function on the specific runtime you want to affect.</span></span> <span data-ttu-id="4df43-113">若要获取的入口点，请调用[iclrruntimeinfo:: Getprocaddress](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getprocaddress-method.md)方法并指定"CoEEShutDownCOM"。</span><span class="sxs-lookup"><span data-stu-id="4df43-113">To get the entry point, call the [ICLRRuntimeInfo::GetProcAddress](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getprocaddress-method.md) method and specify "CoEEShutDownCOM".</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4df43-114">要求</span><span class="sxs-lookup"><span data-stu-id="4df43-114">Requirements</span></span>  
 <span data-ttu-id="4df43-115">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4df43-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4df43-116">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="4df43-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4df43-117">**库：**作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="4df43-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4df43-118">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4df43-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4df43-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4df43-119">See Also</span></span>  
 [<span data-ttu-id="4df43-120">元数据全局静态函数</span><span class="sxs-lookup"><span data-stu-id="4df43-120">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
