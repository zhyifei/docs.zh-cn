---
title: "如何：转换绑定的数据"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- converting [WPF], bound data
- data binding [WPF], converting bound data
- binding data [WPF], converting bound data
ms.assetid: b00aaa19-c6df-4c3b-a9fd-88a0b488df2b
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3f4bcde15940e76e1d022658e32ff6ef8676e45e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-convert-bound-data"></a><span data-ttu-id="b76db-102">如何：转换绑定的数据</span><span class="sxs-lookup"><span data-stu-id="b76db-102">How to: Convert Bound Data</span></span>
<span data-ttu-id="b76db-103">此示例演示如何将转换应用于在绑定中使用的数据。</span><span class="sxs-lookup"><span data-stu-id="b76db-103">This example shows how to apply conversion to data that is used in bindings.</span></span>  
  
 <span data-ttu-id="b76db-104">若要在绑定期间转换数据，必须创建一个类以实现<xref:System.Windows.Data.IValueConverter>接口，其中包括<xref:System.Windows.Data.IValueConverter.Convert%2A>和<xref:System.Windows.Data.IValueConverter.ConvertBack%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="b76db-104">To convert data during binding, you must create a class that implements the <xref:System.Windows.Data.IValueConverter> interface, which includes the <xref:System.Windows.Data.IValueConverter.Convert%2A> and <xref:System.Windows.Data.IValueConverter.ConvertBack%2A> methods.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b76db-105">示例</span><span class="sxs-lookup"><span data-stu-id="b76db-105">Example</span></span>  
 <span data-ttu-id="b76db-106">下面的示例显示将转换中传递，以便它仅显示年、 月和日的日期值的日期转换器的实现。</span><span class="sxs-lookup"><span data-stu-id="b76db-106">The following example shows the implementation of a date converter that converts the date value passed in so that it only shows the year, the month, and the day.</span></span> <span data-ttu-id="b76db-107">在实现时<xref:System.Windows.Data.IValueConverter>接口，它是一个好办法修饰与实现<xref:System.Windows.Data.ValueConversionAttribute>属性以指示开发工具涉及在转换中，如以下示例所示的数据类型：</span><span class="sxs-lookup"><span data-stu-id="b76db-107">When implementing the <xref:System.Windows.Data.IValueConverter> interface, it is a good practice to decorate the implementation with a <xref:System.Windows.Data.ValueConversionAttribute> attribute to indicate to development tools the data types involved in the conversion, as in the following example:</span></span>  
  
 [!code-csharp[DataBindingLab#18](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DateConverter.cs#18)]
 [!code-vb[DataBindingLab#18](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/DateConverter.vb#18)]  
  
 <span data-ttu-id="b76db-108">一旦创建了转换器后，可以将其添加为中的资源你[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]文件。</span><span class="sxs-lookup"><span data-stu-id="b76db-108">Once you have created a converter, you can add it as a resource in your [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file.</span></span> <span data-ttu-id="b76db-109">在下面的示例中， *src*映射到的命名空间*DateConverter*定义。</span><span class="sxs-lookup"><span data-stu-id="b76db-109">In the following example, *src* maps to the namespace in which *DateConverter* is defined.</span></span>  
  
 [!code-xaml[DataBindingLab#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DataBindingLabApp.xaml#15)]  
  
 <span data-ttu-id="b76db-110">最后，你可以使用以下语法你绑定中使用转换器。</span><span class="sxs-lookup"><span data-stu-id="b76db-110">Finally, you can use the converter in your binding using the following syntax.</span></span> <span data-ttu-id="b76db-111">在下面的示例中的文本内容<xref:System.Windows.Controls.TextBlock>绑定到*StartDate*，这是外部数据源的属性。</span><span class="sxs-lookup"><span data-stu-id="b76db-111">In the following example, the text content of the <xref:System.Windows.Controls.TextBlock> is bound to *StartDate*, which is a property of an external data source.</span></span>  
  
 [!code-xaml[DataBindingLab#17](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DataBindingLabApp.xaml#17)]  
  
 <span data-ttu-id="b76db-112">在上面的示例所引用的样式资源定义中未显示在此主题的资源节中。</span><span class="sxs-lookup"><span data-stu-id="b76db-112">The style resources referenced in the above example are defined in a resource section not shown in this topic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b76db-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="b76db-113">See Also</span></span>  
 [<span data-ttu-id="b76db-114">实现绑定验证</span><span class="sxs-lookup"><span data-stu-id="b76db-114">Implement Binding Validation</span></span>](../../../../docs/framework/wpf/data/how-to-implement-binding-validation.md)  
 [<span data-ttu-id="b76db-115">数据绑定概述</span><span class="sxs-lookup"><span data-stu-id="b76db-115">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="b76db-116">帮助主题</span><span class="sxs-lookup"><span data-stu-id="b76db-116">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
