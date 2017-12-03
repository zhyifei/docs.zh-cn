---
title: "如何：创建自定义活动模板"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6760a5cc-6eb8-465f-b4fa-f89b39539429
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2ae81b96a348712af58c5e8527f0f04a59689368
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-create-a-custom-activity-template"></a><span data-ttu-id="c3d0d-102">如何：创建自定义活动模板</span><span class="sxs-lookup"><span data-stu-id="c3d0d-102">How to: Create a Custom Activity Template</span></span>
<span data-ttu-id="c3d0d-103">可使用自定义活动模板来自定义活动（包括自定义复合活动）的配置，使用户无需单独创建每个活动并手动配置其属性和其他设置。</span><span class="sxs-lookup"><span data-stu-id="c3d0d-103">Custom activity templates are used to customize the configuration of activities, including custom composite activities, so that users do not have to create each activity individually and configure their properties and other settings manually.</span></span> <span data-ttu-id="c3d0d-104">这些自定义模板可以使其可在**工具箱**上[!INCLUDE[wfd1](../../../includes/wfd1-md.md)]或从重新承载设计器中，从该用户可以将它们拖到预配置的设计图面。</span><span class="sxs-lookup"><span data-stu-id="c3d0d-104">These custom templates can be made available in the **Toolbox** on the [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] or from a rehosted designer, from which users can drag them onto the preconfigured design surface.</span></span> [!INCLUDE[wfd2](../../../includes/wfd2-md.md)]<span data-ttu-id="c3d0d-105">附带了很好此类模板的示例： [SendAndReceiveReply 模板设计器](/visualstudio/workflow-designer/sendandreceivereply-template-designer)和[ReceiveAndSendReply 模板设计器](/visualstudio/workflow-designer/receiveandsendreply-template-designer)中[消息传递活动设计器](/visualstudio/workflow-designer/messaging-activity-designers)类别。</span><span class="sxs-lookup"><span data-stu-id="c3d0d-105"> ships with good examples of such templates: the [SendAndReceiveReply Template Designer](/visualstudio/workflow-designer/sendandreceivereply-template-designer) and the [ReceiveAndSendReply Template Designer](/visualstudio/workflow-designer/receiveandsendreply-template-designer) in the [Messaging Activity Designers](/visualstudio/workflow-designer/messaging-activity-designers) category.</span></span>  
  
 <span data-ttu-id="c3d0d-106">本主题中的第一个过程描述如何创建自定义活动模板**延迟**活动和第二个过程简要介绍如何在中提供[!INCLUDE[wfd2](../../../includes/wfd2-md.md)]验证该自定义模板是否有效。</span><span class="sxs-lookup"><span data-stu-id="c3d0d-106">The first procedure in this topic describes how to create a custom activity template for a **Delay** activity and the second procedure describes briefly how to make it available in a [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] to verify that the custom template works.</span></span>  
  
 <span data-ttu-id="c3d0d-107">自定义活动模板必须实现 <xref:System.Activities.Presentation.IActivityTemplateFactory>。</span><span class="sxs-lookup"><span data-stu-id="c3d0d-107">Custom activity templates must implement the <xref:System.Activities.Presentation.IActivityTemplateFactory>.</span></span> <span data-ttu-id="c3d0d-108">此接口具有一个 <xref:System.Activities.Presentation.IActivityTemplateFactory.Create%2A> 方法，可利用此方法创建和配置模板中使用的活动实例。</span><span class="sxs-lookup"><span data-stu-id="c3d0d-108">The interface has a single <xref:System.Activities.Presentation.IActivityTemplateFactory.Create%2A> method with which you can create and configure the activity instances used in the template.</span></span>  
  
### <a name="to-create-a-template-for-the-delay-activity"></a><span data-ttu-id="c3d0d-109">为 Delay 活动创建模板</span><span class="sxs-lookup"><span data-stu-id="c3d0d-109">To create a template for the Delay activity</span></span>  
  
