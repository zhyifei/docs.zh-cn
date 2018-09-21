---
title: 基本的只包含 XAML 的服务
ms.date: 03/30/2017
ms.assetid: c106feb0-0245-43b5-aefe-93ce0e4d38eb
ms.openlocfilehash: f4f296a97b9c3093874c5ec8e05023e84b0af44a
ms.sourcegitcommit: 3ab9254890a52a50762995fa6d7d77a00348db7e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2018
ms.locfileid: "46489742"
---
# <a name="basic-xaml-only-service"></a><span data-ttu-id="5a644-102">基本的只包含 XAML 的服务</span><span class="sxs-lookup"><span data-stu-id="5a644-102">Basic XAML only Service</span></span>
<span data-ttu-id="5a644-103">此示例演示如何创建只包含 XAML 服务。</span><span class="sxs-lookup"><span data-stu-id="5a644-103">This sample demonstrates how to create a XAML only service.</span></span> <span data-ttu-id="5a644-104">此方案是一个用于解决车辆相关故障的诊断服务。</span><span class="sxs-lookup"><span data-stu-id="5a644-104">The scenario is a diagnostics service for car-related problems.</span></span> <span data-ttu-id="5a644-105">此服务作为一个工作流实现，它会向客户端询问一系列问题来诊断故障。</span><span class="sxs-lookup"><span data-stu-id="5a644-105">The service is implemented as a workflow that asks the client a series of questions to diagnose the problem.</span></span> <span data-ttu-id="5a644-106">此服务可诊断两种类型的故障（车辆无法启动或空调无法工作）。</span><span class="sxs-lookup"><span data-stu-id="5a644-106">There are two types of issues the service can diagnose (car does not start or air conditioning not working).</span></span> <span data-ttu-id="5a644-107">工作流使用设计器中的请求/答复模板来公开三个简单的服务操作。</span><span class="sxs-lookup"><span data-stu-id="5a644-107">The workflow uses Request/Reply template from the designer to expose three simple service operations.</span></span> <span data-ttu-id="5a644-108">通过在 IIS 中创建虚拟目录以及将 service1.xamlx 和 Web.config 文件复制到虚拟目录中，在 IIS 中承载服务，而无需编译的代码。</span><span class="sxs-lookup"><span data-stu-id="5a644-108">The service is hosted in IIS by creating a virtual directory in IIS and copying the service1.xamlx and Web.config files into the virtual directory, no compiled code is required.</span></span> <span data-ttu-id="5a644-109">默认情况下此示例将自动将所需的文件复制到虚拟目录创建时遵循的 WCF 和 WF 示例的安装说明： [WindowsCommunicationFoundation示例的一次性安装过程](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) Visual Studio 2010 中生成时。</span><span class="sxs-lookup"><span data-stu-id="5a644-109">By default this sample will automatically copy the needed files into the virtual directory created when you follow the setup instructions for the WCF and WF samples: [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) when built in Visual Studio 2010.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="5a644-110">使用此示例</span><span class="sxs-lookup"><span data-stu-id="5a644-110">To use this sample</span></span>  
  
1.  <span data-ttu-id="5a644-111">在 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 中加载项目解决方案，然后生成项目。</span><span class="sxs-lookup"><span data-stu-id="5a644-111">Load the project solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] and build the project.</span></span>  
  
2.  <span data-ttu-id="5a644-112">运行在 [解决方案基目录]\Client\bin\debug 中生成的 Client 应用程序。</span><span class="sxs-lookup"><span data-stu-id="5a644-112">Run the Client application generated in [solution base directory]\Client\bin\debug.</span></span>  
  
3.  <span data-ttu-id="5a644-113">该应用程序输出多个选项，选择一个选项。</span><span class="sxs-lookup"><span data-stu-id="5a644-113">The application prints out options, selects an option.</span></span> <span data-ttu-id="5a644-114">然后，该应用程序会询问一些问题，使用“是”或“否”（使用 Y/N 键）来回答问题。</span><span class="sxs-lookup"><span data-stu-id="5a644-114">The application then asks some questions, answer them yes or no (using Y/N keys).</span></span> <span data-ttu-id="5a644-115">当服务完成故障诊断之后，该应用程序输出诊断结果。</span><span class="sxs-lookup"><span data-stu-id="5a644-115">When the service is done diagnosing the issues, the application prints out a diagnosis.</span></span>  
  
4.  <span data-ttu-id="5a644-116">该应用程序返回到选项页面。</span><span class="sxs-lookup"><span data-stu-id="5a644-116">The application goes back to the options.</span></span> <span data-ttu-id="5a644-117">您可诊断下一个故障或退出该应用程序。</span><span class="sxs-lookup"><span data-stu-id="5a644-117">You can diagnose another problem or exit the application.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="5a644-118">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="5a644-118">The samples may already be installed on your machine.</span></span> <span data-ttu-id="5a644-119">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="5a644-119">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="5a644-120">如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="5a644-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="5a644-121">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="5a644-121">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\XAMLService`