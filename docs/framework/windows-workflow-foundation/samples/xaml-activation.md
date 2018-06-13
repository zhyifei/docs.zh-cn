---
title: XAML 激活
ms.date: 03/30/2017
ms.assetid: 486760e2-bb10-4ed5-8c02-fe7472498d2d
ms.openlocfilehash: 8621b0ea7b390c81e76ac7eeedb0b547b44320d7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33517707"
---
# <a name="xaml-activation"></a><span data-ttu-id="ebf08-102">XAML 激活</span><span class="sxs-lookup"><span data-stu-id="ebf08-102">XAML Activation</span></span>
<span data-ttu-id="ebf08-103">此示例演示如何在 IIS 中承载声明性工作流。</span><span class="sxs-lookup"><span data-stu-id="ebf08-103">This sample demonstrates how to host a declarative workflow in IIS.</span></span> <span data-ttu-id="ebf08-104">此示例是一个名为 `EchoService` 的基本工作流，它具有一个操作。</span><span class="sxs-lookup"><span data-stu-id="ebf08-104">The sample is a basic workflow called `EchoService` that has one operation.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ebf08-105">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="ebf08-105">The samples may already be installed on your machine.</span></span> <span data-ttu-id="ebf08-106">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="ebf08-106">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="ebf08-107">如果此目录不存在，请转到 （下载页） 以下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="ebf08-107">If this directory does not exist, go to (download page) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ebf08-108">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="ebf08-108">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\XAMLActivation`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="ebf08-109">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="ebf08-109">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="ebf08-110">在 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 中打开 XAMLActivation.sln 解决方案。</span><span class="sxs-lookup"><span data-stu-id="ebf08-110">Open the XAMLActivation.sln solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="ebf08-111">生成解决方案，按**F5**。</span><span class="sxs-lookup"><span data-stu-id="ebf08-111">Build the solution by pressing **F5**.</span></span>  
  
3.  <span data-ttu-id="ebf08-112">运行 WcfTestClient.exe。</span><span class="sxs-lookup"><span data-stu-id="ebf08-112">Run WcfTestClient.exe.</span></span> <span data-ttu-id="ebf08-113">在命令提示符下键入：</span><span class="sxs-lookup"><span data-stu-id="ebf08-113">From a command prompt, type in the following:</span></span>  
  
    1.  <span data-ttu-id="ebf08-114">cd %SystemDrive%\Program Files\Microsoft Visual Studio 10.0\Common7\IDE</span><span class="sxs-lookup"><span data-stu-id="ebf08-114">cd %SystemDrive%\Program Files\Microsoft Visual Studio 10.0\Common7\IDE</span></span>  
  
    2.  <span data-ttu-id="ebf08-115">运行 WcfTestClient.exe。</span><span class="sxs-lookup"><span data-stu-id="ebf08-115">Run WcfTestClient.exe.</span></span>  
  
4.  <span data-ttu-id="ebf08-116">设置 wcftestclient.exe 的服务的地址，通过按 CTRL + SHIFT + A 并将服务地址设置为http://localhost:56133/Service.xamlx。</span><span class="sxs-lookup"><span data-stu-id="ebf08-116">Set the address of the service on WcfTestClient.exe by pressing CTRL+SHIFT+A and setting the service address to http://localhost:56133/Service.xamlx.</span></span>  
  
5.  <span data-ttu-id="ebf08-117">执行 echo 操作以测试服务。</span><span class="sxs-lookup"><span data-stu-id="ebf08-117">Perform the echo operation to test the service.</span></span>  
  
6.  <span data-ttu-id="ebf08-118">通过管理员特权在命令提示中使用 DeployToIIS.Bat 在 IIS 中部署服务。</span><span class="sxs-lookup"><span data-stu-id="ebf08-118">Deploy the Service in IIS using DeployToIIS.Bat in a command prompt with administrator privileges.</span></span>  
  
7.  <span data-ttu-id="ebf08-119">在客户端到服务地址更新http://localhost/XAMLActivation/Service.xamlx和测试使用 WcfTestClient.exe 重新此服务。</span><span class="sxs-lookup"><span data-stu-id="ebf08-119">Update the service address in the client to http://localhost/XAMLActivation/Service.xamlx and test the service again using WcfTestClient.exe.</span></span>
