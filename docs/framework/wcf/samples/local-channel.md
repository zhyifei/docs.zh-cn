---
title: 本地通道
ms.date: 03/30/2017
ms.assetid: fa1917a4-f701-4e82-a439-14a16282c7cc
ms.openlocfilehash: 87e140395ac2fb5702d8655cf970da8a60c991ec
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79144502"
---
# <a name="local-channel"></a><span data-ttu-id="a4ec9-102">本地通道</span><span class="sxs-lookup"><span data-stu-id="a4ec9-102">Local Channel</span></span>
<span data-ttu-id="a4ec9-103">本地通道是用于同一应用程序域内通信的 Windows 通信基础 （WCF） 传输通道。</span><span class="sxs-lookup"><span data-stu-id="a4ec9-103">Local Channel is a Windows Communication Foundation (WCF) transport channel that is used for communication within the same application domain.</span></span> <span data-ttu-id="a4ec9-104">对于客户端和服务在相同应用程序域内运行，并且必须避免典型 WCF 通道堆栈（消息的序列化和反序列化）开销的方案，这十分有用。</span><span class="sxs-lookup"><span data-stu-id="a4ec9-104">This is useful for scenarios where the client and the service are running in the same application domain and the overhead of the typical WCF channel stack (serialization and deserialization of messages) must be avoided.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="a4ec9-105">演示</span><span class="sxs-lookup"><span data-stu-id="a4ec9-105">Demonstrates</span></span>  
 <span data-ttu-id="a4ec9-106">本地通道</span><span class="sxs-lookup"><span data-stu-id="a4ec9-106">Local Channel</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="a4ec9-107">讨论区</span><span class="sxs-lookup"><span data-stu-id="a4ec9-107">Discussion</span></span>  
 <span data-ttu-id="a4ec9-108">示例由两个项目文件组成：</span><span class="sxs-lookup"><span data-stu-id="a4ec9-108">The sample consists of two project files:</span></span>  
  
- <span data-ttu-id="a4ec9-109">**本地通道**：当前应用程序域中本地通道的编程表示形式。</span><span class="sxs-lookup"><span data-stu-id="a4ec9-109">**LocalChannel**: The programmatic representation of the local channel within the current application domain.</span></span> <span data-ttu-id="a4ec9-110">在此项目中，发送组件将消息放置在内存中队列中，接收组件将消息从队列中取出以进行接收。</span><span class="sxs-lookup"><span data-stu-id="a4ec9-110">In this project, the sending component places the message in an in-memory queue and the receiving component de-queues the message to receive it.</span></span>  
  
- <span data-ttu-id="a4ec9-111">**客户端和服务**：此项目在控制台应用程序中托管服务，然后运行客户端以从同一应用程序域中调用该服务。</span><span class="sxs-lookup"><span data-stu-id="a4ec9-111">**ClientAndService**: This project hosts a service in a console application and then runs a client to call the service from within the same application domain.</span></span>  
  
 <span data-ttu-id="a4ec9-112">本地通道设计跳过通道堆栈和序列化过程以提高速度。</span><span class="sxs-lookup"><span data-stu-id="a4ec9-112">The local channel design skips both the channel stack and the serialization process to increase speed.</span></span> <span data-ttu-id="a4ec9-113">本地传输通道使用队列实现，以将服务调用从客户端传输到服务并将值返回到客户端。</span><span class="sxs-lookup"><span data-stu-id="a4ec9-113">The local transport channel is implemented using a queue to transport service calls from the client to the service and to return back the value to the client.</span></span> <span data-ttu-id="a4ec9-114">示例复制对象，而不是对参数和返回值进行序列化。</span><span class="sxs-lookup"><span data-stu-id="a4ec9-114">Rather than serializing parameters and return values, the sample copies the objects.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="a4ec9-115">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="a4ec9-115">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="a4ec9-116">生成并运行 LocalChannel 解决方案。</span><span class="sxs-lookup"><span data-stu-id="a4ec9-116">Build and run the LocalChannel solution.</span></span>  
  
2. <span data-ttu-id="a4ec9-117">服务主机启动，客户端使用本地通道调用服务。</span><span class="sxs-lookup"><span data-stu-id="a4ec9-117">The service host is started and the client calls the service using the local channel.</span></span> <span data-ttu-id="a4ec9-118">出现控制台窗口，以显示服务调用的结果。</span><span class="sxs-lookup"><span data-stu-id="a4ec9-118">A console window appears to display the results of the service call.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="a4ec9-119">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="a4ec9-119">The samples may already be installed on your machine.</span></span> <span data-ttu-id="a4ec9-120">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="a4ec9-120">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="a4ec9-121">如果此目录不存在，请转到[Windows 通信基础 （WCF） 和 Windows 工作流基础 （WF） 示例 .NET 框架 4](https://www.microsoft.com/download/details.aspx?id=21459)以下载[!INCLUDE[wf1](../../../../includes/wf1-md.md)]所有 Windows 通信基础 （WCF） 和示例。</span><span class="sxs-lookup"><span data-stu-id="a4ec9-121">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="a4ec9-122">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="a4ec9-122">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Channels\LocalChannel`
