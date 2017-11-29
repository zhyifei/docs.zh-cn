---
title: GetCustomUI
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: custom error messages [WPF]
ms.assetid: e55180fc-35bb-4f80-a136-772b5eb3e4e5
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3f3c101ad13df9b99a2d872bac8783baed8b4b9a
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="getcustomui"></a><span data-ttu-id="13365-102">GetCustomUI</span><span class="sxs-lookup"><span data-stu-id="13365-102">GetCustomUI</span></span>
<span data-ttu-id="13365-103">如果实现由 PresentationHost.exe 若要从主机中获取自定义的进度和错误消息调用。</span><span class="sxs-lookup"><span data-stu-id="13365-103">Called by PresentationHost.exe to get custom progress and error messages from the host, if implemented.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13365-104">语法</span><span class="sxs-lookup"><span data-stu-id="13365-104">Syntax</span></span>  
  
```  
HRESULT GetCustomUI( [out] BSTR* pwzProgressAssemblyName, [out] BSTR* pwzProgressClassName, [out] BSTR* pwzErrorAssemblyName, [out] BSTR* pwzErrorClassName );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="13365-105">参数</span><span class="sxs-lookup"><span data-stu-id="13365-105">Parameters</span></span>  
 `pwzProgressAssemblyName`  
  
 <span data-ttu-id="13365-106">[out]指向包含主机提供进度用户界面的程序集的指针。</span><span class="sxs-lookup"><span data-stu-id="13365-106">[out] A pointer to the assembly that contains the host-supplied progress user interface.</span></span>  
  
 `pwzProgressClassName`  
  
 <span data-ttu-id="13365-107">[out]最好是主机提供进度用户界面，类的名称[!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)]文件<xref:System.Windows.Controls.Page>是其顶级元素。</span><span class="sxs-lookup"><span data-stu-id="13365-107">[out] The name of the class that is the host-supplied progress user interface, preferably a [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] file with <xref:System.Windows.Controls.Page> is its top-level element.</span></span> <span data-ttu-id="13365-108">此类驻留在由指定的程序集`pwzProgressAssemblyName`。</span><span class="sxs-lookup"><span data-stu-id="13365-108">This class resides in the assembly that is specified by `pwzProgressAssemblyName`.</span></span>  
  
 `pwzErrorAssemblyName`  
  
 <span data-ttu-id="13365-109">[out]指向包含主机提供的错误用户界面的程序集的指针。</span><span class="sxs-lookup"><span data-stu-id="13365-109">[out] A pointer to the assembly that contains the host-supplied error user interface.</span></span>  
  
 `pwzErrorClassName`  
  
 <span data-ttu-id="13365-110">[out]为主机提供的错误的用户类的名称最好接口的 XAML 文件<xref:System.Windows.Controls.Page>是其顶级元素。</span><span class="sxs-lookup"><span data-stu-id="13365-110">[out] The name of the class that is the host-supplied error user interface, preferably a XAML file with <xref:System.Windows.Controls.Page> is its top-level element.</span></span> <span data-ttu-id="13365-111">此类驻留在由指定的程序集`pwzErrorAssemblyName`。</span><span class="sxs-lookup"><span data-stu-id="13365-111">This class resides in the assembly that is specified by `pwzErrorAssemblyName`.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="13365-112">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="13365-112">Property Value/Return Value</span></span>  
 <span data-ttu-id="13365-113">HRESULT： 忽略。</span><span class="sxs-lookup"><span data-stu-id="13365-113">HRESULT: Ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="13365-114">备注</span><span class="sxs-lookup"><span data-stu-id="13365-114">Remarks</span></span>  
 <span data-ttu-id="13365-115">主机应用程序可能具有 PresentationHost.exe 的默认用户界面可能不符合特定主题。</span><span class="sxs-lookup"><span data-stu-id="13365-115">A host application may have a specific theme that PresentationHost.exe’s default user interfaces may not conform to.</span></span> <span data-ttu-id="13365-116">如果出现这种情况，可以实现主机应用程序[GetCustomUI](../../../../docs/framework/wpf/app-development/getcustomui.md)返回进度和错误的用户界面到 PresentationHost.exe。</span><span class="sxs-lookup"><span data-stu-id="13365-116">If this is the case, the host application can implement [GetCustomUI](../../../../docs/framework/wpf/app-development/getcustomui.md) to return progress and error user interfaces to PresentationHost.exe.</span></span> <span data-ttu-id="13365-117">将始终调用 PresentationHost.exe [GetCustomUI](../../../../docs/framework/wpf/app-development/getcustomui.md)然后才能使用其默认用户界面。</span><span class="sxs-lookup"><span data-stu-id="13365-117">PresentationHost.exe will always call [GetCustomUI](../../../../docs/framework/wpf/app-development/getcustomui.md) before using its default user interfaces.</span></span>  
  
 <span data-ttu-id="13365-118">一次在 PresentationHost 的初始化过程中调用此函数。</span><span class="sxs-lookup"><span data-stu-id="13365-118">This function is called once during PresentationHost’s initialization.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13365-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="13365-119">See Also</span></span>  
 [<span data-ttu-id="13365-120">IWpfHostSupport</span><span class="sxs-lookup"><span data-stu-id="13365-120">IWpfHostSupport</span></span>](../../../../docs/framework/wpf/app-development/iwpfhostsupport.md)
