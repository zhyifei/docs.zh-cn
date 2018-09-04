---
title: RangeEnumeration 活动
ms.date: 03/30/2017
ms.assetid: ca5b78f4-94fa-4aa7-830d-26039ac422c8
ms.openlocfilehash: c9cf522227620422b414adc26cbc0bf338bf57d4
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43556287"
---
# <a name="rangeenumeration-activity"></a>RangeEnumeration 活动
此示例演示如何创建一个用于循环访问数字集合的自定义活动。下表详细描述了此示例中包含的主要文件。  
  
|文件名|描述|  
|---------------|-----------------|  
|RangeEnumeration.cs|定义一个名为 `RangeEnumeration` 的自定义活动，该活动重写 <xref:System.Activities.NativeActivity> 类，并循环访问一系列数字。|  
|RangeEnumerationSample.cs|一个使用 `RangeEnumeration` 活动循环访问数字集合的客户端应用程序。|  
  
 下表详细描述了 `RangeEnumeration` 活动的属性。  
  
|属性|描述|  
|--------------|-----------------|  
|Start|开始循环的整数。|  
|停止|停止循环的整数。|  
|步骤|指定每次循环访问的步长。|  
|Body|指定每次循环访问期间要执行的代码。|  
  
#### <a name="to-use-this-sample"></a>使用此示例  
  
1.  使用 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 打开 RangeEnumeration.sln 解决方案文件。  
  
2.  要生成解决方案，按 Ctrl+Shift+B。  
  
3.  若要运行解决方案，请按 Ctrl+F5。  
  
> [!IMPORTANT]
>  您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。 此示例位于以下目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\RangeEnumeration`