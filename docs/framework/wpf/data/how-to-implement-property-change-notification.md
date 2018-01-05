---
title: "如何：实现属性更改通知"
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
- notifications of change [WPF]
- data binding [WPF], property change notifications
- change notifications [WPF]
- properties [WPF], change notifications
ms.assetid: 30b59d9e-8c3a-4349-aa82-4be837e841cf
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f6628ec27ab381f52a086cac3f8d0cd92aea2cd8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-implement-property-change-notification"></a><span data-ttu-id="1a2ca-102">如何：实现属性更改通知</span><span class="sxs-lookup"><span data-stu-id="1a2ca-102">How to: Implement Property Change Notification</span></span>
<span data-ttu-id="1a2ca-103">若要支持<xref:System.Windows.Data.BindingMode.OneWay>或<xref:System.Windows.Data.BindingMode.TwoWay>绑定，从而使你的绑定目标属性，以便自动反映绑定源 （例如具有预览窗格中，当用户编辑窗体时自动更新），动态更改您的类需要提供相应的属性更改通知。</span><span class="sxs-lookup"><span data-stu-id="1a2ca-103">To support <xref:System.Windows.Data.BindingMode.OneWay> or <xref:System.Windows.Data.BindingMode.TwoWay> binding to enable your binding target properties to automatically reflect the dynamic changes of the binding source (for example, to have the preview pane updated automatically when the user edits a form), your class needs to provide the proper property changed notifications.</span></span> <span data-ttu-id="1a2ca-104">此示例演示如何创建一个类以实现<xref:System.ComponentModel.INotifyPropertyChanged>。</span><span class="sxs-lookup"><span data-stu-id="1a2ca-104">This example shows how to create a class that implements <xref:System.ComponentModel.INotifyPropertyChanged>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1a2ca-105">示例</span><span class="sxs-lookup"><span data-stu-id="1a2ca-105">Example</span></span>  
 <span data-ttu-id="1a2ca-106">若要实现<xref:System.ComponentModel.INotifyPropertyChanged>则需要声明<xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged>事件并创建`OnPropertyChanged`方法。</span><span class="sxs-lookup"><span data-stu-id="1a2ca-106">To implement <xref:System.ComponentModel.INotifyPropertyChanged> you need to declare the <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> event and create the `OnPropertyChanged` method.</span></span> <span data-ttu-id="1a2ca-107">然后，对于每个需要更改通知的属性，只要进行了更新，就可以调用 `OnPropertyChanged`。</span><span class="sxs-lookup"><span data-stu-id="1a2ca-107">Then for each property you want change notifications for, you call `OnPropertyChanged` whenever the property is updated.</span></span>  
  
 [!code-csharp[SimpleBinding#PersonClass](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Person.cs#personclass)]
 [!code-vb[SimpleBinding#PersonClass](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Person.vb#personclass)]  
  
 <span data-ttu-id="1a2ca-108">若要查看如何的示例`Person`类可以用于支持<xref:System.Windows.Data.BindingMode.TwoWay>绑定，请参阅[控制文本框文本更新后，源](../../../../docs/framework/wpf/data/how-to-control-when-the-textbox-text-updates-the-source.md)。</span><span class="sxs-lookup"><span data-stu-id="1a2ca-108">To see an example of how the `Person` class can be used to support <xref:System.Windows.Data.BindingMode.TwoWay> binding, see [Control When the TextBox Text Updates the Source](../../../../docs/framework/wpf/data/how-to-control-when-the-textbox-text-updates-the-source.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a2ca-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="1a2ca-109">See Also</span></span>  
 [<span data-ttu-id="1a2ca-110">绑定源概述</span><span class="sxs-lookup"><span data-stu-id="1a2ca-110">Binding Sources Overview</span></span>](../../../../docs/framework/wpf/data/binding-sources-overview.md)  
 [<span data-ttu-id="1a2ca-111">数据绑定概述</span><span class="sxs-lookup"><span data-stu-id="1a2ca-111">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="1a2ca-112">帮助主题</span><span class="sxs-lookup"><span data-stu-id="1a2ca-112">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
