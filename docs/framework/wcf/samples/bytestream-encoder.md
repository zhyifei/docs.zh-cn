---
title: "ByteStream 编码器"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e674a8ab-f79a-4a93-b984-54b34392dafc
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d0984d3989d6441c363730454ea65b0393c94b9b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="bytestream-encoder"></a><span data-ttu-id="b5f17-102">ByteStream 编码器</span><span class="sxs-lookup"><span data-stu-id="b5f17-102">ByteStream Encoder</span></span>
<span data-ttu-id="b5f17-103">本示例演示如何创建 `ByteStreamHttpBinding`，这是一个演示字节流编码器功能的 <xref:System.ServiceModel.Channels.Binding>。</span><span class="sxs-lookup"><span data-stu-id="b5f17-103">This sample demonstrates how to create a `ByteStreamHttpBinding`, a <xref:System.ServiceModel.Channels.Binding> that demonstrates the functionality of the byte stream encoder.</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="b5f17-104">讨论</span><span class="sxs-lookup"><span data-stu-id="b5f17-104">Discussion</span></span>  
 <span data-ttu-id="b5f17-105">本示例演示如何使用标准绑定元素 <xref:System.ServiceModel.Channels.Binding> 和 <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement> 创建标准 <xref:System.ServiceModel.Channels.HttpTransportBindingElement>。</span><span class="sxs-lookup"><span data-stu-id="b5f17-105">This sample demonstrates how to create a standard <xref:System.ServiceModel.Channels.Binding> using the standard binding elements <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement> and <xref:System.ServiceModel.Channels.HttpTransportBindingElement>.</span></span> <span data-ttu-id="b5f17-106">本示例演示如何使用字节流编码器上载和下载图像。</span><span class="sxs-lookup"><span data-stu-id="b5f17-106">This sample shows how to use the byte stream encoder to upload and download an image.</span></span> <span data-ttu-id="b5f17-107">字节流编码器功能只支持 HTTP 传输，不支持诸如可靠消息传递或安全性此类的功能。</span><span class="sxs-lookup"><span data-stu-id="b5f17-107">The byte stream encoder feature only supports the HTTP transport and it does not support features such as reliable messaging or security.</span></span> <span data-ttu-id="b5f17-108">唯一支持的 <xref:System.ServiceModel.Channels.MessageVersion> 是 <xref:System.ServiceModel.Channels.MessageVersion.None%2A>。</span><span class="sxs-lookup"><span data-stu-id="b5f17-108">The only <xref:System.ServiceModel.Channels.MessageVersion> supported is <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b5f17-109">如果在 [!INCLUDE[windowsver](../../../../includes/windowsver-md.md)] 或 [!INCLUDE[win7_client_firstref](../../../../includes/win7-client-firstref-md.md)] 中运行本示例，请确保使用提升的特权运行 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b5f17-109">If you are running this sample in [!INCLUDE[windowsver](../../../../includes/windowsver-md.md)] or [!INCLUDE[win7_client_firstref](../../../../includes/win7-client-firstref-md.md)], ensure that you are running [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] with elevated privileges.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b5f17-110">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="b5f17-110">The samples may already be installed on your machine.</span></span> <span data-ttu-id="b5f17-111">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="b5f17-111">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="b5f17-112">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="b5f17-112">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="b5f17-113">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="b5f17-113">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Binding\ByteStreamEncoder`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="b5f17-114">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="b5f17-114">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="b5f17-115">在 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 中打开 ByteStreamHttpBinding.sln 文件。</span><span class="sxs-lookup"><span data-stu-id="b5f17-115">Open the ByteStreamHttpBinding.sln file in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span></span>  
  
2.  <span data-ttu-id="b5f17-116">通过右键单击解决方案资源管理器中的项目并选择开始 ByteStreamHttpBindingServer 项目的新实例**调试**，，然后**启动新实例**从上下文菜单。</span><span class="sxs-lookup"><span data-stu-id="b5f17-116">Start a new instance of the ByteStreamHttpBindingServer project by right-clicking the project in the Solution Explorer and selecting **Debug**, and then **Start new instance** from the context menu.</span></span>  
  
3.  <span data-ttu-id="b5f17-117">通过右键单击解决方案资源管理器中的项目并选择开始 ByteStreamHttpBindingClient 项目的新实例**调试**，**启动新实例**从上下文菜单。</span><span class="sxs-lookup"><span data-stu-id="b5f17-117">Start a new instance of the ByteStreamHttpBindingClient project by right-clicking the project in the Solution Explorer and selecting **Debug**, **Start new instance** from the context menu.</span></span>
