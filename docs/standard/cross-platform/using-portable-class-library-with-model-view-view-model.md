---
title: "将可移植类库与模型-视图-视图模型配合使用"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Portable Class Library [.NET Framework], and MVVM
- MVVM, and Portable Class Library
ms.assetid: 41a0b9f8-15a2-431a-bc35-e310b2953b03
caps.latest.revision: "17"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: cc12a90025a1862fc6c588fe4425f3f8341da313
ms.sourcegitcommit: 91691981897cf8451033cb01071d8f5d94017f97
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2018
---
# <a name="using-portable-class-library-with-model-view-view-model"></a>将可移植类库与模型-视图-视图模型配合使用
你可以使用.NET Framework[可移植类库](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md)实现模型-视图-视图模型 (MVVM) 模式并在多个平台之间共享程序集。  
  
 MVVM 是将用户界面与基础业务逻辑相隔离的应用程序模式。 您可以在 [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] 中的[!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)]项目中实现模型和视图模型类，然后针对不同的平台创建自定义视图。 通过此方法，只需编写数据模型和业务逻辑一次，即可将该代码用于 .NET Framework、Silverlight、Windows Phone 和 [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] 应用，如下图所示。  
  
 ![可移植的 MVVM 关系图](../../../docs/standard/cross-platform/media/portablemvvmdiagram.png "PortableMVVMdiagram")  
  
 本主题不提供有关 MVVM 模式的一般信息。 它仅提供有关如何使用信息[!INCLUDE[net_portable](../../../includes/net-portable-md.md)]实现 MVVM。 MVVM 有关的详细信息，请参阅[MVVM 快速入门](https://msdn.microsoft.com/library/gg430869(v=PandP.40).aspx)。  
  
## <a name="classes-that-support-mvvm"></a>支持 MVVM 类  
 当针对[!INCLUDE[net_v45](../../../includes/net-v45-md.md)]， [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)]，Silverlight 或为 Windows Phone 7.5 你[!INCLUDE[net_portable](../../../includes/net-portable-md.md)]项目中，下面的类是可用于实现 MVVM 模式：  
  
-   <xref:System.Collections.ObjectModel.ObservableCollection%601?displayProperty=nameWithType> 类  
  
-   <xref:System.Collections.ObjectModel.ReadOnlyObservableCollection%601?displayProperty=nameWithType> 类  
  
-   <xref:System.Collections.Specialized.INotifyCollectionChanged?displayProperty=nameWithType> 类  
  
-   <xref:System.Collections.Specialized.NotifyCollectionChangedAction?displayProperty=nameWithType> 类  
  
-   <xref:System.Collections.Specialized.NotifyCollectionChangedEventArgs?displayProperty=nameWithType> 类  
  
-   <xref:System.Collections.Specialized.NotifyCollectionChangedEventHandler?displayProperty=nameWithType> 类  
  
-   <xref:System.ComponentModel.DataErrorsChangedEventArgs?displayProperty=nameWithType> 类  
  
-   <xref:System.ComponentModel.INotifyDataErrorInfo?displayProperty=nameWithType> 类  
  
-   <xref:System.ComponentModel.INotifyPropertyChanged?displayProperty=nameWithType> 类  
  
-   <xref:System.Windows.Input.ICommand?displayProperty=nameWithType> 类  
  
-   中的所有类<xref:System.ComponentModel.DataAnnotations?displayProperty=nameWithType>命名空间  
  
## <a name="implementing-mvvm"></a>实现 MVVM  
 若要实现 MVVM，你通常创建模型，以及在视图模型[!INCLUDE[net_portable](../../../includes/net-portable-md.md)]项目，因为[!INCLUDE[net_portable](../../../includes/net-portable-md.md)]项目不能引用不可移植项目。 模型和视图模型可以是同一项目中或在单独的项目。 如果你使用单独的项目，从视图模型项目模型项目添加引用。  
  
 编译模型和查看模型项目后，你将引用的包含视图的应用中的这些程序集。 如果该视图仅与视图模型交互时，只需引用包含视图模型的程序集。  
  
### <a name="model"></a>模型  
 下面的示例演示可驻留在一个简化的模型类[!INCLUDE[net_portable](../../../includes/net-portable-md.md)]项目。  
  
 [!code-csharp[PortableClassLibraryMVVM#1](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/customer.cs#1)]
 [!code-vb[PortableClassLibraryMVVM#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customer.vb#1)]  
  
 下面的示例演示一种简单的方法，以填充、 检索和更新中的数据[!INCLUDE[net_portable](../../../includes/net-portable-md.md)]项目。 在实际应用中，将从 Windows Communication Foundation (WCF) 服务等源检索数据。  
  
 [!code-csharp[PortableClassLibraryMVVM#2](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/customerrepository.cs#2)]
 [!code-vb[PortableClassLibraryMVVM#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customerrepository.vb#2)]  
  
### <a name="view-model"></a>视图模型  
 在实现 MVVM 模式时，经常会添加的查看模型的基类。 下面的示例演示的基类。  
  
 [!code-csharp[PortableClassLibraryMVVM#3](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/viewmodelbase.cs#3)]
 [!code-vb[PortableClassLibraryMVVM#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/viewmodelbase.vb#3)]  
  
 实现<xref:System.Windows.Input.ICommand>接口经常用于 MVVM 模式。 下面的示例演示 <xref:System.Windows.Input.ICommand> 接口的实现。  
  
 [!code-csharp[PortableClassLibraryMVVM#4](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/relaycommand.cs#4)]
 [!code-vb[PortableClassLibraryMVVM#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/relaycommand.vb#4)]  
  
 下面的示例显示了一个简化的视图模型。  
  
 [!code-csharp[PortableClassLibraryMVVM#5](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/mainpageviewmodel.cs#5)]
 [!code-vb[PortableClassLibraryMVVM#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customerviewmodel.vb#5)]  
  
### <a name="view"></a>视图  
 从[!INCLUDE[net_v45](../../../includes/net-v45-md.md)]应用，[!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]应用程序、 基于 Silverlight 的应用或 Windows Phone 7.5 应用，你可以引用包含模型和视图模型项目的程序集。  然后与视图模型配合创建交互的视图。 下面的示例演示一个简化的 Windows Presentation Foundation (WPF) 应用，检索更新视图模型中的数据。 你可以创建 Silverlight，Windows Phone 中的类似视图或[!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]应用。  
  
 [!code-xaml[PortableClassLibraryMVVM#6](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/mainwindow.xaml#6)]  
  
## <a name="see-also"></a>请参阅  
 [可移植类库](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md)
