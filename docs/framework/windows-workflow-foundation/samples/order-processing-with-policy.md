---
title: "使用策略的订单处理"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 66833724-dc36-4fad-86b0-59ffeaa3ba6a
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 6202d17741c276c03e80cedd979cbcf2f39ccc1f
ms.sourcegitcommit: 5177d6ae2e9baf026f07ee0631556700a5a193f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="order-processing-with-policy"></a>使用策略的订单处理
订单处理策略示例演示了 Windows Workflow Foundation (WF) 的 [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] 中引入的一些主要功能。 以下功能对 WF 规则引擎而言是新功能：  
  
-   支持运算符重载。  
  
-   支持 `new` 运算符，允许用户从 WF 规则创建新的对象和数组。  
  
-   支持扩展方法，使用户能够从与 C# 编码样式兼容的 WF 规则中调用扩展方法。  
  
> [!NOTE]
>  此示例需要安装 [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)]才能生成和运行。 若要打开项目和解决方案文件，需要使用 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]。  
  
 此示例演示了一个 `OrderProcessingPolicy` 项目，在该项目中输入客户订单和邮政编码，订单包括一份可用项的编号列表。 如果两项输入均正确，则订单将成功处理；否则，策略会创建错误对象，并利用重载 `+` 运算符和预定义的扩展方法将该错误通知给用户。  
  
> [!NOTE]
>  [!INCLUDE[crabout](../../../../includes/crabout-md.md)]扩展方法，请参阅[C# 3.0 版规范](http://go.microsoft.com/fwlink/?LinkId=95402)。  
  
 该示例由下列项目组成：  
  
-   `OrderErrorLibrary`  
  
     `OrderErrorLibrary` 是一个类库，定义了 `OrderError` 和 `OrderErrorCollection` 类。 输入无效时，将创建一个 `OrderError` 实例。 此库也在 `OrderErrorCollection` 类上提供扩展方法，该方法输出 `ErrorText` 中所有 `OrderError` 对象上的 `OrderErrorCollection` 属性。  
  
-   `OrderProcessingPolicy`  
  
     `OrderProcessingPolicy` 项目是一个 WF 控制台应用程序，定义单个 `PolicyFromFile` 活动。 该活动包含下列规则：  
  
    -   `invalidItemNum`  
  
         此规则验证项编号是否介于 1 和 6（包含 1 和 6）之间。 如果项编号在有效范围内，则该规则不会进行任何操作（除了输出到控制台）。 如果项编号未介于 1 和 6 之间，则 `invalidItemNum` 规则将进行下列操作：  
  
        1.  创建一个新的 `OrderError` 对象，将输入的项编号传递给该对象，并在对象上设置 `ErrorText` 和 `CustomerName` 属性。  
  
        2.  创建一个 `invalidItemNumErrorCollection` 对象。  
  
        3.  将新创建的 `OrderError` 实例添加到 `invalidItemNumErrorCollection`。  
  
         这表明支持 `new` 运算符，您可以使用该运算符在规则内进行对象的实例化。  
  
    -   `invalidZip`  
  
         此规则验证邮政编码是否有 5 个数字，并且是否在 600 到 99998 的范围内。 如果邮政编码在有效范围内，则该规则不会进行任何操作（除了输出到控制台）。 如果邮政编码的长度小于 5 或不在 00600 和 99998 之间，则 `invalidZip` 规则将执行以下操作：  
  
        1.  创建一个 `OrderError` 对象，将输入的邮政编码传递给该对象，并在该对象上设置 `ErrorText` 和 `CustomerName` 属性。  
  
        2.  创建一个 `invalidZipCodeErrorCollection` 对象。  
  
        3.  将新创建的 `OrderError` 实例添加到新创建的 `invalidZipCodeErrorCollection`。  
  
         此规则再次表明支持 `new` 运算符，因此您可以在规则内进行对象的实例化。  
  
    -   `displayErrors`  
  
         此规则检查前两个规则是否将任何错误添加到了两个 `OrderErrorCollection` 对象 `invalidItemNumErrorCollection` 和 `invalidIZipCodeErrorCollection` 中。 如果存在错误（`invalidItemNumErrorCollection` 或 `invalidZipCodeErrorCollection` 不为 `null`），则规则将进行下列操作：  
  
        1.  调用重载`+`运算符的内容复制`invalidItemNumErrorCollection`和`invalidZipCodeErrorCollection`到`invalidOrdersCollection``OrderErrorCollection`实例。  
  
        2.  调用 `PrintOrderErrors` 上的 `invalidOrdersCollection` 扩展方法，并输出 `ErrorText` 中所有 `orderError` 对象上的 `invalidOrdersCollection` 属性。  
  
 `+` 上的重载运算符 `OrderErrorCollection` 在 `OrderErrorCollection` 项目的 `OrderErrorLibrary` 类中进行定义。 它将使用两个 `OrderErrorCollection` 对象，并将这两个对象合并到一个 `OrderErrorCollection` 对象中。  
  
 `PrintOrderErrors` 扩展方法也在 `OrderErrorLibrary` 项目中进行定义。 扩展方法是一项全新的 C# 功能，它使开发人员能够将新方法添加到现有 CLR 类型的公共协定中，而不必再从它派生子类或重新编译原始类型。  
  
 当您运行示例时，系统将提示您输入名称、要采购项目的项编号和邮政编码。 此信息随后将由在策略活动中定义的规则进行验证。 下面是来自程序的示例输出。  
  
```  
Please enter your name: John  
  
What would you like to purchase?  
        (1) Vista Ultimate DVD  
        (2) Vista Ultimate Upgrade DVD  
        (3) Vista Home Premium DVD  
        (4) Vista Home Premium Upgrade DVD  
        (5) Vista Home Basic DVD  
        (6) Vista Home Basic Upgrade DVD  
  
Please enter an item number: 1  
  
Please enter your 5-Digit zip code: 98102  
  
        Executing Rule: invalidItemNum  
        Executing Rule: invalidZip  
        Executing Rule: displayErrors  
  
                              Thank you for your order, it has been processed.  
  
Workflow Completed  
Another Order? (Y/N): y  
  
Please enter your name: Joel  
  
What would you like to purchase?  
        (1) Vista Ultimate DVD  
        (2) Vista Ultimate Upgrade DVD  
        (3) Vista Home Premium DVD  
        (4) Vista Home Premium Upgrade DVD  
        (5) Vista Home Basic DVD  
        (6) Vista Home Basic Upgrade DVD  
  
Please enter an item number: 8  
  
Please enter your 5-Digit zip code: 0000  
  
        Executing Rule: invalidItemNum  
        Executing Rule: invalidZip  
        Executing Rule: displayErrors  
  
                              Your order contains the following error(s)  
  
Error: No item number found. Please choose an available item.  
Error: Invalid zip code. Please choose a zip code between 00600 and 99998.  
  
Workflow Completed  
Another Order? (Y/N): n  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a>设置、生成和运行示例  
  
1.  在 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 中打开 OrderProcessingPolicy.sln 项目文件。  
  
2.  解决方案中有两个不同的项目：`OrderErrorLibrary` 和 `OrderProcessingPolicy`。 `OrderProcessingPolicy` 项目使用在 `OrderErrorLibrary` 中定义的类和方法。  
  
3.  生成所有项目。  
  
4.  单击“运行” 。  
  
> [!IMPORTANT]
>  您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。 此示例位于以下目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Rules\Policy\OrderProcessingPolicy`