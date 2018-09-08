---
title: 源数据存储可编程性
ms.date: 03/30/2017
ms.assetid: 5b613661-f3f9-4e07-8e88-28c9ea2fd8f8
ms.openlocfilehash: 4ea6117686b985a9ea18ce4e5cc4ea2b5c25524c
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2018
ms.locfileid: "44187015"
---
# <a name="metadata-store-programmability"></a><span data-ttu-id="bb82c-102">源数据存储可编程性</span><span class="sxs-lookup"><span data-stu-id="bb82c-102">Metadata Store Programmability</span></span>
<span data-ttu-id="bb82c-103">元数据存储是一项 [!INCLUDE[wfd1](../../../../includes/wfd1-md.md)] 功能，可用于将任意元数据关联（以 CLR 特性的形式）运行时类型。</span><span class="sxs-lookup"><span data-stu-id="bb82c-103">The metadata store is a [!INCLUDE[wfd1](../../../../includes/wfd1-md.md)] feature that allows for the association of arbitrary metadata, in the form of CLR attributes, to types at runtime.</span></span> <span data-ttu-id="bb82c-104">这可以实现运行时组件与其设计时对应项之间的松散耦合，并且可以实现在不影响运行时的情况下更改设计时组件。</span><span class="sxs-lookup"><span data-stu-id="bb82c-104">This allows for a loose coupling between the run-time components and their design-time counterparts, as well as the ability to change the design-time components without affecting the runtime.</span></span> <span data-ttu-id="bb82c-105">此示例演示如何通过对运行时类型（我们无法控制的源）应用特性来针对元数据存储进行编程。</span><span class="sxs-lookup"><span data-stu-id="bb82c-105">The sample shows how to program against the metadata store by applying attributes to a run-time type, the source for which we have no control over.</span></span> <span data-ttu-id="bb82c-106">通常使用的术语是，主机应用程序为一组类型注册元数据。</span><span class="sxs-lookup"><span data-stu-id="bb82c-106">The terminology typically used is that a hosting application registers the metadata for a set of types.</span></span>  
  
 <span data-ttu-id="bb82c-107">在输出中，你可能会发现其他、 意外的特性<!--zz <xref:System.Runtime.InteropServices.GUIDAttribute> --> `System.Runtime.InteropServices.GUIDAttribute`。</span><span class="sxs-lookup"><span data-stu-id="bb82c-107">Within the output, you may notice an additional, unexpected attribute, <!--zz <xref:System.Runtime.InteropServices.GUIDAttribute> --> `System.Runtime.InteropServices.GUIDAttribute`.</span></span> <span data-ttu-id="bb82c-108">此特性是在使用元数据 API 时添加的，对示例的运行没有任何影响。</span><span class="sxs-lookup"><span data-stu-id="bb82c-108">This is added when using the Metadata API and has no impact on the running of the sample.</span></span>  
  
 <span data-ttu-id="bb82c-109">此示例演示：</span><span class="sxs-lookup"><span data-stu-id="bb82c-109">This sample demonstrates:</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="bb82c-110">演示</span><span class="sxs-lookup"><span data-stu-id="bb82c-110">Demonstrates</span></span>  
  
-   <span data-ttu-id="bb82c-111">使用元数据存储 API 注入特性。</span><span class="sxs-lookup"><span data-stu-id="bb82c-111">Attribute injection using the metadata store API.</span></span>  
  
-   <span data-ttu-id="bb82c-112">使用回调机制延迟元数据注册。</span><span class="sxs-lookup"><span data-stu-id="bb82c-112">Using a callback mechanism to defer metadata registration.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="bb82c-113">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="bb82c-113">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="bb82c-114">使用 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 打开 ProgrammingMetadataStore.sln 解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="bb82c-114">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the ProgrammingMetadataStore.sln solution file.</span></span>  
  
2.  <span data-ttu-id="bb82c-115">要生成解决方案，按 Ctrl+Shift+B。</span><span class="sxs-lookup"><span data-stu-id="bb82c-115">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="bb82c-116">若要运行解决方案，请按 F5。</span><span class="sxs-lookup"><span data-stu-id="bb82c-116">To run the solution, press F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="bb82c-117">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="bb82c-117">The samples may already be installed on your machine.</span></span> <span data-ttu-id="bb82c-118">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="bb82c-118">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="bb82c-119">如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="bb82c-119">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="bb82c-120">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="bb82c-120">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\CustomActivityDesigners\MetadataStore`