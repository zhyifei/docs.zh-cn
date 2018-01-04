---
title: "ICorRuntimeHost::MapFile 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorRuntimeHost.MapFile
api_location: mscoree.dll
api_type: COM
f1_keywords: ICorRuntimeHost::MapFile
helpviewer_keywords:
- ICorRuntimeHost::MapFile method [.NET Framework hosting]
- MapFile method [.NET Framework hosting]
ms.assetid: 45ae0502-0a31-4342-b7e3-f36e1cf738f3
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b3047a473f36762ec57ae4ea87067e941ac568c4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icorruntimehostmapfile-method"></a><span data-ttu-id="e784e-102">ICorRuntimeHost::MapFile 方法</span><span class="sxs-lookup"><span data-stu-id="e784e-102">ICorRuntimeHost::MapFile Method</span></span>
<span data-ttu-id="e784e-103">将指定的文件映射到内存中。</span><span class="sxs-lookup"><span data-stu-id="e784e-103">Maps the specified file into memory.</span></span> <span data-ttu-id="e784e-104">此方法已过时。</span><span class="sxs-lookup"><span data-stu-id="e784e-104">This method is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e784e-105">语法</span><span class="sxs-lookup"><span data-stu-id="e784e-105">Syntax</span></span>  
  
```  
HRESULT MapFile(  
    [in]  HANDLE    hFile,  
    [out] HMODULE*  hMapAddress  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e784e-106">参数</span><span class="sxs-lookup"><span data-stu-id="e784e-106">Parameters</span></span>  
 `hFile`  
 <span data-ttu-id="e784e-107">[in]要映射的文件句柄。</span><span class="sxs-lookup"><span data-stu-id="e784e-107">[in] The handle of the file to be mapped.</span></span>  
  
 `hMapAddress`  
 <span data-ttu-id="e784e-108">[out]从此处开始映射文件起始内存地址。</span><span class="sxs-lookup"><span data-stu-id="e784e-108">[out] The starting memory address at which to begin mapping the file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e784e-109">惠?</span><span class="sxs-lookup"><span data-stu-id="e784e-109">Requirements</span></span>  
 <span data-ttu-id="e784e-110">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e784e-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e784e-111">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e784e-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e784e-112">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="e784e-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e784e-113">**.NET framework 版本：** 1.0、 1.1</span><span class="sxs-lookup"><span data-stu-id="e784e-113">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e784e-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="e784e-114">See Also</span></span>  
 [<span data-ttu-id="e784e-115">ICorRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="e784e-115">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
