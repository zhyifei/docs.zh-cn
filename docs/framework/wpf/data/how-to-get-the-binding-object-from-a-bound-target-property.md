---
title: 如何：从已绑定的目标属性获取绑定对象
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], getting binding objects from bound target properties
- properties [WPF], getting binding objects from
ms.assetid: 87974c5f-136b-4de7-b07d-9285b62ab123
ms.openlocfilehash: 7cebaf1077fb66420d77d656db32f444dd932b85
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2018
ms.locfileid: "44259869"
---
# <a name="how-to-get-the-binding-object-from-a-bound-target-property"></a><span data-ttu-id="12480-102">如何：从已绑定的目标属性获取绑定对象</span><span class="sxs-lookup"><span data-stu-id="12480-102">How to: Get the Binding Object from a Bound Target Property</span></span>
<span data-ttu-id="12480-103">本示例演示如何从数据绑定的目标属性获取绑定对象。</span><span class="sxs-lookup"><span data-stu-id="12480-103">This example shows how to obtain the binding object from a data-bound target property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="12480-104">示例</span><span class="sxs-lookup"><span data-stu-id="12480-104">Example</span></span>  
 <span data-ttu-id="12480-105">可以执行以下操作来获取 <xref:System.Windows.Data.Binding> 对象：</span><span class="sxs-lookup"><span data-stu-id="12480-105">You can do the following to get the <xref:System.Windows.Data.Binding> object:</span></span>  
  
 [!code-csharp[BindValidation#GetBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml.cs#getbinding)]  
  
> [!NOTE]
>  <span data-ttu-id="12480-106">要获取所需的绑定，必须指定依赖属性，因为目标对象中正在使用数据绑定的属性可能不止一个。</span><span class="sxs-lookup"><span data-stu-id="12480-106">You must specify the dependency property for the binding you want because it is possible that more than one property of the target object is using data binding.</span></span>  
  
 <span data-ttu-id="12480-107">或者，可以获取 <xref:System.Windows.Data.BindingExpression>，然后获取 <xref:System.Windows.Data.BindingExpression.ParentBinding%2A> 属性的值。</span><span class="sxs-lookup"><span data-stu-id="12480-107">Alternatively, you can get the <xref:System.Windows.Data.BindingExpression> and then get the value of the <xref:System.Windows.Data.BindingExpression.ParentBinding%2A> property.</span></span>  
  
 <span data-ttu-id="12480-108">有关完整示例，请参阅[绑定验证示例](https://go.microsoft.com/fwlink/?LinkID=159972)。</span><span class="sxs-lookup"><span data-stu-id="12480-108">For the complete example see [Binding Validation Sample](https://go.microsoft.com/fwlink/?LinkID=159972).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="12480-109">如果绑定是<xref:System.Windows.Data.MultiBinding>，使用<xref:System.Windows.Data.BindingOperations>。<xref:System.Windows.Data.BindingOperations.GetMultiBinding%2A>。</span><span class="sxs-lookup"><span data-stu-id="12480-109">If your binding is a <xref:System.Windows.Data.MultiBinding>, use <xref:System.Windows.Data.BindingOperations>.<xref:System.Windows.Data.BindingOperations.GetMultiBinding%2A>.</span></span> <span data-ttu-id="12480-110">如果它是<xref:System.Windows.Data.PriorityBinding>，使用<xref:System.Windows.Data.BindingOperations>。<xref:System.Windows.Data.BindingOperations.GetPriorityBinding%2A>。</span><span class="sxs-lookup"><span data-stu-id="12480-110">If it is a <xref:System.Windows.Data.PriorityBinding>, use <xref:System.Windows.Data.BindingOperations>.<xref:System.Windows.Data.BindingOperations.GetPriorityBinding%2A>.</span></span> <span data-ttu-id="12480-111">如果你不确定是否使用绑定目标属性<xref:System.Windows.Data.Binding>、 <xref:System.Windows.Data.MultiBinding>，或<xref:System.Windows.Data.PriorityBinding>，你可以使用<xref:System.Windows.Data.BindingOperations>。<xref:System.Windows.Data.BindingOperations.GetBindingBase%2A>。</span><span class="sxs-lookup"><span data-stu-id="12480-111">If you are uncertain whether the target property is bound using a <xref:System.Windows.Data.Binding>, a <xref:System.Windows.Data.MultiBinding>, or a <xref:System.Windows.Data.PriorityBinding>, you can use <xref:System.Windows.Data.BindingOperations>.<xref:System.Windows.Data.BindingOperations.GetBindingBase%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12480-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="12480-112">See Also</span></span>  
 [<span data-ttu-id="12480-113">在代码中创建绑定</span><span class="sxs-lookup"><span data-stu-id="12480-113">Create a Binding in Code</span></span>](../../../../docs/framework/wpf/data/how-to-create-a-binding-in-code.md)  
 [<span data-ttu-id="12480-114">帮助主题</span><span class="sxs-lookup"><span data-stu-id="12480-114">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
