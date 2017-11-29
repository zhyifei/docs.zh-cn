---
title: "激活函数 （WPF 非托管 API 参考）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: cpp
api_name: Acrivate
api_location: PresentationHost_v0400.dll
ms.assetid: 1400329c-b598-465f-80f2-e3dabf044811
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 68f3f2a29da11a648b8c635667de6493a04ccd54
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="activate-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="631cc-102">激活函数 （WPF 非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="631cc-102">Activate Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="631cc-103">此 API 支持的 Windows Presentation Foundation (WPF) 基础结构，不宜在代码中直接使用。</span><span class="sxs-lookup"><span data-stu-id="631cc-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="631cc-104">Windows Presentation Foundation (WPF) 基础结构用于 windows 管理。</span><span class="sxs-lookup"><span data-stu-id="631cc-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="631cc-105">语法</span><span class="sxs-lookup"><span data-stu-id="631cc-105">Syntax</span></span>  
  
```cpp  
void Activate(  
    const ActivateParameters* pParameters,  
    __deref_out_ecount(1) LPUNKNOWN* ppInner,  
    );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="631cc-106">参数</span><span class="sxs-lookup"><span data-stu-id="631cc-106">Parameters</span></span>  
 <span data-ttu-id="631cc-107">pParameters</span><span class="sxs-lookup"><span data-stu-id="631cc-107">pParameters</span></span>  
 <span data-ttu-id="631cc-108">指向窗口的激活参数的指针。</span><span class="sxs-lookup"><span data-stu-id="631cc-108">A pointer to the window's activation parameters.</span></span>  
  
 <span data-ttu-id="631cc-109">ppInner</span><span class="sxs-lookup"><span data-stu-id="631cc-109">ppInner</span></span>  
 <span data-ttu-id="631cc-110">指向包含的指针的单个元素缓冲区的地址的指针<xref:Microsoft.VisualStudio.OLE.Interop.IOleDocument>对象。</span><span class="sxs-lookup"><span data-stu-id="631cc-110">A pointer to the address of a single-element buffer that contains a pointer to an <xref:Microsoft.VisualStudio.OLE.Interop.IOleDocument> object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="631cc-111">要求</span><span class="sxs-lookup"><span data-stu-id="631cc-111">Requirements</span></span>  
 <span data-ttu-id="631cc-112">**平台：**请参阅[.NET Framework 系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="631cc-112">**Platforms:** See [.NET Framework System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="631cc-113">**DLL:**</span><span class="sxs-lookup"><span data-stu-id="631cc-113">**DLL:**</span></span>  
  
 <span data-ttu-id="631cc-114">在.NET Framework 3.0 和 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="631cc-114">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="631cc-115">在.NET Framework 4 及更高版本： PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="631cc-115">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="631cc-116">**.NET framework 版本：**[!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="631cc-116">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="631cc-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="631cc-117">See Also</span></span>  
 [<span data-ttu-id="631cc-118">WPF 非托管 API 参考</span><span class="sxs-lookup"><span data-stu-id="631cc-118">WPF Unmanaged API Reference</span></span>](../../../../docs/framework/wpf/advanced/wpf-unmanaged-api-reference.md)
