---
title: "使用 InvokeMethod 活动"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b6643550-d043-4ac7-8069-9c55ebbb4233
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: aacc20bf483877ac501fd8b35c04f6e3f9311afb
ms.sourcegitcommit: 5177d6ae2e9baf026f07ee0631556700a5a193f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="using-the-invokemethod-activity"></a>使用 InvokeMethod 活动
此示例演示如何使用<!--zz <xref:System.Activities.Statements.InvokeMethod%601> --> [ <code>System.Activities.Statements.InvokeMethod\`1</code> ](https://msdn.microsoft.com/library/dd647677.aspx)活动调用公共类中的公共方法。 <!--zz <xref:System.Activities.Statements.InvokeMethod%601> --> [ <code>System.Activities.Statements.InvokeMethod\`1</code> ](https://msdn.microsoft.com/library/dd647677.aspx)活动允许工作流针对对象调用方法、 传入参数、 获取返回值、 指定泛型方法的类型和指定的方法是同步或异步。 
  
没有一个非泛型版本<xref:System.Activities.Statements.InvokeMethod>其中的返回值设置为活动<xref:System.Activities.Statements.InvokeMethod.Result%2A>属性和一个泛型版本<!--zz <xref:System.Activities.Statements.InvokeMethod%601> --> [ <code>System.Activities.Statements.InvokeMethod\`1</code> ](https://msdn.microsoft.com/library/dd647677.aspx)其中返回的返回值的活动通过<!--zz <xref:System.Activities.Statements.InvokeMethod.Result%601.Result%2A> --> [ <code>System.Activities.Statements.InvokeMethod\`1.Result</code> ](https://msdn.microsoft.com/library/dd987724.aspx)类型的属性`TResult`。 
  
 此示例演示如何调用各种不同的方法类型。 下面的列表详细介绍了此示例中演示的方法类型：  
  
-   调用不含参数的实例方法。  
  
-   调用含有两个参数（System.String 和 System.Int32）的实例方法。  
  
-   调用含有两个参数（System.String 和 System.Int32）和一个 System.String[] 类型的参数数组的实例方法。  
  
-   调用含有两个参数（两个 System.Int32 数）和一个 System.Int32 类型的结果的实例方法。  
  
     使用 <xref:System.Activities.Statements.WriteLine> 活动将返回值绑定到一个变量，并输出到控制台。  
  
-   调用含有两个参数（System.String 和 System.Int32）的静态方法。  
  
-   调用含有一个泛型参数 (System.String) 的实例方法。  
  
-   调用含有两个泛型参数（System.String 和 System.Int32）的静态方法。  
  
-   调用包含一个按引用传递的参数的 (System.String) 实例方法。  
  
     使用 <xref:System.Activities.Statements.WriteLine> 活动将引用的参数绑定到一个变量，并输出到控制台。  
  
-   调用异步的实例方法。  
  
## <a name="to-use-this-sample"></a>使用此示例  
  
1.  使用 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 打开 InvokeMethodUsage.sln 解决方案文件。  
  
2.  要生成解决方案，按 Ctrl+Shift+B。  
  
3.  若要运行解决方案，请按 Ctrl+F5。  
  
> [!IMPORTANT]
>  您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。 此示例位于以下目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\InvokeMethod`