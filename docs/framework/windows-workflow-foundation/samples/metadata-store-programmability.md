---
title: 源数据存储可编程性
ms.date: 03/30/2017
ms.assetid: 5b613661-f3f9-4e07-8e88-28c9ea2fd8f8
ms.openlocfilehash: 9f30fcdac131b8749a4d165875b9bbb584542843
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2018
ms.locfileid: "47088199"
---
# <a name="metadata-store-programmability"></a>源数据存储可编程性
元数据存储是一项 [!INCLUDE[wfd1](../../../../includes/wfd1-md.md)] 功能，可用于将任意元数据关联（以 CLR 特性的形式）运行时类型。 这可以实现运行时组件与其设计时对应项之间的松散耦合，并且可以实现在不影响运行时的情况下更改设计时组件。 此示例演示如何通过对运行时类型（我们无法控制的源）应用特性来针对元数据存储进行编程。 通常使用的术语是，主机应用程序为一组类型注册元数据。  
  
 在输出中，您可能会注意到一个附加的、意外的特性 <xref:System.Runtime.InteropServices.GuidAttribute>。 此特性是在使用元数据 API 时添加的，对示例的运行没有任何影响。  
  
 此示例演示：  
  
## <a name="demonstrates"></a>演示  
  
-   使用元数据存储 API 注入特性。  
  
-   使用回调机制延迟元数据注册。  
  
## <a name="to-set-up-build-and-run-the-sample"></a>设置、生成和运行示例
  
1.  使用 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 打开 ProgrammingMetadataStore.sln 解决方案文件。  
  
2.  要生成解决方案，按 Ctrl+Shift+B。  
  
3.  若要运行解决方案，请按 F5。  
  
> [!IMPORTANT]
>  您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。 此示例位于以下目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\CustomActivityDesigners\MetadataStore`