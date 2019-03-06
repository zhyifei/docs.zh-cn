---
title: 如何：使用 GridView 显示 ListView 内容
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], displaying contents with GridView
- GridView [WPF], displaying ListView contents
ms.assetid: 5bc1e767-ab46-4f14-bd41-3d5d39e1d000
ms.openlocfilehash: 9a4bcc8b613637521ee91a11b0bdac8f77f90a03
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57354396"
---
# <a name="how-to-display-listview-contents-by-using-a-gridview"></a>如何：使用 GridView 显示 ListView 内容
此示例演示如何定义<xref:System.Windows.Controls.GridView>视图模式<xref:System.Windows.Controls.ListView>控件。  
  
## <a name="example"></a>示例  
 您可以定义的视图模式<xref:System.Windows.Controls.GridView>通过指定<xref:System.Windows.Controls.GridViewColumn>对象。 下面的示例演示如何定义<xref:System.Windows.Controls.GridViewColumn>绑定到为指定的数据内容的对象<xref:System.Windows.Controls.ListView>控件。 这<xref:System.Windows.Controls.GridView>的示例指定三个<xref:System.Windows.Controls.GridViewColumn>映射到的对象`FirstName`， `LastName`，并`EmployeeNumber`的字段`EmployeeInfoDataSource`设置为<xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>的<xref:System.Windows.Controls.ListView>控件。  
  
 [!code-xaml[ListViewCode#ListViewEmployee](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#listviewemployee)]  
  
 下图显示了此示例中的显示方式。  
  
 ![具有 GridView 输出的 ListView](./media/listviewgridview.JPG "ListViewGridView")  
  
## <a name="see-also"></a>请参阅
- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [ListView 概述](listview-overview.md)
- [GridView 概述](gridview-overview.md)
- [帮助主题](listview-how-to-topics.md)
