---
title: 如何：创建使用现有服务协定的工作流服务
ms.date: 03/30/2017
ms.assetid: 11d11b59-acc4-48bf-8e4b-e97b516aa0a9
ms.openlocfilehash: f25e71aec03f9808b3263f0353328f92888ccc69
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962313"
---
# <a name="how-to-create-a-workflow-service-that-consumes-an-existing-service-contract"></a><span data-ttu-id="d0be5-102">如何：创建使用现有服务协定的工作流服务</span><span class="sxs-lookup"><span data-stu-id="d0be5-102">How to: Create a workflow service that consumes an existing service contract</span></span>
<span data-ttu-id="d0be5-103">.NET Framework 4.5 以协定优先工作流开发的形式, 在 web 服务和工作流之间更好地集成。</span><span class="sxs-lookup"><span data-stu-id="d0be5-103">.NET Framework 4.5 features better integration between web services and workflows in the form of contract-first workflow development.</span></span> <span data-ttu-id="d0be5-104">通过协定优先的工作流开发工具，可以在代码中优先设计协定。</span><span class="sxs-lookup"><span data-stu-id="d0be5-104">The contract-first workflow development tool allows you to design the contract in code first.</span></span> <span data-ttu-id="d0be5-105">然后该工具在工具箱中为协定中的操作自动生成活动模板。</span><span class="sxs-lookup"><span data-stu-id="d0be5-105">The tool then automatically generates an activity template in the toolbox for the operations in the contract.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d0be5-106">本主题提供了有关创建协定优先工作流服务的分步指南。</span><span class="sxs-lookup"><span data-stu-id="d0be5-106">This topic provides step-by-step guidance on creating a contract-first workflow service.</span></span> <span data-ttu-id="d0be5-107">有关协定优先工作流服务开发的详细信息, 请参阅[约定优先工作流服务开发](contract-first-workflow-service-development.md)。</span><span class="sxs-lookup"><span data-stu-id="d0be5-107">For more information about contract-first workflow service development, see [Contract First Workflow Service Development](contract-first-workflow-service-development.md).</span></span>  
  
### <a name="creating-the-workflow-project"></a><span data-ttu-id="d0be5-108">创建工作流项目</span><span class="sxs-lookup"><span data-stu-id="d0be5-108">Creating the workflow project</span></span>  
  
1. <span data-ttu-id="d0be5-109">在 Visual Studio 中, 选择 "**文件**"、"**新建项目**"。</span><span class="sxs-lookup"><span data-stu-id="d0be5-109">In Visual Studio, select **File**, **New Project**.</span></span> <span data-ttu-id="d0be5-110">在**模板**树中的**C#** 节点下选择 " **wcf** " 节点, 并选择 " **wcf 工作流服务应用程序**" 模板。</span><span class="sxs-lookup"><span data-stu-id="d0be5-110">Select the **WCF** node under the **C#** node in the **Templates** tree, and select the **WCF Workflow Service Application** template.</span></span>  
  
2. <span data-ttu-id="d0be5-111">为新项目`ContractFirst`命名, 然后单击 **"确定"** 。</span><span class="sxs-lookup"><span data-stu-id="d0be5-111">Name the new project `ContractFirst` and click **Ok**.</span></span>  
  
### <a name="creating-the-service-contract"></a><span data-ttu-id="d0be5-112">创建服务协定</span><span class="sxs-lookup"><span data-stu-id="d0be5-112">Creating the service contract</span></span>  
  
1. <span data-ttu-id="d0be5-113">在**解决方案资源管理器**中右键单击该项目, 然后选择 "**添加**"、"**新建项 ...** "。</span><span class="sxs-lookup"><span data-stu-id="d0be5-113">Right-click the project in **Solution Explorer** and select **Add**, **New Item…**.</span></span> <span data-ttu-id="d0be5-114">选择左侧的 "**代码**" 节点, 并在右侧选择 "**类**" 模板。</span><span class="sxs-lookup"><span data-stu-id="d0be5-114">Select the **Code** node on the left, and the **Class** template on the right.</span></span> <span data-ttu-id="d0be5-115">将新类`IBookService`命名为, 然后单击 **"确定"** 。</span><span class="sxs-lookup"><span data-stu-id="d0be5-115">Name the new class `IBookService` and click **Ok**.</span></span>  
  
2. <span data-ttu-id="d0be5-116">在显示的代码窗口的顶部，向 `System.Servicemodel` 添加一个 Using 语句。</span><span class="sxs-lookup"><span data-stu-id="d0be5-116">In the top of the code window that appears, add a Using statement to `System.Servicemodel`.</span></span>  
  
    ```  
    using System.ServiceModel;  
    ```  
  
3. <span data-ttu-id="d0be5-117">将示例类定义更改为以下接口定义。</span><span class="sxs-lookup"><span data-stu-id="d0be5-117">Change the sample class definition to the following interface definition.</span></span>  
  
    ```  
    [ServiceContract]  
        public interface IBookService  
        {  
            [OperationContract]  
            void Buy(string bookName);  
  
            [OperationContract(IsOneWay=true)]  
            void Checkout();  
        }  
    ```  
  
