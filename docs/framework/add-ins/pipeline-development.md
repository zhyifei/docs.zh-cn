---
title: "管线开发"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- add-in pipeline [.NET Framework], segments
- activation path for add-ins [.NET Framework]
- add-in pipeline [.NET Framework], activation path
- communication pipeline for add-ins [.NET Framework]
- add-in pipeline [.NET Framework], about
- add-ins [.NET Framework], pipeline development
ms.assetid: 932788f2-b87d-44cf-82f9-04492a8b2722
caps.latest.revision: "31"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4991fc65a48d620d30d09c44f1a30c2d1839071e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="pipeline-development"></a>管线开发
外接程序管线是主机应用程序和其外接程序必须使用才能相互之间进行通信的管道段的路径。  
  
 下图显示的通信管道和其片段。  
  
 ![添加 &#45; 管道模型中。] (../../../docs/framework/add-ins/media/addin1.png "AddIn1")  
外接程序管道  
  
 主机应用程序是管道的另一端外, 接程序在另一端。 从每个结尾和向中间移动，主机应用程序和外接程序将具有一个定义它们都共享的对象模型的视图的抽象基类。 这些类型 （类） 构成了外接程序视图管道段和外接程序管线段的主机视图。 外接程序视图管道段通常包含多个抽象类，但外接程序继承自的类称为外接程序基准。  
  
 外接程序端适配器管道段和主机端适配器管线段转换其视图管道段和协定管道段之间的类型的流。 中央管道段是派生自协定<xref:System.AddIn.Contract.IContract>接口。 此协定定义主机应用程序和其外接程序将同时使用的方法。  
  
 如果将主机和外接程序加载到单独的应用程序域中，则必须分隔主机应用程序从范围的外接程序的作用域的隔离边界。 协定是在主机和外接程序应用程序域中加载的唯一程序集。 主机和外接程序每个仅引用其视图协定方法。 因此，它们被隔开的从协定的抽象层。  
  
 若要开发管道段，必须创建将包含它们的目录结构。 有关开发要求和作用域准则的详细信息，请参阅[管线开发要求](http://msdn.microsoft.com/en-us/ef9fa986-e80b-43e1-868b-247f4c1d9da5)。  
  
 下图显示构成的管道段的类型。 在图中所示的类型的名称是任意的但主机和主机除外的所有类型都视图之外的外接程序中需要特性使构造信息存储的方法可以发现它们。  
  
 ![添加 &#45; 在模型中具有必需特性的类型。] (../../../docs/framework/add-ins/media/addin-model.png "AddIn_Model")  
类型与外接程序管线  
  
 下表描述了有关激活外接程序中的管道段。 有关这些段的详细信息，请参阅[协定、 视图和适配器](http://msdn.microsoft.com/en-us/a6460173-9507-4b87-8c07-d4ee245d715c)。  
  
|管道段|描述|  
|----------------------|-----------------|  
|Host|为应用程序集创建的外接程序的实例。|  
|外接程序的主机视图|表示对象类型以及用于与外接程序进行通信的方法的主机应用程序的视图。 主机视图是一个抽象基类或接口。|  
|主机端适配器|采用与其他协定的方法与一个或多个类程序集。<br /><br /> 通过标识此管道段<xref:System.AddIn.Pipeline.HostAdapterAttribute>属性。<br /><br /> 不支持多模块程序集。|  
|协定|派生自的接口<xref:System.AddIn.Contract.IContract>接口，并且定义主机和其外接程序之间的通信类型的协议。<br /><br /> 通过设置标识此管道段<xref:System.AddIn.Pipeline.AddInContractAttribute>属性。|  
|的外接程序端适配器|采用与其他协定的方法与一个或多个类程序集。<br /><br /> 通过标识此管道段<xref:System.AddIn.Pipeline.AddInAdapterAttribute>属性。<br /><br /> 包含具有的类型的外接程序端适配器目录中的每个程序集<xref:System.AddIn.Pipeline.AddInAdapterAttribute>属性加载到外接程序的应用程序域。<br /><br /> 在其自己的应用程序域中将会加载外接程序端目录中的每个程序集。<br /><br /> 不支持多模块程序集|  
|外接程序视图|表示外接程序的视图对象类型以及用于与主机通信的方法的程序集。 外接程序视图是一个抽象基类或接口。<br /><br /> 通过标识此管道段<xref:System.AddIn.Pipeline.AddInBaseAttribute>属性。<br /><br /> 包含具有的类型的 AddInViews 目录中的每个程序集<xref:System.AddIn.Pipeline.AddInBaseAttribute>属性加载到外接程序的应用程序域。|  
|外接程序|执行某项服务主机实例化的类型。|  
  
## <a name="pipeline-activation-path"></a>管道激活路径  
 当激活外接程序时下, 图显示类型的激活。 它还显示到主机，如计算或对象的集合的结果的传递的对象。 这是最典型的情形。  
  
 ![添加 &#45; 具有激活路径的模型中。] (../../../docs/framework/add-ins/media/addin6.png "AddIn6")  
从外接程序到宿主的激活路径  
  
 管道的激活路径发生，如下所示：  
  
1.  主机应用程序激活外接程序与<xref:System.AddIn.Hosting.AddInToken.Activate%2A>方法。  
  
2.  外接程序中外, 接程序视图、 外接程序端适配器和协定程序集加载到外接程序的应用程序域中。  
  
3.  使用外接程序视图创建外接程序端适配器的实例 (与类由标识<xref:System.AddIn.Pipeline.AddInBaseAttribute>属性) 作为其构造函数。 外接程序端适配器从协定继承。  
  
4.  外接程序端适配器，将类型化为协定，跨 （可选） 隔离边界传递给主机端适配器的构造函数。  
  
5.  外接程序、 宿主端适配器和协定程序集的主机视图加载到主机的应用程序域中。  
  
6.  使用协定作为其构造函数创建的主机端适配器实例。 主机端适配器继承自的外接程序的主机视图。  
  
7.  主机有外接程序，这类型的主机的外接程序时，查看并可以继续调用其方法。  
  
## <a name="walkthroughs"></a>演练  
 有三个描述如何创建使用 Visual Studio 的管道的演练主题：  
  
-   [演练： 创建可扩展应用程序](../../../docs/framework/add-ins/walkthrough-create-extensible-app.md)  
  
     描述一个计算器外接程序，执行加法、 减法、 乘法和除法计算的主机。  
  
-   [演练： 启用主机更改为向后的兼容性](http://msdn.microsoft.com/en-us/6fa15bb5-8f04-407d-bd7d-675dc043c848)  
  
     描述一个计算器外接程序使用增强的计算功能，以及如何维护与第一个计算器外接程序的兼容性。  
  
-   [主机和外接程序之间的演练： 传递集合](http://msdn.microsoft.com/en-us/b532c604-548e-4fab-b11c-377257dd0ee5)  
  
     描述如何通过使用书店方案管道传递数据集合。  
  
## <a name="see-also"></a>另请参阅  
 [外接程序管线方案](http://msdn.microsoft.com/en-us/feb70e0b-8734-494c-aeaf-b567f014043e)  
 [外接程序和扩展性](../../../docs/framework/add-ins/index.md)
