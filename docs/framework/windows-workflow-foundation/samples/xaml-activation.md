---
title: XAML 激活
ms.date: 03/30/2017
ms.assetid: 486760e2-bb10-4ed5-8c02-fe7472498d2d
ms.openlocfilehash: 8621b0ea7b390c81e76ac7eeedb0b547b44320d7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="xaml-activation"></a>XAML 激活
此示例演示如何在 IIS 中承载声明性工作流。 此示例是一个名为 `EchoService` 的基本工作流，它具有一个操作。  
  
> [!IMPORTANT]
>  您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  如果此目录不存在，请转到 （下载页） 以下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。 此示例位于以下目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\XAMLActivation`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>设置、生成和运行示例  
  
1.  在 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 中打开 XAMLActivation.sln 解决方案。  
  
2.  生成解决方案，按**F5**。  
  
3.  运行 WcfTestClient.exe。 在命令提示符下键入：  
  
    1.  cd %SystemDrive%\Program Files\Microsoft Visual Studio 10.0\Common7\IDE  
  
    2.  运行 WcfTestClient.exe。  
  
4.  设置 wcftestclient.exe 的服务的地址，通过按 CTRL + SHIFT + A 并将服务地址设置为http://localhost:56133/Service.xamlx。  
  
5.  执行 echo 操作以测试服务。  
  
6.  通过管理员特权在命令提示中使用 DeployToIIS.Bat 在 IIS 中部署服务。  
  
7.  在客户端到服务地址更新http://localhost/XAMLActivation/Service.xamlx和测试使用 WcfTestClient.exe 重新此服务。
