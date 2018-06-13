---
title: ByteStream 编码器
ms.date: 03/30/2017
ms.assetid: e674a8ab-f79a-4a93-b984-54b34392dafc
ms.openlocfilehash: ab9ccf47527dcf7f01f272f09b3b341d30fbd8d3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33499675"
---
# <a name="bytestream-encoder"></a>ByteStream 编码器
本示例演示如何创建 `ByteStreamHttpBinding`，这是一个演示字节流编码器功能的 <xref:System.ServiceModel.Channels.Binding>。  
  
## <a name="discussion"></a>讨论  
 本示例演示如何使用标准绑定元素 <xref:System.ServiceModel.Channels.Binding> 和 <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement> 创建标准 <xref:System.ServiceModel.Channels.HttpTransportBindingElement>。 本示例演示如何使用字节流编码器上载和下载图像。 字节流编码器功能只支持 HTTP 传输，不支持诸如可靠消息传递或安全性此类的功能。 唯一支持的 <xref:System.ServiceModel.Channels.MessageVersion> 是 <xref:System.ServiceModel.Channels.MessageVersion.None%2A>。  
  
> [!IMPORTANT]
>  如果在 [!INCLUDE[windowsver](../../../../includes/windowsver-md.md)] 或 [!INCLUDE[win7_client_firstref](../../../../includes/win7-client-firstref-md.md)] 中运行本示例，请确保使用提升的特权运行 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]。  
  
> [!IMPORTANT]
>  您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和针对.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780)下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。 此示例位于以下目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Binding\ByteStreamEncoder`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>设置、生成和运行示例  
  
1.  在 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 中打开 ByteStreamHttpBinding.sln 文件。  
  
2.  通过右键单击解决方案资源管理器中的项目并选择开始 ByteStreamHttpBindingServer 项目的新实例**调试**，，然后**启动新实例**从上下文菜单。  
  
3.  通过右键单击解决方案资源管理器中的项目并选择开始 ByteStreamHttpBindingClient 项目的新实例**调试**，**启动新实例**从上下文菜单。
