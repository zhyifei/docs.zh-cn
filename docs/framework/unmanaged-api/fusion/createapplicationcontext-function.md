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
ms.openlocfilehash: 25364330dafdf858c4b41e9a05731c37e97fbb57
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795435"
---
# <a name="createapplicationcontext-function"></a><span data-ttu-id="cd8d9-102">CreateApplicationContext 函数</span><span class="sxs-lookup"><span data-stu-id="cd8d9-102">CreateApplicationContext Function</span></span>
<span data-ttu-id="cd8d9-103">此函数支持 .NET Framework 基础结构，不应在代码中直接使用。</span><span class="sxs-lookup"><span data-stu-id="cd8d9-103">This function supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd8d9-104">语法</span><span class="sxs-lookup"><span data-stu-id="cd8d9-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateApplicationContext (  
    [in]  IAssemblyName  *pName,  
    [out] LPPAPPLICATIONCONTEXT  *ppCtx  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="cd8d9-105">参数</span><span class="sxs-lookup"><span data-stu-id="cd8d9-105">Parameters</span></span>  
 `pName`  
 <span data-ttu-id="cd8d9-106">中指向友好名称的指针。</span><span class="sxs-lookup"><span data-stu-id="cd8d9-106">[in] A pointer to a friendly name.</span></span>  
  
 `ppCtx`  
 <span data-ttu-id="cd8d9-107">弄指向应用程序上下文的指针。</span><span class="sxs-lookup"><span data-stu-id="cd8d9-107">[out] A pointer to an application context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd8d9-108">要求</span><span class="sxs-lookup"><span data-stu-id="cd8d9-108">Requirements</span></span>  
 <span data-ttu-id="cd8d9-109">**适用**请参阅[系统需求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="cd8d9-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd8d9-110">**标头：** 合成。h</span><span class="sxs-lookup"><span data-stu-id="cd8d9-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="cd8d9-111">**类库**作为资源包含在合成 .dll 中</span><span class="sxs-lookup"><span data-stu-id="cd8d9-111">**Library:** Included as a resource in Fusion.dll</span></span>  
  
 <span data-ttu-id="cd8d9-112">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd8d9-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd8d9-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="cd8d9-113">See also</span></span>

- [<span data-ttu-id="cd8d9-114">IAssemblyCache 接口</span><span class="sxs-lookup"><span data-stu-id="cd8d9-114">IAssemblyCache Interface</span></span>](iassemblycache-interface.md)
- [<span data-ttu-id="cd8d9-115">合成全局静态函数</span><span class="sxs-lookup"><span data-stu-id="cd8d9-115">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
- [<span data-ttu-id="cd8d9-116">全局程序集缓存</span><span class="sxs-lookup"><span data-stu-id="cd8d9-116">Global Assembly Cache</span></span>](../../app-domains/gac.md)