4. <span data-ttu-id="d0be5-118">按**Ctrl + Shift + B**生成项目。</span><span class="sxs-lookup"><span data-stu-id="d0be5-118">Build the project by pressing **Ctrl+Shift+B**.</span></span>  
  
### <a name="importing-the-service-contract"></a><span data-ttu-id="d0be5-119">导入服务协定</span><span class="sxs-lookup"><span data-stu-id="d0be5-119">Importing the service contract</span></span>  
  
1. <span data-ttu-id="d0be5-120">在**解决方案资源管理器**中右键单击该项目, 然后选择 "**导入服务协定**"。</span><span class="sxs-lookup"><span data-stu-id="d0be5-120">Right-click the project in **Solution Explorer** and select **Import Service Contract**.</span></span> <span data-ttu-id="d0be5-121">下 **\<当前项目>** ，打开所有子节点，然后选择 **IBookService** 。</span><span class="sxs-lookup"><span data-stu-id="d0be5-121">Under **\<Current Project>**, open all sub-nodes and select **IBookService**.</span></span> <span data-ttu-id="d0be5-122">单击 **“确定”** 。</span><span class="sxs-lookup"><span data-stu-id="d0be5-122">Click **OK**.</span></span>  
  
2. <span data-ttu-id="d0be5-123">将会打开一个对话框，提示您该操作已成功完成，并且在生成该项目后，所生成的活动将出现在工具箱中。</span><span class="sxs-lookup"><span data-stu-id="d0be5-123">A dialog will open, alerting you that the operation completed successfully, and that the generated activities will appear in the toolbox after you build the project.</span></span> <span data-ttu-id="d0be5-124">单击 **“确定”** 。</span><span class="sxs-lookup"><span data-stu-id="d0be5-124">Click **OK**.</span></span>  
  
3. <span data-ttu-id="d0be5-125">按**Ctrl + Shift + B**生成项目, 以便导入的活动将显示在工具箱中。</span><span class="sxs-lookup"><span data-stu-id="d0be5-125">Build the project by pressing **Ctrl+Shift+B**, so that the imported activities will appear in the toolbox.</span></span>  
  
4. <span data-ttu-id="d0be5-126">在**解决方案资源管理器**中, 打开 .xamlx。</span><span class="sxs-lookup"><span data-stu-id="d0be5-126">In **Solution Explorer**, open Service1.xamlx.</span></span> <span data-ttu-id="d0be5-127">该工作流服务将出现在设计器中。</span><span class="sxs-lookup"><span data-stu-id="d0be5-127">The workflow service will appear in the designer.</span></span>  
  
5. <span data-ttu-id="d0be5-128">选择 "**序列**" 活动。</span><span class="sxs-lookup"><span data-stu-id="d0be5-128">Select the **Sequence** activity.</span></span> <span data-ttu-id="d0be5-129">在属性窗口中, 单击 **...**</span><span class="sxs-lookup"><span data-stu-id="d0be5-129">In the Properties window, click the **…**</span></span> <span data-ttu-id="d0be5-130">按钮的**ImplementedContract** 。</span><span class="sxs-lookup"><span data-stu-id="d0be5-130">button in the **ImplementedContract** property.</span></span> <span data-ttu-id="d0be5-131">在出现的 "**类型集合编辑器**" 窗口中, 单击 "**类型**" 下拉列表, 然后选择 "**浏览类型 ...** "</span><span class="sxs-lookup"><span data-stu-id="d0be5-131">In the **Type Collection Editor** window that appears, click the **Type** dropdown, and select the **Browse for Types…**</span></span> <span data-ttu-id="d0be5-132">条目.</span><span class="sxs-lookup"><span data-stu-id="d0be5-132">entry.</span></span> <span data-ttu-id="d0be5-133">在中 **浏览并选择.NET 类型** 对话框下 **\<当前项目>** ，打开所有子节点，然后选择 **IBookService** 。</span><span class="sxs-lookup"><span data-stu-id="d0be5-133">In the **Browse and Select a .NET Type** dialog, under **\<Current Project>**, open all sub-nodes and select **IBookService**.</span></span> <span data-ttu-id="d0be5-134">单击 **“确定”** 。</span><span class="sxs-lookup"><span data-stu-id="d0be5-134">Click **OK**.</span></span> <span data-ttu-id="d0be5-135">在 "**类型集合编辑器**" 对话框中, 单击 **"确定"** 。</span><span class="sxs-lookup"><span data-stu-id="d0be5-135">In the **Type Collection Editor** dialog, click **OK**.</span></span>  
  
6. <span data-ttu-id="d0be5-136">选择并删除 " **ReceiveRequest** " 和 " **SendResponse** " 活动。</span><span class="sxs-lookup"><span data-stu-id="d0be5-136">Select and delete the **ReceiveRequest** and **SendResponse** activities.</span></span>  
  
7. <span data-ttu-id="d0be5-137">从 "工具箱" 中, 将 " **Buy_ReceiveAndSendReply** " 和 " **Checkout_Receive** " 活动拖到 "**顺序服务**" 活动上。</span><span class="sxs-lookup"><span data-stu-id="d0be5-137">From the toolbox, drag a **Buy_ReceiveAndSendReply** and a **Checkout_Receive** activity onto the **Sequential Service** activity.</span></span>
