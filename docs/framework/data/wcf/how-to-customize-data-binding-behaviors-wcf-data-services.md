---
title: "如何：自定义数据绑定行为（WCF 数据服务）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, customizing
- WCF Data Services, data binding
ms.assetid: 40476b89-8941-4771-8d21-2fe430c85a9d
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 1ee72c905ab6df222d256eeeeb2a59579e82923b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-customize-data-binding-behaviors-wcf-data-services"></a>如何：自定义数据绑定行为（WCF 数据服务）
通过 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]，您可以提供当向绑定集合中添加对象或从中移除对象时或检测到属性更改时由 <xref:System.Data.Services.Client.DataServiceCollection%601> 调用的自定义逻辑。 此自定义逻辑作为方法，作为引用提供<xref:System.Func%602>委托，返回的值`false`时的默认行为仍应执行的自定义方法完成时和`true`时后续处理应停止事件。  
  
 本主题中的示例为 `entityChanged` 的 `entityCollectionChanged` 和 <xref:System.Data.Services.Client.DataServiceCollection%601> 参数提供了自定义方法。 本主题中的示例使用 Northwind 示例数据服务和自动生成的客户端数据服务类。 在完成时创建此服务和客户端数据类[WCF 数据服务快速入门](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)。  
  
## <a name="example"></a>示例  
 下面的 XAML 文件代码隐藏页使用当更改绑定到绑定集合的数据时调用的自定义方法来创建 <xref:System.Data.Services.Client.DataServiceCollection%601>。 当发生 <xref:System.Collections.ObjectModel.ObservableCollection%601.CollectionChanged> 事件时，提供的方法阻止从数据服务删除已从绑定集合移除的项。 当发生 <xref:System.Collections.ObjectModel.ObservableCollection%601.PropertyChanged> 事件时，验证 `ShipDate` 值以确保不对已发货的订单进行更改。  
  
 [!code-csharp[Astoria Northwind Client#WpfDataBindingCustom](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/customerorderscustom.xaml.cs#wpfdatabindingcustom)]
 [!code-vb[Astoria Northwind Client#WpfDataBindingCustom](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerorderscustom.xaml.vb#wpfdatabindingcustom)]
 [!code-vb[Astoria Northwind Client#WpfDataBindingCustom](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerorderscustom2.xaml.vb#wpfdatabindingcustom)]  
  
## <a name="example"></a>示例  
 下面的 XAML 定义上例的窗口。  
  
 [!code-xaml[Astoria Northwind Client#WpfDataBindingCustomXaml](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerorderscustom.xaml#wpfdatabindingcustomxaml)]  
  
## <a name="see-also"></a>另请参阅  
 [WCF Data Services 客户端库](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)
