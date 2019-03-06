---
title: GetCustomUI
ms.date: 03/30/2017
helpviewer_keywords:
- custom error messages [WPF]
ms.assetid: e55180fc-35bb-4f80-a136-772b5eb3e4e5
ms.openlocfilehash: 623ff5d14db6ae9cc5999aa184b81d6b22f4b201
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57365004"
---
# <a name="getcustomui"></a><span data-ttu-id="fcbce-102">GetCustomUI</span><span class="sxs-lookup"><span data-stu-id="fcbce-102">GetCustomUI</span></span>
<span data-ttu-id="fcbce-103">如果实现由 PresentationHost.exe 从主机获取自定义进度和错误消息调用。</span><span class="sxs-lookup"><span data-stu-id="fcbce-103">Called by PresentationHost.exe to get custom progress and error messages from the host, if implemented.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fcbce-104">语法</span><span class="sxs-lookup"><span data-stu-id="fcbce-104">Syntax</span></span>  
  
```  
HRESULT GetCustomUI( [out] BSTR* pwzProgressAssemblyName, [out] BSTR* pwzProgressClassName, [out] BSTR* pwzErrorAssemblyName, [out] BSTR* pwzErrorClassName );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fcbce-105">参数</span><span class="sxs-lookup"><span data-stu-id="fcbce-105">Parameters</span></span>  
 `pwzProgressAssemblyName`  
  
 <span data-ttu-id="fcbce-106">[out]指向包含主机提供进度用户界面的程序集的指针。</span><span class="sxs-lookup"><span data-stu-id="fcbce-106">[out] A pointer to the assembly that contains the host-supplied progress user interface.</span></span>  
  
 `pwzProgressClassName`  
  
 <span data-ttu-id="fcbce-107">[out]最好是为主机提供进度用户界面，类的名称[!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)]文件具有<xref:System.Windows.Controls.Page>是其顶级元素。</span><span class="sxs-lookup"><span data-stu-id="fcbce-107">[out] The name of the class that is the host-supplied progress user interface, preferably a [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] file with <xref:System.Windows.Controls.Page> is its top-level element.</span></span> <span data-ttu-id="fcbce-108">此类驻留在由指定的程序集`pwzProgressAssemblyName`。</span><span class="sxs-lookup"><span data-stu-id="fcbce-108">This class resides in the assembly that is specified by `pwzProgressAssemblyName`.</span></span>  
  
 `pwzErrorAssemblyName`  
  
 <span data-ttu-id="fcbce-109">[out]指向包含主机提供的错误用户界面的程序集的指针。</span><span class="sxs-lookup"><span data-stu-id="fcbce-109">[out] A pointer to the assembly that contains the host-supplied error user interface.</span></span>  
  
 `pwzErrorClassName`  
  
 <span data-ttu-id="fcbce-110">[out]为主机提供的错误用户类的名称最好是接口具有的 XAML 文件<xref:System.Windows.Controls.Page>是其顶级元素。</span><span class="sxs-lookup"><span data-stu-id="fcbce-110">[out] The name of the class that is the host-supplied error user interface, preferably a XAML file with <xref:System.Windows.Controls.Page> is its top-level element.</span></span> <span data-ttu-id="fcbce-111">此类驻留在由指定的程序集`pwzErrorAssemblyName`。</span><span class="sxs-lookup"><span data-stu-id="fcbce-111">This class resides in the assembly that is specified by `pwzErrorAssemblyName`.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="fcbce-112">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="fcbce-112">Property Value/Return Value</span></span>  
 <span data-ttu-id="fcbce-113">HRESULT：已忽略。</span><span class="sxs-lookup"><span data-stu-id="fcbce-113">HRESULT: Ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fcbce-114">备注</span><span class="sxs-lookup"><span data-stu-id="fcbce-114">Remarks</span></span>  
 <span data-ttu-id="fcbce-115">主机应用程序可能具有可能不符合 PresentationHost.exe 的默认用户界面的特定主题。</span><span class="sxs-lookup"><span data-stu-id="fcbce-115">A host application may have a specific theme that PresentationHost.exe’s default user interfaces may not conform to.</span></span> <span data-ttu-id="fcbce-116">如果是这样，主机应用程序可以实现[GetCustomUI](getcustomui.md)返回进度和错误的用户界面到 PresentationHost.exe。</span><span class="sxs-lookup"><span data-stu-id="fcbce-116">If this is the case, the host application can implement [GetCustomUI](getcustomui.md) to return progress and error user interfaces to PresentationHost.exe.</span></span> <span data-ttu-id="fcbce-117">将始终调用 PresentationHost.exe [GetCustomUI](getcustomui.md)之前使用其默认用户界面。</span><span class="sxs-lookup"><span data-stu-id="fcbce-117">PresentationHost.exe will always call [GetCustomUI](getcustomui.md) before using its default user interfaces.</span></span>  
  
 <span data-ttu-id="fcbce-118">一次在 PresentationHost 的初始化期间调用此函数。</span><span class="sxs-lookup"><span data-stu-id="fcbce-118">This function is called once during PresentationHost’s initialization.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcbce-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="fcbce-119">See also</span></span>
- [<span data-ttu-id="fcbce-120">IWpfHostSupport</span><span class="sxs-lookup"><span data-stu-id="fcbce-120">IWpfHostSupport</span></span>](iwpfhostsupport.md)
