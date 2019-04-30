---
title: 如何：在 XAML 中使用视图对数据进行排序和分组
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], grouping data in views in XAML
- XAML [WPF], sorting data in views
- grouping data in views in XAML [WPF]
- data binding [WPF], sorting data in views in XAML
- sorting data in views in XAML [WPF]
- XAML [WPF], grouping data in views
- views [WPF], sorting data
- views [WPF], grouping data
ms.assetid: 145c8c3f-dbdd-4d0d-816f-90b35eba7eda
ms.openlocfilehash: ca4439b574264ebebfda745f0765f750099bc95f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62020733"
---
# <a name="how-to-sort-and-group-data-using-a-view-in-xaml"></a><span data-ttu-id="70eba-102">如何：在 XAML 中使用视图对数据进行排序和分组</span><span class="sxs-lookup"><span data-stu-id="70eba-102">How to: Sort and Group Data Using a View in XAML</span></span>
<span data-ttu-id="70eba-103">此示例演示如何在[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]中创建数据集合的视图。</span><span class="sxs-lookup"><span data-stu-id="70eba-103">This example shows how to create a view of a data collection in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span> <span data-ttu-id="70eba-104">视图提供分组、排序、筛选功能和当前项的概念。</span><span class="sxs-lookup"><span data-stu-id="70eba-104">Views allow for the functionalities of grouping, sorting, filtering, and the notion of a current item.</span></span>  
  
## <a name="example"></a><span data-ttu-id="70eba-105">示例</span><span class="sxs-lookup"><span data-stu-id="70eba-105">Example</span></span>  
 <span data-ttu-id="70eba-106">在下面的示例中，名为 *places* 的静态资源被定义为 *Place* 对象的集合，其中每个 *Place* 对象包含城市名和州。</span><span class="sxs-lookup"><span data-stu-id="70eba-106">In the following example, the static resource named *places* is defined as a collection of *Place* objects, in which each *Place* object is consisted of a city name and the state.</span></span> <span data-ttu-id="70eba-107">前缀 *src* 映射到定义 *Places* 数据源的命名空间。</span><span class="sxs-lookup"><span data-stu-id="70eba-107">The prefix *src* is mapped to the namespace where the data source *Places* is defined.</span></span> <span data-ttu-id="70eba-108">前缀 *scm* 映射到`"clr-namespace:System.ComponentModel;assembly=WindowsBase"`，*dat* 映射到`"clr-namespace:System.Windows.Data;assembly=PresentationFramework"`。</span><span class="sxs-lookup"><span data-stu-id="70eba-108">The prefix *scm* maps to `"clr-namespace:System.ComponentModel;assembly=WindowsBase"` and *dat* maps to `"clr-namespace:System.Windows.Data;assembly=PresentationFramework"`.</span></span>  
  
 <span data-ttu-id="70eba-109">下面的示例创建数据集合的视图，数据按城市名称排序，并按州分组。</span><span class="sxs-lookup"><span data-stu-id="70eba-109">The following example creates a view of the data collection that is sorted by the city name and grouped by the state.</span></span>  
  
 [!code-xaml[CollectionViewSource#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#1)]  
  
 <span data-ttu-id="70eba-110">然后，该视图可以是绑定源，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="70eba-110">The view can then be a binding source, as in the following example:</span></span>  
  
 [!code-xaml[CollectionViewSource#2](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#2)]  
  
 <span data-ttu-id="70eba-111">绑定到 <xref:System.Windows.Data.XmlDataProvider> 资源中定义的 XML 数据时，XML 名称前面要加上 @ 符号。</span><span class="sxs-lookup"><span data-stu-id="70eba-111">For bindings to XML data defined in an <xref:System.Windows.Data.XmlDataProvider> resource, precede the XML name with an @ symbol.</span></span>  
  
 [!code-xaml[CollectionViewSource#XDPChunk](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#xdpchunk)]  
  
 [!code-xaml[CollectionViewSource#Attribute](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#attribute)]  
  
## <a name="see-also"></a><span data-ttu-id="70eba-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="70eba-112">See also</span></span>

- <xref:System.Windows.Data.CollectionViewSource>
- [<span data-ttu-id="70eba-113">获取数据集合的默认视图</span><span class="sxs-lookup"><span data-stu-id="70eba-113">Get the Default View of a Data Collection</span></span>](how-to-get-the-default-view-of-a-data-collection.md)
- [<span data-ttu-id="70eba-114">数据绑定概述</span><span class="sxs-lookup"><span data-stu-id="70eba-114">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="70eba-115">帮助主题</span><span class="sxs-lookup"><span data-stu-id="70eba-115">How-to Topics</span></span>](data-binding-how-to-topics.md)
