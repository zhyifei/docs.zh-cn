---
title: 如何：转换绑定的数据
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- converting [WPF], bound data
- data binding [WPF], converting bound data
- binding data [WPF], converting bound data
ms.assetid: b00aaa19-c6df-4c3b-a9fd-88a0b488df2b
ms.openlocfilehash: f9ad390626092d481bf47f017f643a29302c1b29
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458868"
---
# <a name="how-to-convert-bound-data"></a><span data-ttu-id="84f46-102">如何：转换绑定的数据</span><span class="sxs-lookup"><span data-stu-id="84f46-102">How to: Convert Bound Data</span></span>
<span data-ttu-id="84f46-103">此示例演示如何将转换应用于绑定中使用的数据。</span><span class="sxs-lookup"><span data-stu-id="84f46-103">This example shows how to apply conversion to data that is used in bindings.</span></span>  
  
 <span data-ttu-id="84f46-104">若要在绑定期间转换数据，您必须创建一个实现 <xref:System.Windows.Data.IValueConverter> 接口的类，其中包括 <xref:System.Windows.Data.IValueConverter.Convert%2A> 和 <xref:System.Windows.Data.IValueConverter.ConvertBack%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="84f46-104">To convert data during binding, you must create a class that implements the <xref:System.Windows.Data.IValueConverter> interface, which includes the <xref:System.Windows.Data.IValueConverter.Convert%2A> and <xref:System.Windows.Data.IValueConverter.ConvertBack%2A> methods.</span></span>  
  
## <a name="example"></a><span data-ttu-id="84f46-105">示例</span><span class="sxs-lookup"><span data-stu-id="84f46-105">Example</span></span>  
 <span data-ttu-id="84f46-106">下面的示例演示如何实现日期转换器，该转换器转换传入的 date 值，以便只显示年份、月份和日期。</span><span class="sxs-lookup"><span data-stu-id="84f46-106">The following example shows the implementation of a date converter that converts the date value passed in so that it only shows the year, the month, and the day.</span></span> <span data-ttu-id="84f46-107">在实现 <xref:System.Windows.Data.IValueConverter> 接口时，最好使用 <xref:System.Windows.Data.ValueConversionAttribute> 特性来修饰实现，以便向开发工具指示转换中涉及的数据类型，如以下示例中所示：</span><span class="sxs-lookup"><span data-stu-id="84f46-107">When implementing the <xref:System.Windows.Data.IValueConverter> interface, it is a good practice to decorate the implementation with a <xref:System.Windows.Data.ValueConversionAttribute> attribute to indicate to development tools the data types involved in the conversion, as in the following example:</span></span>  
  
 [!code-csharp[DataBindingLab#18](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DateConverter.cs#18)]
 [!code-vb[DataBindingLab#18](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/DateConverter.vb#18)]  
  
 <span data-ttu-id="84f46-108">创建转换器后，可以将其作为资源添加到 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 文件中。</span><span class="sxs-lookup"><span data-stu-id="84f46-108">Once you have created a converter, you can add it as a resource in your [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file.</span></span> <span data-ttu-id="84f46-109">在下面的示例中， *src*映射到在其中定义了*DateConverter*的命名空间。</span><span class="sxs-lookup"><span data-stu-id="84f46-109">In the following example, *src* maps to the namespace in which *DateConverter* is defined.</span></span>  
  
 [!code-xaml[DataBindingLab#15](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DataBindingLabApp.xaml#15)]  
  
 <span data-ttu-id="84f46-110">最后，可以使用以下语法在绑定中使用转换器。</span><span class="sxs-lookup"><span data-stu-id="84f46-110">Finally, you can use the converter in your binding using the following syntax.</span></span> <span data-ttu-id="84f46-111">在下面的示例中，<xref:System.Windows.Controls.TextBlock> 的文本内容绑定到开始*日期*，这是外部数据源的属性。</span><span class="sxs-lookup"><span data-stu-id="84f46-111">In the following example, the text content of the <xref:System.Windows.Controls.TextBlock> is bound to *StartDate*, which is a property of an external data source.</span></span>  
  
 [!code-xaml[DataBindingLab#17](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DataBindingLabApp.xaml#17)]  
  
 <span data-ttu-id="84f46-112">上述示例中引用的样式资源在资源部分中定义，而不会显示在本主题中。</span><span class="sxs-lookup"><span data-stu-id="84f46-112">The style resources referenced in the above example are defined in a resource section not shown in this topic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84f46-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="84f46-113">See also</span></span>

- [<span data-ttu-id="84f46-114">实现绑定验证</span><span class="sxs-lookup"><span data-stu-id="84f46-114">Implement Binding Validation</span></span>](how-to-implement-binding-validation.md)
- [<span data-ttu-id="84f46-115">数据绑定概述</span><span class="sxs-lookup"><span data-stu-id="84f46-115">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="84f46-116">帮助主题</span><span class="sxs-lookup"><span data-stu-id="84f46-116">How-to Topics</span></span>](data-binding-how-to-topics.md)
