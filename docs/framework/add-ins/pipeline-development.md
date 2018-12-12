---
title: 管线开发
ms.date: 03/30/2017
helpviewer_keywords:
- add-in pipeline [.NET Framework], segments
- activation path for add-ins [.NET Framework]
- add-in pipeline [.NET Framework], activation path
- communication pipeline for add-ins [.NET Framework]
- add-in pipeline [.NET Framework], about
- add-ins [.NET Framework], pipeline development
ms.assetid: 932788f2-b87d-44cf-82f9-04492a8b2722
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f981d667f3cbf35ab010ac5bd26a9ecd5c2aae11
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53151338"
---
# <a name="pipeline-development"></a>管线开发
外接程序管道是主机应用程序和其外接程序必须使用与彼此进行通信的管线段的路径。  
  
 下图显示通信管道和其段。  
  
 ![添加&#45;管道模型中。](../../../docs/framework/add-ins/media/addin1.png "AddIn1")  
外接程序管道  
  
 主机应用程序是某一端的管道和外接程序是在另一端。 从每个端开始，向中间移动，主机应用程序和外接程序具有一个抽象基类，定义它们共享的对象模型的视图。 这些类型 （类） 构成了外接程序视图管道段和外接程序管线段的宿主视图。 外接程序视图管道段通常包含多个抽象类，但外接程序继承的类名为外接程序基。  
  
 外接程序端适配器管道段和主机端适配器管道段 convert 其视图管道段和协定管道段之间的类型的流。 管道的中央段是派生自的协定<xref:System.AddIn.Contract.IContract>接口。 此协定定义主机应用程序和其外接程序将同时使用的方法。  
  
 如果将主机和外接程序加载到单独的应用程序域，则可以隔离边界分隔主机应用程序从作用域外接程序的作用域。 协定是在主机和外接程序应用程序域中加载的唯一程序集。 主机和外接程序都仅涉及其协定方法的视图。 因此，它们之间用一个约定的抽象层。  
  
 若要开发管道段，必须创建将包含它们的目录结构。 有关开发要求和作用域指南的详细信息，请参阅[管线开发要求](https://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5)。  
  
 下图显示构成的管线段的类型。 在图中所示的类型的名称是任意的但除主机和主机以外的所有类型都视图的外接程序需要特性以使它们可以发现构造的信息存储区的方法。  
  
 ![添加&#45;在模型中具有必需特性的类型。](../../../docs/framework/add-ins/media/addin-model.png "AddIn_Model")  
外接程序管道，其中包含类型  
  
 下表描述了用于激活外接程序管线段。 有关这些段的详细信息，请参阅[协定、 视图和适配器](https://msdn.microsoft.com/library/a6460173-9507-4b87-8c07-d4ee245d715c)。  
  
|管道段|描述|  
|----------------------|-----------------|  
|Host|创建的外接程序实例应用程序程序集。|  
|宿主视图的外接程序|表示主机应用程序的视图的对象类型和方法用于与外接程序进行通信。 宿主视图是一个抽象基类或接口。|  
|主机端适配器|调整方法与协定程序集与一个或多个类。<br /><br /> 此管道段由使用<xref:System.AddIn.Pipeline.HostAdapterAttribute>属性。<br /><br /> 不支持多模块程序集。|  
|协定|派生自的接口<xref:System.AddIn.Contract.IContract>接口，并定义用于在主机和其外接程序之间的通信类型的协议。<br /><br /> 此管道段由设置<xref:System.AddIn.Pipeline.AddInContractAttribute>属性。|  
|的外接程序端适配器|调整方法与协定程序集与一个或多个类。<br /><br /> 此管道段由使用<xref:System.AddIn.Pipeline.AddInAdapterAttribute>属性。<br /><br /> 包含具有的类型的外接程序端适配器目录中的每个程序集<xref:System.AddIn.Pipeline.AddInAdapterAttribute>属性加载到外接程序的应用程序域。<br /><br /> 在其自己的应用程序域中是加载外接程序端目录中的每个程序集。<br /><br /> 不支持多模块程序集|  
|外接程序视图|表示外接程序的视图的对象类型和用于与主机通信的方法的程序集。 外接程序视图是一个抽象基类或接口。<br /><br /> 此管道段由使用<xref:System.AddIn.Pipeline.AddInBaseAttribute>属性。<br /><br /> 包含具有的类型的 AddInViews 目录中的每个程序集<xref:System.AddIn.Pipeline.AddInBaseAttribute>属性加载到外接程序的应用程序域。|  
|外接程序|执行某项服务的主机实例化的类型。|  
  
## <a name="pipeline-activation-path"></a>管道激活路径  
 下图显示类型的激活外接程序激活时。 它还显示到主机，如计算或对象的集合的结果的对象的传递。 这是最典型的方案。  
  
 ![添加&#45;在模型中具有激活路径。](../../../docs/framework/add-ins/media/addin6.png "AddIn6")  
从外接程序到主机的激活路径  
  
 管道的激活路径发生，如下所示：  
  
1.  主机应用程序激活外接程序与<xref:System.AddIn.Hosting.AddInToken.Activate%2A>方法。  
  
2.  外接程序、 外接程序视图、 外接程序端适配器和约定程序集加载到外接程序的应用程序域中。  
  
3.  使用外接程序视图创建外接程序端适配器的实例 (与类由标识<xref:System.AddIn.Pipeline.AddInBaseAttribute>属性) 作为其构造函数。 外接程序端适配器从协定继承。  
  
4.  外接程序端适配器，将类型化为协定，在 （可选） 隔离边界传递给宿主端适配器的构造函数。  
  
5.  宿主视图的外接程序、 宿主端适配器和约定程序集加载到主机的应用程序域中。  
  
6.  使用该约定作为其构造函数创建的宿主端适配器实例。 主机端适配器中继承从外接程序的宿主视图。  
  
7.  主机有外接程序，其类型为主机视图外接程序，并可以继续调用其方法。  
  
## <a name="walkthroughs"></a>演练  
 有三个演练主题介绍如何使用 Visual Studio 创建管道：  
  
-   [演练：创建可扩展的应用程序](../../../docs/framework/add-ins/walkthrough-create-extensible-app.md)  
  
     描述一个计算器外接程序，针对主机执行加法、 减法、 乘法和除法的计算的。  
  
-   [演练：启用主机更改为向后的兼容性](https://msdn.microsoft.com/library/6fa15bb5-8f04-407d-bd7d-675dc043c848)  
  
     描述一个计算器外接程序增强的计算功能，以及如何保持与第一个计算器外接程序兼容性。  
  
-   [演练：主机和外接程序之间传递集合](https://msdn.microsoft.com/library/b532c604-548e-4fab-b11c-377257dd0ee5)  
  
     介绍如何通过使用书店方案管道传递的数据集合。  
  
## <a name="see-also"></a>请参阅  
- [外接程序管线方案](https://msdn.microsoft.com/library/feb70e0b-8734-494c-aeaf-b567f014043e)  
- [外接程序和扩展性](../../../docs/framework/add-ins/index.md)
