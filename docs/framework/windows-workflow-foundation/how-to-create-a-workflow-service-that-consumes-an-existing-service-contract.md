---
title: 如何：创建使用现有服务协定的工作流服务
ms.date: 03/30/2017
ms.assetid: 11d11b59-acc4-48bf-8e4b-e97b516aa0a9
ms.openlocfilehash: 06d4d4f6687979f4fd54e919ca6f236a5b5402e8
ms.sourcegitcommit: 69bf8b719d4c289eec7b45336d0b933dd7927841
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2019
ms.locfileid: "57843003"
---
# <a name="how-to-create-a-workflow-service-that-consumes-an-existing-service-contract"></a><span data-ttu-id="db129-102">如何：创建使用现有服务协定的工作流服务</span><span class="sxs-lookup"><span data-stu-id="db129-102">How to: Create a workflow service that consumes an existing service contract</span></span>
[!INCLUDE[net_v45](../../../includes/net-v45-md.md)] <span data-ttu-id="db129-103">以协定优先工作流开发的形式实现了 Web 服务与工作流之间的更佳集成。</span><span class="sxs-lookup"><span data-stu-id="db129-103">features better integration between web services and workflows in the form of contract-first workflow development.</span></span> <span data-ttu-id="db129-104">通过协定优先的工作流开发工具，可以在代码中优先设计协定。</span><span class="sxs-lookup"><span data-stu-id="db129-104">The contract-first workflow development tool allows you to design the contract in code first.</span></span> <span data-ttu-id="db129-105">然后该工具在工具箱中为协定中的操作自动生成活动模板。</span><span class="sxs-lookup"><span data-stu-id="db129-105">The tool then automatically generates an activity template in the toolbox for the operations in the contract.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="db129-106">本主题提供了有关创建协定优先工作流服务的分步指南。</span><span class="sxs-lookup"><span data-stu-id="db129-106">This topic provides step-by-step guidance on creating a contract-first workflow service.</span></span> <span data-ttu-id="db129-107">有关协定优先工作流服务开发的详细信息，请参阅[协定优先工作流服务开发](contract-first-workflow-service-development.md)。</span><span class="sxs-lookup"><span data-stu-id="db129-107">For more information about contract-first workflow service development, see [Contract First Workflow Service Development](contract-first-workflow-service-development.md).</span></span>  
  
### <a name="creating-the-workflow-project"></a><span data-ttu-id="db129-108">创建工作流项目</span><span class="sxs-lookup"><span data-stu-id="db129-108">Creating the workflow project</span></span>  
  
1.  <span data-ttu-id="db129-109">在 Visual Studio 中，选择**文件**，**新项目**。</span><span class="sxs-lookup"><span data-stu-id="db129-109">In Visual Studio, select **File**, **New Project**.</span></span> <span data-ttu-id="db129-110">选择**WCF**节点下的**C#** 中的节点**模板**树，然后选择**WCF 工作流服务应用程序**模板。</span><span class="sxs-lookup"><span data-stu-id="db129-110">Select the **WCF** node under the **C#** node in the **Templates** tree, and select the **WCF Workflow Service Application** template.</span></span>  
  
2.  <span data-ttu-id="db129-111">将新项目命名`ContractFirst`然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="db129-111">Name the new project `ContractFirst` and click **Ok**.</span></span>  
  
### <a name="creating-the-service-contract"></a><span data-ttu-id="db129-112">创建服务协定</span><span class="sxs-lookup"><span data-stu-id="db129-112">Creating the service contract</span></span>  
  
1.  <span data-ttu-id="db129-113">右键单击该项目中的**解决方案资源管理器**，然后选择**添加**，**新项...**.</span><span class="sxs-lookup"><span data-stu-id="db129-113">Right-click the project in **Solution Explorer** and select **Add**, **New Item…**.</span></span> <span data-ttu-id="db129-114">选择**代码**左侧节点和**类**在右侧的模板。</span><span class="sxs-lookup"><span data-stu-id="db129-114">Select the **Code** node on the left, and the **Class** template on the right.</span></span> <span data-ttu-id="db129-115">将新类命名`IBookService`然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="db129-115">Name the new class `IBookService` and click **Ok**.</span></span>  
  
2.  <span data-ttu-id="db129-116">在显示的代码窗口的顶部，向 `System.Servicemodel` 添加一个 Using 语句。</span><span class="sxs-lookup"><span data-stu-id="db129-116">In the top of the code window that appears, add a Using statement to `System.Servicemodel`.</span></span>  
  
    ```  
    using System.ServiceModel;  
    ```  
  
3.  <span data-ttu-id="db129-117">将示例类定义更改为以下接口定义。</span><span class="sxs-lookup"><span data-stu-id="db129-117">Change the sample class definition to the following interface definition.</span></span>  
  
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
  
