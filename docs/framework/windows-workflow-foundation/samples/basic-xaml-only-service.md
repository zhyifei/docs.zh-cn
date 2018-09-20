---
title: 基本的只包含 XAML 的服务
ms.date: 03/30/2017
ms.assetid: c106feb0-0245-43b5-aefe-93ce0e4d38eb
ms.openlocfilehash: f4f296a97b9c3093874c5ec8e05023e84b0af44a
ms.sourcegitcommit: 3ab9254890a52a50762995fa6d7d77a00348db7e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2018
ms.locfileid: "46489742"
---
# <a name="basic-xaml-only-service"></a>基本的只包含 XAML 的服务
此示例演示如何创建只包含 XAML 服务。 此方案是一个用于解决车辆相关故障的诊断服务。 此服务作为一个工作流实现，它会向客户端询问一系列问题来诊断故障。 此服务可诊断两种类型的故障（车辆无法启动或空调无法工作）。 工作流使用设计器中的请求/答复模板来公开三个简单的服务操作。 通过在 IIS 中创建虚拟目录以及将 service1.xamlx 和 Web.config 文件复制到虚拟目录中，在 IIS 中承载服务，而无需编译的代码。 默认情况下此示例将自动将所需的文件复制到虚拟目录创建时遵循的 WCF 和 WF 示例的安装说明： [WindowsCommunicationFoundation示例的一次性安装过程](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) Visual Studio 2010 中生成时。  
  
#### <a name="to-use-this-sample"></a>使用此示例  
  
1.  在 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 中加载项目解决方案，然后生成项目。  
  
2.  运行在 [解决方案基目录]\Client\bin\debug 中生成的 Client 应用程序。  
  
3.  该应用程序输出多个选项，选择一个选项。 然后，该应用程序会询问一些问题，使用“是”或“否”（使用 Y/N 键）来回答问题。 当服务完成故障诊断之后，该应用程序输出诊断结果。  
  
4.  该应用程序返回到选项页面。 您可诊断下一个故障或退出该应用程序。  
  
> [!IMPORTANT]
>  您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。 此示例位于以下目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\XAMLService`