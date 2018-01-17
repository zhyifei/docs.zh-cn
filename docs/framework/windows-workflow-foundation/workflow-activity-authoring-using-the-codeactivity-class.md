---
title: "使用 CodeActivity 类的工作流活动创作"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cfe315c1-f86d-43ec-b9ce-2f8c469b1106
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2daec260c1224cd81280c6bf699b70efc2072588
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="workflow-activity-authoring-using-the-codeactivity-class"></a>使用 CodeActivity 类的工作流活动创作
从 <xref:System.Activities.CodeActivity> 继承而创建的活动可以通过重写 <xref:System.Activities.CodeActivity.Execute%2A> 方法来实现基本的命令性行为。  
  
## <a name="using-codeactivitycontext"></a>使用 CodeActivityContext  
 通过使用类型为 <xref:System.Activities.CodeActivity.Execute%2A> 的 `context` 参数的成员，可从 <xref:System.Activities.CodeActivityContext> 方法中访问工作流运行时的功能。 可通过 <xref:System.Activities.CodeActivityContext> 使用的功能如下：  
  
-   获取并设置变量和参数的值。  
  
-   使用 <xref:System.Activities.CodeActivityContext.Track%2A> 的自定义跟踪功能。  
  
-   使用 <xref:System.Activities.CodeActivityContext.GetProperty%2A> 访问活动的执行属性。  
  
#### <a name="to-create-a-custom-activity-that-inherits-from-codeactivity"></a>创建从 CodeActivity 继承的自定义活动  
  
1.  打开 [!INCLUDE[vs2010](../../../includes/vs2010-md.md)]。  
  
2.  选择**文件**，**新**，，然后**项目**。 选择**Workflow 4.0**下**Visual C#**中**项目类型**窗口中，然后选择**v2010**节点。 选择**活动库**中**模板**窗口。 将新项目命名为 HelloActivity。  
  
3.  右击 HelloActivity 项目中的 Activity1.xaml，然后选择**删除**。  
  
4.  右击 HelloActivity 项目并选择**添加**，，然后**类**。 将新类命名为 HelloActivity.cs。  
  
5.  在 HelloActivity.cs 文件中，添加以下 `using` 指令。  
  
    ```csharp  
    using System.Activities;  
    using System.Activities.Statements;  
    ```  
  
6.  通过向类声明中添加一个基类使新类从 <xref:System.Activities.CodeActivity> 继承。  
  
    ```csharp  
    class HelloActivity : CodeActivity  
    ```  
  
7.  通过添加 <xref:System.Activities.CodeActivity.Execute%2A> 方法来向类中添加功能。  
  
    ```csharp  
    protected override void Execute(CodeActivityContext context)  
    {  
        Console.WriteLine("Hello World!");  
    }  
    ```  
  
8.  使用 <xref:System.Activities.CodeActivityContext> 创建一个跟踪记录。  
  
    ```csharp  
    protected override void Execute(CodeActivityContext context)  
    {  
        Console.WriteLine("Hello World!");  
        CustomTrackingRecord record = new CustomTrackingRecord("MyRecord");  
        record.Data.Add(new KeyValuePair<String, Object>("ExecutionTime", DateTime.Now));  
        context.Track(record);  
    }  
    ```
