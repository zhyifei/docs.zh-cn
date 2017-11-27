---
title: "CreateApplicationContext 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CreateApplicationContext
api_location: fusion.dll
api_type: DLLExport
f1_keywords: CreateApplicationContext
helpviewer_keywords: CreateApplicationContext function [.NET Framework fusion]
ms.assetid: 7bf8a141-b2c0-4058-9885-1cef7dcaa811
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c089c32d4bc8474168274186a9303d39976abfca
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="createapplicationcontext-function"></a><span data-ttu-id="76749-102">CreateApplicationContext 函数</span><span class="sxs-lookup"><span data-stu-id="76749-102">CreateApplicationContext Function</span></span>
<span data-ttu-id="76749-103">此函数支持的.NET Framework 基础结构，不宜在代码中直接使用。</span><span class="sxs-lookup"><span data-stu-id="76749-103">This function supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76749-104">语法</span><span class="sxs-lookup"><span data-stu-id="76749-104">Syntax</span></span>  
  
```  
HRESULT CreateApplicationContext (  
    [in]  IAssemblyName  *pName,  
    [out] LPPAPPLICATIONCONTEXT  *ppCtx  
 );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="76749-105">参数</span><span class="sxs-lookup"><span data-stu-id="76749-105">Parameters</span></span>  
 `pName`  
 <span data-ttu-id="76749-106">[in]指向一个友好名称的指针。</span><span class="sxs-lookup"><span data-stu-id="76749-106">[in] A pointer to a friendly name.</span></span>  
  
 `ppCtx`  
 <span data-ttu-id="76749-107">[out]指向应用程序上下文的指针。</span><span class="sxs-lookup"><span data-stu-id="76749-107">[out] A pointer to an application context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="76749-108">要求</span><span class="sxs-lookup"><span data-stu-id="76749-108">Requirements</span></span>  
 <span data-ttu-id="76749-109">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="76749-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="76749-110">**标头：** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="76749-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="76749-111">**库：**作为中为 Fusion.dll 资源包括</span><span class="sxs-lookup"><span data-stu-id="76749-111">**Library:** Included as a resource in Fusion.dll</span></span>  
  
 <span data-ttu-id="76749-112">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="76749-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76749-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="76749-113">See Also</span></span>  
 [<span data-ttu-id="76749-114">IAssemblyCache 接口</span><span class="sxs-lookup"><span data-stu-id="76749-114">IAssemblyCache Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)  
 [<span data-ttu-id="76749-115">合成全局静态函数</span><span class="sxs-lookup"><span data-stu-id="76749-115">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)  
 [<span data-ttu-id="76749-116">全局程序集缓存</span><span class="sxs-lookup"><span data-stu-id="76749-116">Global Assembly Cache</span></span>](../../../../docs/framework/app-domains/gac.md)
