---
title: 如何：使用应用程序范围的资源字典
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dictionaries [WPF], resource
- resource dictionaries [WPF], application-scope
- application-scope resource dictionaries
ms.assetid: 53857682-bd2c-4f2c-8f25-1307d0b451a2
ms.openlocfilehash: 5bfb3ed0304598a5acf4b7682bf4a4169c5153d1
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459795"
---
# <a name="how-to-use-an-application-scope-resource-dictionary"></a>如何：使用应用程序范围的资源字典
本示例显示如何定义和使用应用程序范围的自定义资源字典。  
  
## <a name="example"></a>示例  
 <xref:System.Windows.Application> 公开共享资源的应用程序范围存储： <xref:System.Windows.Application.Resources%2A>。 默认情况下，使用 <xref:System.Windows.ResourceDictionary> 类型的实例初始化 <xref:System.Windows.Application.Resources%2A> 属性。 使用 <xref:System.Windows.Application.Resources%2A>获取和设置应用程序范围的属性时，可以使用此实例。 有关详细信息，请参阅[如何：获取和设置应用程序范围资源](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/aa348547(v=vs.100))。
  
 如果有多个使用 <xref:System.Windows.Application.Resources%2A>设置的资源，则可以改为使用自定义资源字典来存储这些资源并将 <xref:System.Windows.Application.Resources%2A> 设置为。 下面演示了如何使用 XAML 声明自定义资源字典。
  
 [!code-xaml[HOWTOResourceDictionaries#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MyResourceDictionary.xaml#1)]  
  
 使用 <xref:System.Windows.Application.Resources%2A> 交换整个资源字典允许您支持应用程序范围的主题，其中每个主题都由单个资源字典封装。 下面的示例演示如何设置 <xref:System.Windows.ResourceDictionary>。  
  
 [!code-xaml[HOWTOResourceDictionaries#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/App.xaml#2)]  
  
 下面演示了如何从 XAML 中 <xref:System.Windows.Application.Resources%2A> 公开的资源字典中获取应用程序范围的资源。  
  
 [!code-xaml[HOWTOResourceDictionaries#4](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MainWindow.xaml#4)]  
  
 以下内容显示如何也能获取代码中的资源。  
  
 [!code-csharp[HOWTOResourceDictionaries#3](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MainWindow.xaml.cs#3)]
 [!code-vb[HOWTOResourceDictionaries#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToResourceDictionaries/VB/MainWindow.xaml.vb#3)]  
  
 使用 <xref:System.Windows.Application.Resources%2A>时有两个注意事项。 首先，字典*键*是一个对象，因此在设置和获取属性值时，必须使用完全相同的对象实例。 （请注意，使用字符串时，该键区分大小写。）其次，字典*值*是一个对象，因此在获取属性值时，必须将该值转换为所需的类型。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.ResourceDictionary>
- <xref:System.Windows.Application.Resources%2A>
- [XAML 资源](../../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [合并资源字典](../advanced/merged-resource-dictionaries.md)