4.  <span data-ttu-id="db129-118">生成项目，通过按**Ctrl + Shift + B**。</span><span class="sxs-lookup"><span data-stu-id="db129-118">Build the project by pressing **Ctrl+Shift+B**.</span></span>  
  
### <a name="importing-the-service-contract"></a><span data-ttu-id="db129-119">导入服务协定</span><span class="sxs-lookup"><span data-stu-id="db129-119">Importing the service contract</span></span>  
  
1.  <span data-ttu-id="db129-120">右键单击该项目中的**解决方案资源管理器**，然后选择**导入服务协定**。</span><span class="sxs-lookup"><span data-stu-id="db129-120">Right-click the project in **Solution Explorer** and select **Import Service Contract**.</span></span> <span data-ttu-id="db129-121">下**\<当前项目 >**，打开所有子节点，然后选择**IBookService**。</span><span class="sxs-lookup"><span data-stu-id="db129-121">Under **\<Current Project>**, open all sub-nodes and select **IBookService**.</span></span> <span data-ttu-id="db129-122">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="db129-122">Click **OK**.</span></span>  
  
2.  <span data-ttu-id="db129-123">将会打开一个对话框，提示您该操作已成功完成，并且在生成该项目后，所生成的活动将出现在工具箱中。</span><span class="sxs-lookup"><span data-stu-id="db129-123">A dialog will open, alerting you that the operation completed successfully, and that the generated activities will appear in the toolbox after you build the project.</span></span> <span data-ttu-id="db129-124">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="db129-124">Click **OK**.</span></span>  
  
3.  <span data-ttu-id="db129-125">生成项目，通过按**Ctrl + Shift + B**，以便导入的活动将出现在工具箱中。</span><span class="sxs-lookup"><span data-stu-id="db129-125">Build the project by pressing **Ctrl+Shift+B**, so that the imported activities will appear in the toolbox.</span></span>  
  
4.  <span data-ttu-id="db129-126">在中**解决方案资源管理器**，打开 Service1.xamlx。</span><span class="sxs-lookup"><span data-stu-id="db129-126">In **Solution Explorer**, open Service1.xamlx.</span></span> <span data-ttu-id="db129-127">该工作流服务将出现在设计器中。</span><span class="sxs-lookup"><span data-stu-id="db129-127">The workflow service will appear in the designer.</span></span>  
  
5.  <span data-ttu-id="db129-128">选择**序列**活动。</span><span class="sxs-lookup"><span data-stu-id="db129-128">Select the **Sequence** activity.</span></span> <span data-ttu-id="db129-129">在属性窗口中，单击 **...**</span><span class="sxs-lookup"><span data-stu-id="db129-129">In the Properties window, click the **…**</span></span> <span data-ttu-id="db129-130">在按钮**ImplementedContract**属性。</span><span class="sxs-lookup"><span data-stu-id="db129-130">button in the **ImplementedContract** property.</span></span> <span data-ttu-id="db129-131">在中**类型集合编辑器**出现窗口中，单击**类型**下拉列表中，并选择**浏览类型...**</span><span class="sxs-lookup"><span data-stu-id="db129-131">In the **Type Collection Editor** window that appears, click the **Type** dropdown, and select the **Browse for Types…**</span></span> <span data-ttu-id="db129-132">项。</span><span class="sxs-lookup"><span data-stu-id="db129-132">entry.</span></span> <span data-ttu-id="db129-133">在中**浏览并选择.NET 类型**对话框下**\<当前项目 >**，打开所有子节点，然后选择**IBookService**。</span><span class="sxs-lookup"><span data-stu-id="db129-133">In the **Browse and Select a .NET Type** dialog, under **\<Current Project>**, open all sub-nodes and select **IBookService**.</span></span> <span data-ttu-id="db129-134">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="db129-134">Click **OK**.</span></span> <span data-ttu-id="db129-135">在中**类型集合编辑器**对话框中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="db129-135">In the **Type Collection Editor** dialog, click **OK**.</span></span>  
  
6.  <span data-ttu-id="db129-136">选择并删除**ReceiveRequest**并**SendResponse**活动。</span><span class="sxs-lookup"><span data-stu-id="db129-136">Select and delete the **ReceiveRequest** and **SendResponse** activities.</span></span>  
  
7.  <span data-ttu-id="db129-137">从工具箱中拖动**Buy_ReceiveAndSendReply**和一个**Checkout_Receive**活动拖动到**顺序服务**活动。</span><span class="sxs-lookup"><span data-stu-id="db129-137">From the toolbox, drag a **Buy_ReceiveAndSendReply** and a **Checkout_Receive** activity onto the **Sequential Service** activity.</span></span>
