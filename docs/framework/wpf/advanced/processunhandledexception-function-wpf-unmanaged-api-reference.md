---
title: "ProcessUnhandledException 函数 （WPF 非托管 API 参考）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: cpp
api_name: ProcessUnhandledException
api_location: PresentationHost_v0400.dll
ms.assetid: 495ce5f6-bb4d-4b30-807a-c3c35f1ca95c
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8328ae4bcbff54743e8df0a4b6ff6da3065ea470
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="processunhandledexception-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="41135-102">ProcessUnhandledException 函数 （WPF 非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="41135-102">ProcessUnhandledException Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="41135-103">此 API 支持的 Windows Presentation Foundation (WPF) 基础结构，不宜在代码中直接使用。</span><span class="sxs-lookup"><span data-stu-id="41135-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="41135-104">Windows Presentation Foundation (WPF) 基础结构用于异常处理。</span><span class="sxs-lookup"><span data-stu-id="41135-104">Used by the Windows Presentation Foundation (WPF) infrastructure for exception handling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41135-105">语法</span><span class="sxs-lookup"><span data-stu-id="41135-105">Syntax</span></span>  
  
```cpp  
void __stdcall ProcessUnhandledException(  
   __in_ecount(1) BSTR errorMsg  
)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="41135-106">参数</span><span class="sxs-lookup"><span data-stu-id="41135-106">Parameters</span></span>  
 <span data-ttu-id="41135-107">errorMsg</span><span class="sxs-lookup"><span data-stu-id="41135-107">errorMsg</span></span>  
 <span data-ttu-id="41135-108">错误消息。</span><span class="sxs-lookup"><span data-stu-id="41135-108">The error message.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41135-109">要求</span><span class="sxs-lookup"><span data-stu-id="41135-109">Requirements</span></span>  
 <span data-ttu-id="41135-110">**平台：**请参阅[.NET Framework 系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="41135-110">**Platforms:** See [.NET Framework System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41135-111">**DLL:**</span><span class="sxs-lookup"><span data-stu-id="41135-111">**DLL:**</span></span>  
  
 <span data-ttu-id="41135-112">在.NET Framework 3.0 和 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="41135-112">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="41135-113">在.NET Framework 4 及更高版本： PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="41135-113">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="41135-114">**.NET framework 版本：**[!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="41135-114">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41135-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="41135-115">See Also</span></span>  
 [<span data-ttu-id="41135-116">WPF 非托管 API 参考</span><span class="sxs-lookup"><span data-stu-id="41135-116">WPF Unmanaged API Reference</span></span>](../../../../docs/framework/wpf/advanced/wpf-unmanaged-api-reference.md)
