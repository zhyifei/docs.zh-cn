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
ms.openlocfilehash: e188fe80e770481aac02244a2c105639e4da19e2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73108891"
---
# <a name="createapplicationcontext-function"></a><span data-ttu-id="a6089-102">CreateApplicationContext 函数</span><span class="sxs-lookup"><span data-stu-id="a6089-102">CreateApplicationContext Function</span></span>
<span data-ttu-id="a6089-103">此函数支持 .NET Framework 基础结构，不应在代码中直接使用。</span><span class="sxs-lookup"><span data-stu-id="a6089-103">This function supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6089-104">语法</span><span class="sxs-lookup"><span data-stu-id="a6089-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateApplicationContext (  
    [in]  IAssemblyName  *pName,  
    [out] LPPAPPLICATIONCONTEXT  *ppCtx  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="a6089-105">参数</span><span class="sxs-lookup"><span data-stu-id="a6089-105">Parameters</span></span>  
 `pName`  
 <span data-ttu-id="a6089-106">中指向友好名称的指针。</span><span class="sxs-lookup"><span data-stu-id="a6089-106">[in] A pointer to a friendly name.</span></span>  
  
 `ppCtx`  
 <span data-ttu-id="a6089-107">弄指向应用程序上下文的指针。</span><span class="sxs-lookup"><span data-stu-id="a6089-107">[out] A pointer to an application context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a6089-108">要求</span><span class="sxs-lookup"><span data-stu-id="a6089-108">Requirements</span></span>  
 <span data-ttu-id="a6089-109">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a6089-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6089-110">**标头：** 合成。h</span><span class="sxs-lookup"><span data-stu-id="a6089-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="a6089-111">**库：** 作为资源包含在合成 .dll 中</span><span class="sxs-lookup"><span data-stu-id="a6089-111">**Library:** Included as a resource in Fusion.dll</span></span>  
  
 <span data-ttu-id="a6089-112">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6089-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6089-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="a6089-113">See also</span></span>

- [<span data-ttu-id="a6089-114">IAssemblyCache 接口</span><span class="sxs-lookup"><span data-stu-id="a6089-114">IAssemblyCache Interface</span></span>](iassemblycache-interface.md)
- [<span data-ttu-id="a6089-115">合成全局静态函数</span><span class="sxs-lookup"><span data-stu-id="a6089-115">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
- [<span data-ttu-id="a6089-116">全局程序集缓存</span><span class="sxs-lookup"><span data-stu-id="a6089-116">Global Assembly Cache</span></span>](../../app-domains/gac.md)
