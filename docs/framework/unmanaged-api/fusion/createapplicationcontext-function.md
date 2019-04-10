---
title: CreateApplicationContext 函数
ms.date: 03/30/2017
api_name:
- CreateApplicationContext
api_location:
- fusion.dll
api_type:
- DLLExport
f1_keywords:
- CreateApplicationContext
helpviewer_keywords:
- CreateApplicationContext function [.NET Framework fusion]
ms.assetid: 7bf8a141-b2c0-4058-9885-1cef7dcaa811
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d98829b29100824e5d606e23aaf287c9f6e81d69
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59170958"
---
# <a name="createapplicationcontext-function"></a><span data-ttu-id="b633e-102">CreateApplicationContext 函数</span><span class="sxs-lookup"><span data-stu-id="b633e-102">CreateApplicationContext Function</span></span>
<span data-ttu-id="b633e-103">此函数支持.NET Framework 基础结构，不应在代码中直接使用。</span><span class="sxs-lookup"><span data-stu-id="b633e-103">This function supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b633e-104">语法</span><span class="sxs-lookup"><span data-stu-id="b633e-104">Syntax</span></span>  
  
```  
HRESULT CreateApplicationContext (  
    [in]  IAssemblyName  *pName,  
    [out] LPPAPPLICATIONCONTEXT  *ppCtx  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="b633e-105">参数</span><span class="sxs-lookup"><span data-stu-id="b633e-105">Parameters</span></span>  
 `pName`  
 <span data-ttu-id="b633e-106">[in]指向一个友好名称的指针。</span><span class="sxs-lookup"><span data-stu-id="b633e-106">[in] A pointer to a friendly name.</span></span>  
  
 `ppCtx`  
 <span data-ttu-id="b633e-107">[out]指向应用程序上下文的指针。</span><span class="sxs-lookup"><span data-stu-id="b633e-107">[out] A pointer to an application context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b633e-108">要求</span><span class="sxs-lookup"><span data-stu-id="b633e-108">Requirements</span></span>  
 <span data-ttu-id="b633e-109">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b633e-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b633e-110">**标头：** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="b633e-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="b633e-111">**库：** 包含为 Fusion.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="b633e-111">**Library:** Included as a resource in Fusion.dll</span></span>  
  
 **<span data-ttu-id="b633e-112">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="b633e-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b633e-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="b633e-113">See also</span></span>

- [<span data-ttu-id="b633e-114">IAssemblyCache 接口</span><span class="sxs-lookup"><span data-stu-id="b633e-114">IAssemblyCache Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)
- [<span data-ttu-id="b633e-115">合成全局静态函数</span><span class="sxs-lookup"><span data-stu-id="b633e-115">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
- [<span data-ttu-id="b633e-116">全局程序集缓存</span><span class="sxs-lookup"><span data-stu-id="b633e-116">Global Assembly Cache</span></span>](../../../../docs/framework/app-domains/gac.md)
