---
title: 任务 1：创建一个新的 Windows Presentation Foundation 应用程序
ms.date: 03/30/2017
ms.assetid: 270eaeba-9492-4532-af9f-403ce5c9935b
ms.openlocfilehash: 5576d6f893aa405d454758387334b85a473b0c73
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33517944"
---
# <a name="task-1-create-a-new-windows-presentation-foundation-application"></a><span data-ttu-id="78d63-102">任务 1：创建一个新的 Windows Presentation Foundation 应用程序</span><span class="sxs-lookup"><span data-stu-id="78d63-102">Task 1: Create a New Windows Presentation Foundation Application</span></span>
<span data-ttu-id="78d63-103">在此任务中，你将使用 WPF 应用程序 Visual Studio 模板创建空的 Windows Presentation Foundation (WPF) 应用程序并添加对相应的引用[!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]工作流程序集。</span><span class="sxs-lookup"><span data-stu-id="78d63-103">In this task, you will create an empty Windows Presentation Foundation (WPF) application by using the WPF Application Visual Studio template and add references to the appropriate [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] workflow assemblies.</span></span>  
  
### <a name="to-create-the-wpf-application-project"></a><span data-ttu-id="78d63-104">创建 WPF 应用程序项目</span><span class="sxs-lookup"><span data-stu-id="78d63-104">To create the WPF Application project</span></span>  
  
1.  <span data-ttu-id="78d63-105">打开 Visual Studio 并在**文件**菜单上，指向**新建**，然后单击**项目**。</span><span class="sxs-lookup"><span data-stu-id="78d63-105">Open Visual Studio and on the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="78d63-106">在**新项目**对话框框中，选择**Visual C#** 或**Visual Basic**从**已安装的模板**的左侧窗格中框。</span><span class="sxs-lookup"><span data-stu-id="78d63-106">In the **New Project** dialog box, select either **Visual C#** or **Visual Basic** from the **Installed Templates** pane on the left side of the box.</span></span> <span data-ttu-id="78d63-107">如果未出现所选的语言，查找在**其他语言**。</span><span class="sxs-lookup"><span data-stu-id="78d63-107">If the language of your choice does not appear, look under **Other Languages**.</span></span>  
  
3.  <span data-ttu-id="78d63-108">选择**Windows**中**已安装的模板**窗格。</span><span class="sxs-lookup"><span data-stu-id="78d63-108">Select **Windows** in the **Installed Templates** pane.</span></span>  
  
4.  <span data-ttu-id="78d63-109">在顶部窗格中，确认 （默认值） **.NET Framework 4**已选定在下拉列表框中，然后选择**WPF 应用程序**。</span><span class="sxs-lookup"><span data-stu-id="78d63-109">In the top pane, confirm that (the default value) **.NET Framework 4** has been selected in the drop-down list box, and then select **WPF Application**.</span></span>  
  
5.  <span data-ttu-id="78d63-110">设置到项目的名称**HostingApplication**在窗口的底部。</span><span class="sxs-lookup"><span data-stu-id="78d63-110">Set the name of the project to **HostingApplication** at the bottom of the window.</span></span>  
  
6.  <span data-ttu-id="78d63-111">将解决方案名称设置为**RehostingTheDesigner**。</span><span class="sxs-lookup"><span data-stu-id="78d63-111">Set the solution name to **RehostingTheDesigner**.</span></span>  
  
7.  <span data-ttu-id="78d63-112">单击**确定**创建应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="78d63-112">Click **OK** to create the application project.</span></span> <span data-ttu-id="78d63-113">Visual Studio 创建你的应用程序一个基本 WPF UI，并包括相应的 XAML 和代码隐藏文件。</span><span class="sxs-lookup"><span data-stu-id="78d63-113">Visual Studio creates a basic WPF UI for your application and includes the appropriate XAML and code-behind files.</span></span>  
  
8.  <span data-ttu-id="78d63-114">将引用添加到**WorkflowModel**程序集。</span><span class="sxs-lookup"><span data-stu-id="78d63-114">Add references to **WorkflowModel** assemblies.</span></span> <span data-ttu-id="78d63-115">为此，请在**解决方案资源管理器**，右键单击**HostingApplication**项目，然后选择**添加引用**。</span><span class="sxs-lookup"><span data-stu-id="78d63-115">To do this, in **Solution Explorer**, right-click the **HostingApplication** project and select **Add Reference**.</span></span>  
  
9. <span data-ttu-id="78d63-116">在**添加引用**对话框中，单击 **.NET**选项卡上，请按住 CTRL 键，选择下列程序集，，然后单击**确定**:</span><span class="sxs-lookup"><span data-stu-id="78d63-116">In the **Add Reference** dialog box, click the **.NET** tab, hold down the CTRL key, select the following assemblies, and then click **OK**:</span></span>  
  
    -   <span data-ttu-id="78d63-117">System.Activities</span><span class="sxs-lookup"><span data-stu-id="78d63-117">System.Activities</span></span>  
  
    -   <span data-ttu-id="78d63-118">System.Activities.Presentation</span><span class="sxs-lookup"><span data-stu-id="78d63-118">System.Activities.Presentation</span></span>  
  
    -   <span data-ttu-id="78d63-119">System.Activities.Core.Presentation</span><span class="sxs-lookup"><span data-stu-id="78d63-119">System.Activities.Core.Presentation</span></span>  
  
10. <span data-ttu-id="78d63-120">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="78d63-120">Click **OK**.</span></span>  
  
11. <span data-ttu-id="78d63-121">请参阅[任务 2： 承载工作流设计器](../../../docs/framework/windows-workflow-foundation/task-2-host-the-workflow-designer.md)若要了解如何承载工作流设计器设计画布。</span><span class="sxs-lookup"><span data-stu-id="78d63-121">See [Task 2: Host the Workflow Designer](../../../docs/framework/windows-workflow-foundation/task-2-host-the-workflow-designer.md) to learn how to host the workflow designer design canvas.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78d63-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="78d63-122">See Also</span></span>  
 [<span data-ttu-id="78d63-123">重新托管工作流设计器</span><span class="sxs-lookup"><span data-stu-id="78d63-123">Rehosting the Workflow Designer</span></span>](../../../docs/framework/windows-workflow-foundation/rehosting-the-workflow-designer.md)  
 [<span data-ttu-id="78d63-124">任务 2：托管工作流设计器</span><span class="sxs-lookup"><span data-stu-id="78d63-124">Task 2: Host the Workflow Designer</span></span>](../../../docs/framework/windows-workflow-foundation/task-2-host-the-workflow-designer.md)
