---
title: 任务 1：创建一个新的 Windows Presentation Foundation 应用程序
ms.date: 03/30/2017
ms.assetid: 270eaeba-9492-4532-af9f-403ce5c9935b
ms.openlocfilehash: 3205840da575041b449eb841fc8084e89937fca7
ms.sourcegitcommit: 10db6551ea3c971470cf5d2cc21ba1cbcefe5c55
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/08/2019
ms.locfileid: "72031893"
---
# <a name="task-1-create-a-new-windows-presentation-foundation-application"></a><span data-ttu-id="bbd09-102">任务 1：创建一个新的 Windows Presentation Foundation 应用程序</span><span class="sxs-lookup"><span data-stu-id="bbd09-102">Task 1: Create a New Windows Presentation Foundation Application</span></span>

<span data-ttu-id="bbd09-103">在此任务中，您将使用 WPF 应用程序 Visual Studio 模板创建一个空的 Windows Presentation Foundation （WPF）应用程序，并向相应的 [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] 工作流程序集添加引用。</span><span class="sxs-lookup"><span data-stu-id="bbd09-103">In this task, you will create an empty Windows Presentation Foundation (WPF) application by using the WPF Application Visual Studio template and add references to the appropriate [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] workflow assemblies.</span></span>  
  
## <a name="to-create-the-wpf-application-project"></a><span data-ttu-id="bbd09-104">创建 WPF 应用程序项目</span><span class="sxs-lookup"><span data-stu-id="bbd09-104">To create the WPF Application project</span></span>

1. <span data-ttu-id="bbd09-105">打开 Visual Studio，在 "**文件**" 菜单上，指向 "**新建**"，然后单击 "**项目**"。</span><span class="sxs-lookup"><span data-stu-id="bbd09-105">Open Visual Studio and on the **File** menu, point to **New**, and then click **Project**.</span></span>

2. <span data-ttu-id="bbd09-106">在 "**新建项目**" 对话框中，从框左侧的 "**已安装的模板**" 窗格中选择 "**视觉C#对象**" 或 " **Visual Basic** "。</span><span class="sxs-lookup"><span data-stu-id="bbd09-106">In the **New Project** dialog box, select either **Visual C#** or **Visual Basic** from the **Installed Templates** pane on the left side of the box.</span></span> <span data-ttu-id="bbd09-107">如果你选择的语言未显示，请在 "**其他语言**" 下查看。</span><span class="sxs-lookup"><span data-stu-id="bbd09-107">If the language of your choice does not appear, look under **Other Languages**.</span></span>

3. <span data-ttu-id="bbd09-108">在 "**已安装的模板**" 窗格中选择 "**窗口**"。</span><span class="sxs-lookup"><span data-stu-id="bbd09-108">Select **Windows** in the **Installed Templates** pane.</span></span>

4. <span data-ttu-id="bbd09-109">在顶部窗格中，确认已在下拉列表框中选择了 " **.NET Framework 4** " （默认值），然后选择 " **WPF 应用程序**"。</span><span class="sxs-lookup"><span data-stu-id="bbd09-109">In the top pane, confirm that (the default value) **.NET Framework 4** has been selected in the drop-down list box, and then select **WPF Application**.</span></span>

5. <span data-ttu-id="bbd09-110">在窗口底部，将项目的名称设置为**HostingApplication** 。</span><span class="sxs-lookup"><span data-stu-id="bbd09-110">Set the name of the project to **HostingApplication** at the bottom of the window.</span></span>

6. <span data-ttu-id="bbd09-111">将解决方案名称设置为**RehostingTheDesigner**。</span><span class="sxs-lookup"><span data-stu-id="bbd09-111">Set the solution name to **RehostingTheDesigner**.</span></span>

7. <span data-ttu-id="bbd09-112">单击 **"确定"** 以创建应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="bbd09-112">Click **OK** to create the application project.</span></span> <span data-ttu-id="bbd09-113">Visual Studio 为应用程序创建一个基本 WPF UI，并包含相应的 XAML 和代码隐藏文件。</span><span class="sxs-lookup"><span data-stu-id="bbd09-113">Visual Studio creates a basic WPF UI for your application and includes the appropriate XAML and code-behind files.</span></span>

8. <span data-ttu-id="bbd09-114">添加对**WorkflowModel**程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="bbd09-114">Add references to **WorkflowModel** assemblies.</span></span> <span data-ttu-id="bbd09-115">为此，请在**解决方案资源管理器**中，右键单击**HostingApplication**项目，然后选择 "**添加引用**"。</span><span class="sxs-lookup"><span data-stu-id="bbd09-115">To do this, in **Solution Explorer**, right-click the **HostingApplication** project and select **Add Reference**.</span></span>

9. <span data-ttu-id="bbd09-116">在 "**添加引用**" 对话框中，单击 " **.net** " 选项卡，按住 CTRL 键，选择以下程序集，然后单击 **"确定"** ：</span><span class="sxs-lookup"><span data-stu-id="bbd09-116">In the **Add Reference** dialog box, click the **.NET** tab, hold down the CTRL key, select the following assemblies, and then click **OK**:</span></span>

    - <span data-ttu-id="bbd09-117">System.Activities</span><span class="sxs-lookup"><span data-stu-id="bbd09-117">System.Activities</span></span>
    - <span data-ttu-id="bbd09-118">System.Activities.Presentation</span><span class="sxs-lookup"><span data-stu-id="bbd09-118">System.Activities.Presentation</span></span>
    - <span data-ttu-id="bbd09-119">System.Activities.Core.Presentation</span><span class="sxs-lookup"><span data-stu-id="bbd09-119">System.Activities.Core.Presentation</span></span>

10. <span data-ttu-id="bbd09-120">请参阅[任务2：宿主工作流设计器](task-2-host-the-workflow-designer.md)以了解如何承载工作流设计器设计画布。</span><span class="sxs-lookup"><span data-stu-id="bbd09-120">See [Task 2: Host the Workflow Designer](task-2-host-the-workflow-designer.md) to learn how to host the workflow designer design canvas.</span></span>

## <a name="see-also"></a><span data-ttu-id="bbd09-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bbd09-121">See also</span></span>

- [<span data-ttu-id="bbd09-122">重新托管工作流设计器</span><span class="sxs-lookup"><span data-stu-id="bbd09-122">Rehosting the Workflow Designer</span></span>](rehosting-the-workflow-designer.md)
- [<span data-ttu-id="bbd09-123">任务 2：托管工作流设计器</span><span class="sxs-lookup"><span data-stu-id="bbd09-123">Task 2: Host the Workflow Designer</span></span>](task-2-host-the-workflow-designer.md)