1.  <span data-ttu-id="c3d0d-110">启动 [!INCLUDE[vs2010](../../../includes/vs2010-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c3d0d-110">Start [!INCLUDE[vs2010](../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="c3d0d-111">上**文件**菜单上，指向**新建**，然后选择**项目**。</span><span class="sxs-lookup"><span data-stu-id="c3d0d-111">On the **File** menu, point to **New**, and then select **Project**.</span></span>  
  
     <span data-ttu-id="c3d0d-112">**“新建项目”** 对话框随即打开。</span><span class="sxs-lookup"><span data-stu-id="c3d0d-112">The **New Project** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="c3d0d-113">在**项目类型**窗格中，选择**工作流**从**Visual C#**项目或**Visual Basic**分组，具体取决于你语言首选项。</span><span class="sxs-lookup"><span data-stu-id="c3d0d-113">In the **Project Types** pane, select **Workflow** from either the **Visual C#** projects or **Visual Basic** groupings depending on your language preference.</span></span>  
  
4.  <span data-ttu-id="c3d0d-114">在**模板**窗格中，选择**活动库**。</span><span class="sxs-lookup"><span data-stu-id="c3d0d-114">In the **Templates** pane, select **Activity Library**.</span></span>  
  
5.  <span data-ttu-id="c3d0d-115">在**名称**框中，输入`DelayActivityTemplate`。</span><span class="sxs-lookup"><span data-stu-id="c3d0d-115">In the **Name** box, enter `DelayActivityTemplate`.</span></span>  
  
6.  <span data-ttu-id="c3d0d-116">接受中的默认值**位置**和**解决方案名称**文本框中，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="c3d0d-116">Accept the defaults in the **Location** and **Solution name** text boxes, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="c3d0d-117">右击 DelayActivityTemplate 项目中的引用目录**解决方案资源管理器**选择**添加引用**以打开**添加引用**对话框。</span><span class="sxs-lookup"><span data-stu-id="c3d0d-117">Right-click the References directory of the DelayActivityTemplate project in **Solution Explorer** and choose **Add Reference** to open the **Add Reference** dialog box.</span></span>  
  
8.  <span data-ttu-id="c3d0d-118">转到**.NET**选项卡并选择**PresentationFramework**从**组件名称**列在左侧和单击**确定**添加的引用对 PresentationFramework.dll 文件中。</span><span class="sxs-lookup"><span data-stu-id="c3d0d-118">Go to the **.NET** tab and select **PresentationFramework** from the **Component Name** column on the left and click **OK** to add a reference to the PresentationFramework.dll file.</span></span>  
  
9. <span data-ttu-id="c3d0d-119">重复此过程以添加对 System.Activities.Presentation.dll 文件和 WindowsBase.dll 文件的引用。</span><span class="sxs-lookup"><span data-stu-id="c3d0d-119">Repeat this procedure to add references to the System.Activities.Presentation.dll and the WindowsBase.dll files.</span></span>  
  
10. <span data-ttu-id="c3d0d-120">在右击 DelayActivityTemplate 项目**解决方案资源管理器**选择**添加**然后**新项**以打开**添加新项**对话框。</span><span class="sxs-lookup"><span data-stu-id="c3d0d-120">Right-click the DelayActivityTemplate project in **Solution Explorer** and choose **Add** and then **New Item** to open the **Add New Item** dialog box.</span></span>  
  
11. <span data-ttu-id="c3d0d-121">选择**类**模板，将其命名为 MyDelayTemplate，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="c3d0d-121">Select the **Class** template, name it MyDelayTemplate, and then click **OK**.</span></span>  
  
12. <span data-ttu-id="c3d0d-122">打开 MyDelayTemplate.cs 文件并添加下面的语句。</span><span class="sxs-lookup"><span data-stu-id="c3d0d-122">Open the MyDelayTemplate.cs file and add the following statements.</span></span>  
  
    ```  
    //Namespaces added  
    using System.Activities;  
    using System.Activities.Statements;  
    using System.Activities.Presentation;  
    using System.Windows;  
    ```  
  
13. <span data-ttu-id="c3d0d-123">使用带有以下代码的 <xref:System.Activities.Presentation.IActivityTemplateFactory> 类来实现 `MyDelayActivity`。</span><span class="sxs-lookup"><span data-stu-id="c3d0d-123">Implement the <xref:System.Activities.Presentation.IActivityTemplateFactory> with the `MyDelayActivity` class with the following code.</span></span> <span data-ttu-id="c3d0d-124">这会将延迟时间配置为 10 秒。</span><span class="sxs-lookup"><span data-stu-id="c3d0d-124">This configures the delay to have a duration of 10 seconds.</span></span>  
  
    ```  
    public sealed class MyDelayActivity : IActivityTemplateFactory  
    {  
        public Activity Create(System.Windows.DependencyObject target)  
        {  
            return new System.Activities.Statements.Delay  
            {  
                DisplayName = "DelayActivityTemplate",  
                Duration = new TimeSpan(0, 0, 10)  
  
            };  
        }  
    }  
    ```  
  
14. <span data-ttu-id="c3d0d-125">选择**生成解决方案**从**生成**菜单以生成 DelayActivityTemplate.dll 文件。</span><span class="sxs-lookup"><span data-stu-id="c3d0d-125">Select **Build Solution** from the **Build** menu to generate the DelayActivityTemplate.dll file.</span></span>  
  
### <a name="to-make-the-template-available-in-a-workflow-designer"></a><span data-ttu-id="c3d0d-126">使模板在工作流设计器中可用</span><span class="sxs-lookup"><span data-stu-id="c3d0d-126">To make the template available in a Workflow Designer</span></span>  
  
1.  <span data-ttu-id="c3d0d-127">右击 DelayActivityTemplate 解决方案中的**解决方案资源管理器**选择**添加**然后**新项目**以打开**添加新项目**对话框。</span><span class="sxs-lookup"><span data-stu-id="c3d0d-127">Right-click the DelayActivityTemplate solution in **Solution Explorer** and choose **Add** and then **New Project** to open the **Add New Project** dialog box.</span></span>  
  
2.  <span data-ttu-id="c3d0d-128">选择**工作流控制台应用程序**模板，将其命名为`CustomActivityTemplateApp`，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="c3d0d-128">Select the **Workflow Console Application** template, name it `CustomActivityTemplateApp`, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="c3d0d-129">右击 CustomActivityTemplateApp 项目中的引用目录**解决方案资源管理器**选择**添加引用**以打开**添加引用**对话框框。</span><span class="sxs-lookup"><span data-stu-id="c3d0d-129">Right-click the References directory of the CustomActivityTemplateApp project in **Solution Explorer** and choose **Add Reference** to open the **Add Reference** dialog box.</span></span>  
  
4.  <span data-ttu-id="c3d0d-130">转到**项目**选项卡并选择**DelayActivityTemplate**从**项目名称**列在左侧和单击**确定**添加引用到第一个过程中创建的 DelayActivityTemplate.dll 文件。</span><span class="sxs-lookup"><span data-stu-id="c3d0d-130">Go to the **Projects** tab and select **DelayActivityTemplate** from the **Project Name** column on the left and click **OK** to add a reference to the DelayActivityTemplate.dll file that you created in the first procedure.</span></span>  
  
5.  <span data-ttu-id="c3d0d-131">右击 CustomActivityTemplateApp 项目中的**解决方案资源管理器**选择**生成**编译应用程序。</span><span class="sxs-lookup"><span data-stu-id="c3d0d-131">Right-click the CustomActivityTemplateApp project in **Solution Explorer** and choose **Build** to compile the application.</span></span>  
  
6.  <span data-ttu-id="c3d0d-132">右击 CustomActivityTemplateApp 项目中的**解决方案资源管理器**选择**设为启动项目**。</span><span class="sxs-lookup"><span data-stu-id="c3d0d-132">Right-click the CustomActivityTemplateApp project in **Solution Explorer** and choose **Set as Startup Project**.</span></span>  
  
7.  <span data-ttu-id="c3d0d-133">选择**启动但不调试**从**调试**菜单，然后按任意键以继续出现提示时，在 cmd.exe 窗口中。</span><span class="sxs-lookup"><span data-stu-id="c3d0d-133">Select **Start Without Debugging** from the **Debug** menu and press any key to continue when prompted from the cmd.exe window.</span></span>  
  
8.  <span data-ttu-id="c3d0d-134">打开 Workflow1.xaml 文件并打开**工具箱**。</span><span class="sxs-lookup"><span data-stu-id="c3d0d-134">Open the Workflow1.xaml file and open the **Toolbox**.</span></span>  
  
9. <span data-ttu-id="c3d0d-135">找到**MyDelayActivity**中的模板**DelayActivityTemplate**类别。</span><span class="sxs-lookup"><span data-stu-id="c3d0d-135">Locate the **MyDelayActivity** template in the **DelayActivityTemplate** category.</span></span> <span data-ttu-id="c3d0d-136">将此模板拖动到设计图面上。</span><span class="sxs-lookup"><span data-stu-id="c3d0d-136">Drag it onto the design surface.</span></span> <span data-ttu-id="c3d0d-137">在确认**属性**窗口，`Duration`属性设置为 10 秒。</span><span class="sxs-lookup"><span data-stu-id="c3d0d-137">Confirm in the **Properties** window that the `Duration` property has been set to 10 seconds.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c3d0d-138">示例</span><span class="sxs-lookup"><span data-stu-id="c3d0d-138">Example</span></span>  
 <span data-ttu-id="c3d0d-139">MyDelayActivity.cs 文件应包含以下代码。</span><span class="sxs-lookup"><span data-stu-id="c3d0d-139">The MyDelayActivity.cs file should contain the following code.</span></span>  
  
```  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
  
//Namespaces added  
using System.Activities;  
using System.Activities.Statements;  
using System.Activities.Presentation;  
using System.Windows;  
  
namespace DelayActivityTemplate  
{  
    public sealed class MyDelayActivity : IActivityTemplateFactory  
    {  
        public Activity Create(System.Windows.DependencyObject target)  
        {  
            return new System.Activities.Statements.Delay  
            {  
                DisplayName = "DelayActivityTemplate",  
                Duration = new TimeSpan(0, 0, 10)  
  
            };  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="c3d0d-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c3d0d-140">See Also</span></span>  
 <xref:System.Activities.Presentation.IActivityTemplateFactory>  
 [<span data-ttu-id="c3d0d-141">自定义工作流设计体验</span><span class="sxs-lookup"><span data-stu-id="c3d0d-141">Customizing the Workflow Design Experience</span></span>](../../../docs/framework/windows-workflow-foundation/customizing-the-workflow-design-experience.md)
