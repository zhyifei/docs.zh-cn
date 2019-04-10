---
title: 如何：使用 ColumnDefinitionsCollection 和 RowDefinitionsCollection 操作列和行
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], Grid class
- Grid control [WPF], ColumnDefinitionCollection class
- Grid control [WPF], RowDefinitionCollection class
ms.assetid: bfc7160a-45f2-4e17-9961-df414dfb13c5
ms.openlocfilehash: f316cced076223edba1d39c9cfb21b9a504b9eee
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59147727"
---
# <a name="how-to-manipulate-columns-and-rows-by-using-columndefinitionscollections-and-rowdefinitionscollections"></a><span data-ttu-id="e9f84-102">如何：使用 ColumnDefinitionsCollection 和 RowDefinitionsCollection 操作列和行</span><span class="sxs-lookup"><span data-stu-id="e9f84-102">How to: Manipulate Columns and Rows by Using ColumnDefinitionsCollections and RowDefinitionsCollections</span></span>
<span data-ttu-id="e9f84-103">此示例演示如何使用中的方法<xref:System.Windows.Controls.ColumnDefinitionCollection>和<xref:System.Windows.Controls.RowDefinitionCollection>类执行的操作，例如添加、 清除或计数的行或列的内容。</span><span class="sxs-lookup"><span data-stu-id="e9f84-103">This example shows how to use the methods in the <xref:System.Windows.Controls.ColumnDefinitionCollection> and <xref:System.Windows.Controls.RowDefinitionCollection> classes to perform actions like adding, clearing, or counting the contents of rows or columns.</span></span> <span data-ttu-id="e9f84-104">例如，可以<xref:System.Windows.Controls.ColumnDefinitionCollection.Add%2A>， <xref:System.Windows.Controls.ColumnDefinitionCollection.Clear%2A>，或<xref:System.Windows.Controls.ColumnDefinitionCollection.Count%2A>中包含的项<xref:System.Windows.Controls.ColumnDefinition>或<xref:System.Windows.Controls.RowDefinition>。</span><span class="sxs-lookup"><span data-stu-id="e9f84-104">For example, you can <xref:System.Windows.Controls.ColumnDefinitionCollection.Add%2A>, <xref:System.Windows.Controls.ColumnDefinitionCollection.Clear%2A>, or <xref:System.Windows.Controls.ColumnDefinitionCollection.Count%2A> the items that are included in a <xref:System.Windows.Controls.ColumnDefinition> or <xref:System.Windows.Controls.RowDefinition>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e9f84-105">示例</span><span class="sxs-lookup"><span data-stu-id="e9f84-105">Example</span></span>  
 <span data-ttu-id="e9f84-106">下面的示例创建<xref:System.Windows.Controls.Grid>具有元素<xref:System.Windows.FrameworkElement.Name%2A>的`grid1`。</span><span class="sxs-lookup"><span data-stu-id="e9f84-106">The following example creates a <xref:System.Windows.Controls.Grid> element with a <xref:System.Windows.FrameworkElement.Name%2A> of `grid1`.</span></span> <span data-ttu-id="e9f84-107"><xref:System.Windows.Controls.Grid>包含<xref:System.Windows.Controls.StackPanel>，它持有<xref:System.Windows.Controls.Button>元素，每个受不同的集合方法。</span><span class="sxs-lookup"><span data-stu-id="e9f84-107">The <xref:System.Windows.Controls.Grid> contains a <xref:System.Windows.Controls.StackPanel> that holds <xref:System.Windows.Controls.Button> elements, each controlled by a different collection method.</span></span> <span data-ttu-id="e9f84-108">当您单击<xref:System.Windows.Controls.Button>，则会激活的代码隐藏文件中的方法调用。</span><span class="sxs-lookup"><span data-stu-id="e9f84-108">When you click a <xref:System.Windows.Controls.Button>, it activates a method call in the code-behind file.</span></span>  
  
 [!code-xaml[ColumnDefinitionsGrid#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ColumnDefinitionsGrid/CSharp/Window1.xaml#1)]  
  
 <span data-ttu-id="e9f84-109">此示例中定义的自定义方法，每个对应于一系列<xref:System.Windows.Controls.Primitives.ButtonBase.Click>中的事件[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]文件。</span><span class="sxs-lookup"><span data-stu-id="e9f84-109">This example defines a series of custom methods, each corresponding to a <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event in the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file.</span></span> <span data-ttu-id="e9f84-110">可以更改的列和中的行数<xref:System.Windows.Controls.Grid>中有多种，其中包括添加或删除行和列; 以及计算行和列的总数。</span><span class="sxs-lookup"><span data-stu-id="e9f84-110">You can change the number of columns and rows in the <xref:System.Windows.Controls.Grid> in several ways, which includes adding or removing rows and columns; and counting the total number of rows and columns.</span></span> <span data-ttu-id="e9f84-111">若要防止<xref:System.ArgumentOutOfRangeException>和<xref:System.ArgumentException>异常，您可以使用错误检查功能的<xref:System.Windows.Controls.ColumnDefinitionCollection.RemoveRange%2A>方法提供。</span><span class="sxs-lookup"><span data-stu-id="e9f84-111">To prevent <xref:System.ArgumentOutOfRangeException> and <xref:System.ArgumentException> exceptions, you can use the error-checking functionality that the <xref:System.Windows.Controls.ColumnDefinitionCollection.RemoveRange%2A> method provides.</span></span>  
  
 [!code-csharp[ColumnDefinitionsGrid#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ColumnDefinitionsGrid/CSharp/Window1.xaml.cs#2)]
 [!code-vb[ColumnDefinitionsGrid#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ColumnDefinitionsGrid/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="e9f84-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="e9f84-112">See also</span></span>

- <xref:System.Windows.Controls.Grid>
- <xref:System.Windows.Controls.ColumnDefinitionCollection>
- <xref:System.Windows.Controls.RowDefinitionCollection>
