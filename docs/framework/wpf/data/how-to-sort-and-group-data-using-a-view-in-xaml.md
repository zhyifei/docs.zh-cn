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
ms.openlocfilehash: 80529420bcc5fdca473313e164b3d096732953f4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33555823"
---
# <a name="how-to-sort-and-group-data-using-a-view-in-xaml"></a><span data-ttu-id="15a71-102">如何：在 XAML 中使用视图对数据进行排序和分组</span><span class="sxs-lookup"><span data-stu-id="15a71-102">How to: Sort and Group Data Using a View in XAML</span></span>
<span data-ttu-id="15a71-103">此示例演示如何创建数据集合中的视图[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="15a71-103">This example shows how to create a view of a data collection in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span> <span data-ttu-id="15a71-104">视图允许分组、 排序、 筛选、 功能和当前项的概念。</span><span class="sxs-lookup"><span data-stu-id="15a71-104">Views allow for the functionalities of grouping, sorting, filtering, and the notion of a current item.</span></span>  
  
## <a name="example"></a><span data-ttu-id="15a71-105">示例</span><span class="sxs-lookup"><span data-stu-id="15a71-105">Example</span></span>  
 <span data-ttu-id="15a71-106">在下面的示例中，静态资源名为*放置*指一套*位置*对象，其中的每个*位置*对象包含的城市名称和状态。</span><span class="sxs-lookup"><span data-stu-id="15a71-106">In the following example, the static resource named *places* is defined as a collection of *Place* objects, in which each *Place* object is consisted of a city name and the state.</span></span> <span data-ttu-id="15a71-107">前缀*src*映射到命名空间中的数据源*位置*定义。</span><span class="sxs-lookup"><span data-stu-id="15a71-107">The prefix *src* is mapped to the namespace where the data source *Places* is defined.</span></span> <span data-ttu-id="15a71-108">前缀*scm*映射到`"clr-namespace:System.ComponentModel;assembly=WindowsBase"`和*dat*映射到`"clr-namespace:System.Windows.Data;assembly=PresentationFramework"`。</span><span class="sxs-lookup"><span data-stu-id="15a71-108">The prefix *scm* maps to `"clr-namespace:System.ComponentModel;assembly=WindowsBase"` and *dat* maps to `"clr-namespace:System.Windows.Data;assembly=PresentationFramework"`.</span></span>  
  
 <span data-ttu-id="15a71-109">下面的示例创建数据集合，它按状态分组并按城市名称排序的视图。</span><span class="sxs-lookup"><span data-stu-id="15a71-109">The following example creates a view of the data collection that is sorted by the city name and grouped by the state.</span></span>  
  
 [!code-xaml[CollectionViewSource#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#1)]  
  
 <span data-ttu-id="15a71-110">视图随后可以绑定源，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="15a71-110">The view can then be a binding source, as in the following example:</span></span>  
  
 [!code-xaml[CollectionViewSource#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#2)]  
  
 <span data-ttu-id="15a71-111">对于到 XML 数据中定义的绑定<xref:System.Windows.Data.XmlDataProvider>资源，XML 名称前面加上 @ 符号。</span><span class="sxs-lookup"><span data-stu-id="15a71-111">For bindings to XML data defined in an <xref:System.Windows.Data.XmlDataProvider> resource, precede the XML name with an @ symbol.</span></span>  
  
 [!code-xaml[CollectionViewSource#XDPChunk](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#xdpchunk)]  
  
 [!code-xaml[CollectionViewSource#Attribute](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#attribute)]  
  
## <a name="see-also"></a><span data-ttu-id="15a71-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="15a71-112">See Also</span></span>  
 <xref:System.Windows.Data.CollectionViewSource>  
 [<span data-ttu-id="15a71-113">获取数据集合的默认视图</span><span class="sxs-lookup"><span data-stu-id="15a71-113">Get the Default View of a Data Collection</span></span>](../../../../docs/framework/wpf/data/how-to-get-the-default-view-of-a-data-collection.md)  
 [<span data-ttu-id="15a71-114">数据绑定概述</span><span class="sxs-lookup"><span data-stu-id="15a71-114">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="15a71-115">帮助主题</span><span class="sxs-lookup"><span data-stu-id="15a71-115">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
