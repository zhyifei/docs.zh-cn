---
title: 如何：从元素中删除装饰器
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], removing
ms.assetid: 97cf4d9f-0596-429e-8526-32a30aa4ae99
ms.openlocfilehash: 256dd6fa0117f88aec2ef6b60c6dcd4c33b57855
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59212396"
---
# <a name="how-to-remove-an-adorner-from-an-element"></a>如何：从元素中删除装饰器
此示例演示如何以编程方式删除特定的装饰器从指定<xref:System.Windows.UIElement>。  
  
## <a name="example"></a>示例  
 此详细的代码示例的装饰器返回的数组中移除第一个装饰器<xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A>。  此示例检索在装饰器恰好<xref:System.Windows.UIElement>名为*myTextBox*。  如果在调用中指定元素<xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A>有任何装饰器，`null`返回。  此代码显式检查 null 的数组，并最适合应用程序的空数组的地方是比较常见。  
  
 [!code-csharp[AdornersMiscCode#_RemoveSpecificAdornerLong](~/samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removespecificadornerlong)]
 [!code-vb[AdornersMiscCode#_RemoveSpecificAdornerLong](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removespecificadornerlong)]  
  
## <a name="example"></a>示例  
 此简化的代码示例是功能上等效于上面所示的详细示例。 此代码不显式检查 null 数组，因此很可能，<xref:System.NullReferenceException>可能引发异常。  Null 数组的地方很少出现，此代码是最适合应用程序。  
  
 [!code-csharp[AdornersMiscCode#_RemoveSpecificAdornerShort](~/samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removespecificadornershort)]
 [!code-vb[AdornersMiscCode#_RemoveSpecificAdornerShort](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removespecificadornershort)]  
  
## <a name="see-also"></a>请参阅

- [装饰器概述](adorners-overview.md)
