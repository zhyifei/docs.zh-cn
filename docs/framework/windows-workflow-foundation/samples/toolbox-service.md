---
title: 工具箱服务
ms.date: 03/30/2017
ms.assetid: 742212d0-445e-41ed-9739-9ee848ce7f1b
ms.openlocfilehash: 0b21f10c763f3f82591f947eb4cc48cf90f4ac79
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2018
ms.locfileid: "43406457"
---
# <a name="toolbox-service"></a><span data-ttu-id="feada-102">工具箱服务</span><span class="sxs-lookup"><span data-stu-id="feada-102">Toolbox Service</span></span>
<span data-ttu-id="feada-103">此示例演示如何根据工作流的上下文来更新 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 工具箱活动。</span><span class="sxs-lookup"><span data-stu-id="feada-103">This sample demonstrates how to update the [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] Toolbox activities based on the context of the workflow.</span></span> <span data-ttu-id="feada-104">此示例包含一个工作流，此工作流基于是否选择了自定义活动来更改工具箱的内容。</span><span class="sxs-lookup"><span data-stu-id="feada-104">The sample contains a workflow that changes the toolbox contents based on whether a custom activity is selected.</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="feada-105">讨论</span><span class="sxs-lookup"><span data-stu-id="feada-105">Discussion</span></span>  
 <span data-ttu-id="feada-106">在工作流创作期间，客户通常希望他们的工具箱是上下文相关的。</span><span class="sxs-lookup"><span data-stu-id="feada-106">During workflow authoring, customers generally want their Toolbox to be context sensitive.</span></span> <span data-ttu-id="feada-107">例如，用户可能希望确保，在将特定活动添加到工作流时，工具箱会显示一些其他活动。</span><span class="sxs-lookup"><span data-stu-id="feada-107">For example, the user may want to ensure that the Toolbox shows a few additional activities when a specific activity is added to the workflow.</span></span> <span data-ttu-id="feada-108">如果从工作流中移除这些活动，则工具箱应根据域要求做出相应的响应。</span><span class="sxs-lookup"><span data-stu-id="feada-108">If the activities are removed from the workflow, the toolbox should react appropriately based on the domain requirements.</span></span>  
  
 <span data-ttu-id="feada-109">在重新承载的工作流设计器中，您可以控制工具箱控件并确保，主机会根据工作流中的模型更改，在工具箱控件中触发适当的更改。</span><span class="sxs-lookup"><span data-stu-id="feada-109">In a re-hosted workflow designer, you control the Toolbox control and can ensure that based on the Model changes in the workflow, the host triggers appropriate changes in the Toolbox control.</span></span> <span data-ttu-id="feada-110">但是，在 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 中，用户无法控制工具箱，因此需要一个接口来修改工具箱的内容。</span><span class="sxs-lookup"><span data-stu-id="feada-110">However, in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], the toolbox is not controlled by the user and thus an interface is required to modify its contents.</span></span> <span data-ttu-id="feada-111">`IActivityToolboxService` 正是这样一个接口。</span><span class="sxs-lookup"><span data-stu-id="feada-111">`IActivityToolboxService` is that interface.</span></span>  
  
 <span data-ttu-id="feada-112">该 API 提供以下四个方法。</span><span class="sxs-lookup"><span data-stu-id="feada-112">The API provides the following four methods.</span></span>  
  
```  
public interface IActivityToolboxService   
{   
        void AddCategory(string categoryName);   
        void RemoveCategory(string categoryName);   
        void AddItem(string qualifiedTypeName, string categoryName);   
        void RemoveItem(string qualifiedTypeName, string categoryName);   
        IList<string> EnumCategories();   
        IList<string> EnumItems(string categoryName);   
}  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="feada-113">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="feada-113">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="feada-114">使用 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 打开 WorkflowSimulator.sln 解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="feada-114">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the WorkflowSimulator.sln solution file.</span></span>  
  
2.  <span data-ttu-id="feada-115">按 Ctrl+Shift+B 生成解决方案。</span><span class="sxs-lookup"><span data-stu-id="feada-115">Build the solution by pressing CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="feada-116">打开 Workflow.xaml 文件。</span><span class="sxs-lookup"><span data-stu-id="feada-116">Open the Workflow.xaml file.</span></span>  
  
4.  <span data-ttu-id="feada-117">添加**CustomActivity**通过拖放工具箱中。</span><span class="sxs-lookup"><span data-stu-id="feada-117">Add a **CustomActivity** by dragging and dropping it from the toolbox.</span></span> <span data-ttu-id="feada-118">请注意，名为的附加工具箱类别：**新 WF 类别**包含一个附加活动**分配**。</span><span class="sxs-lookup"><span data-stu-id="feada-118">Notice that an additional Toolbox category called: **New WF Category** with an additional activity **Assign**.</span></span>  
  
5.  <span data-ttu-id="feada-119">现在请取消选中**CustomActivity**通过将另一个活动拖到其中。</span><span class="sxs-lookup"><span data-stu-id="feada-119">Now unselect the **CustomActivity** by dragging another activity into it.</span></span>  
  
6.  <span data-ttu-id="feada-120">该项**分配**类别中**新 WF 类别**现在移除工具箱下。</span><span class="sxs-lookup"><span data-stu-id="feada-120">The item **Assign** in the category **New WF Category** under Toolbox is now removed.</span></span> <span data-ttu-id="feada-121">此外，由于该类别中没有剩下其他任何项，因此还将移除该类别。</span><span class="sxs-lookup"><span data-stu-id="feada-121">Also, because there are no more items left in the category, the category is removed as well.</span></span>  
  
7.  <span data-ttu-id="feada-122">选择**CustomActivity**再次和类别并**分配**活动添加回来。</span><span class="sxs-lookup"><span data-stu-id="feada-122">Select the **CustomActivity** again and the category and **Assign** activity is added back.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="feada-123">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="feada-123">The samples may already be installed on your machine.</span></span> <span data-ttu-id="feada-124">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="feada-124">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="feada-125">如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="feada-125">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="feada-126">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="feada-126">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Designer\IActivityToolboxService`
