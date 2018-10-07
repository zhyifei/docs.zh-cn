---
title: 如何：创建自定义活动模板
ms.date: 03/30/2017
ms.assetid: 6760a5cc-6eb8-465f-b4fa-f89b39539429
ms.openlocfilehash: 87acf0d084154c9c3e5cbc97da4af9821709f0a5
ms.sourcegitcommit: 8c28ab17c26bf08abbd004cc37651985c68841b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2018
ms.locfileid: "48847591"
---
# <a name="how-to-create-a-custom-activity-template"></a><span data-ttu-id="9e2f4-102">如何：创建自定义活动模板</span><span class="sxs-lookup"><span data-stu-id="9e2f4-102">How to: Create a Custom Activity Template</span></span>

<span data-ttu-id="9e2f4-103">可使用自定义活动模板来自定义活动（包括自定义复合活动）的配置，使用户无需单独创建每个活动并手动配置其属性和其他设置。</span><span class="sxs-lookup"><span data-stu-id="9e2f4-103">Custom activity templates are used to customize the configuration of activities, including custom composite activities, so that users do not have to create each activity individually and configure their properties and other settings manually.</span></span> <span data-ttu-id="9e2f4-104">这些自定义模板可用于在**工具箱**上[!INCLUDE[wfd1](../../../includes/wfd1-md.md)]或从重新承载设计器，从该用户可以将它们拖到预配置的设计图面。</span><span class="sxs-lookup"><span data-stu-id="9e2f4-104">These custom templates can be made available in the **Toolbox** on the [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] or from a rehosted designer, from which users can drag them onto the preconfigured design surface.</span></span> [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] <span data-ttu-id="9e2f4-105">附带了此类模板的很好的示例： [SendAndReceiveReply 模板设计器](/visualstudio/workflow-designer/sendandreceivereply-template-designer)并[ReceiveAndSendReply 模板设计器](/visualstudio/workflow-designer/receiveandsendreply-template-designer)中[消息传递活动设计器](/visualstudio/workflow-designer/messaging-activity-designers)类别。</span><span class="sxs-lookup"><span data-stu-id="9e2f4-105"> ships with good examples of such templates: the [SendAndReceiveReply Template Designer](/visualstudio/workflow-designer/sendandreceivereply-template-designer) and the [ReceiveAndSendReply Template Designer](/visualstudio/workflow-designer/receiveandsendreply-template-designer) in the [Messaging Activity Designers](/visualstudio/workflow-designer/messaging-activity-designers) category.</span></span>

 <span data-ttu-id="9e2f4-106">本主题中的第一个过程介绍如何创建自定义活动模板**延迟**活动和第二个过程简要描述如何使其可在[!INCLUDE[wfd2](../../../includes/wfd2-md.md)]若要验证的自定义模板是否正常工作。</span><span class="sxs-lookup"><span data-stu-id="9e2f4-106">The first procedure in this topic describes how to create a custom activity template for a **Delay** activity and the second procedure describes briefly how to make it available in a [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] to verify that the custom template works.</span></span>

 <span data-ttu-id="9e2f4-107">自定义活动模板必须实现 <xref:System.Activities.Presentation.IActivityTemplateFactory>。</span><span class="sxs-lookup"><span data-stu-id="9e2f4-107">Custom activity templates must implement the <xref:System.Activities.Presentation.IActivityTemplateFactory>.</span></span> <span data-ttu-id="9e2f4-108">此接口具有一个 <xref:System.Activities.Presentation.IActivityTemplateFactory.Create%2A> 方法，可利用此方法创建和配置模板中使用的活动实例。</span><span class="sxs-lookup"><span data-stu-id="9e2f4-108">The interface has a single <xref:System.Activities.Presentation.IActivityTemplateFactory.Create%2A> method with which you can create and configure the activity instances used in the template.</span></span>

## <a name="to-create-a-template-for-the-delay-activity"></a><span data-ttu-id="9e2f4-109">为 Delay 活动创建模板</span><span class="sxs-lookup"><span data-stu-id="9e2f4-109">To create a template for the Delay activity</span></span>

1.  <span data-ttu-id="9e2f4-110">启动 Visual Studio 2010。</span><span class="sxs-lookup"><span data-stu-id="9e2f4-110">Start Visual Studio 2010.</span></span>

2.  <span data-ttu-id="9e2f4-111">在“文件”菜单上，指向“新建”，然后选择“项目”。</span><span class="sxs-lookup"><span data-stu-id="9e2f4-111">On the **File** menu, point to **New**, and then select **Project**.</span></span>

     <span data-ttu-id="9e2f4-112">**“新建项目”** 对话框随即打开。</span><span class="sxs-lookup"><span data-stu-id="9e2f4-112">The **New Project** dialog box opens.</span></span>

3.  <span data-ttu-id="9e2f4-113">在中**项目类型**窗格中，选择**工作流**眖**Visual C#** 项目或**Visual Basic**分组，具体取决于你语言首选项。</span><span class="sxs-lookup"><span data-stu-id="9e2f4-113">In the **Project Types** pane, select **Workflow** from either the **Visual C#** projects or **Visual Basic** groupings depending on your language preference.</span></span>

4.  <span data-ttu-id="9e2f4-114">在中**模板**窗格中，选择**活动库**。</span><span class="sxs-lookup"><span data-stu-id="9e2f4-114">In the **Templates** pane, select **Activity Library**.</span></span>

5.  <span data-ttu-id="9e2f4-115">在中**名称**框中，输入`DelayActivityTemplate`。</span><span class="sxs-lookup"><span data-stu-id="9e2f4-115">In the **Name** box, enter `DelayActivityTemplate`.</span></span>

6.  <span data-ttu-id="9e2f4-116">接受中的默认值**位置**并**解决方案名称**文本框中，并单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="9e2f4-116">Accept the defaults in the **Location** and **Solution name** text boxes, and then click **OK**.</span></span>

7.  <span data-ttu-id="9e2f4-117">右击 DelayActivityTemplate 项目中引用目录**解决方案资源管理器**，然后选择**添加引用**以打开**添加引用**对话框。</span><span class="sxs-lookup"><span data-stu-id="9e2f4-117">Right-click the References directory of the DelayActivityTemplate project in **Solution Explorer** and choose **Add Reference** to open the **Add Reference** dialog box.</span></span>

8.  <span data-ttu-id="9e2f4-118">转到 **.NET**选项卡并选择**PresentationFramework**从**组件名称**列在左侧和单击**确定**添加的引用对 PresentationFramework.dll 文件中。</span><span class="sxs-lookup"><span data-stu-id="9e2f4-118">Go to the **.NET** tab and select **PresentationFramework** from the **Component Name** column on the left and click **OK** to add a reference to the PresentationFramework.dll file.</span></span>

9. <span data-ttu-id="9e2f4-119">重复此过程以添加对 System.Activities.Presentation.dll 文件和 WindowsBase.dll 文件的引用。</span><span class="sxs-lookup"><span data-stu-id="9e2f4-119">Repeat this procedure to add references to the System.Activities.Presentation.dll and the WindowsBase.dll files.</span></span>

10. <span data-ttu-id="9e2f4-120">右击 DelayActivityTemplate 项目中的**解决方案资源管理器**，然后选择**添加**，然后**新项**以打开**添加新项**对话框。</span><span class="sxs-lookup"><span data-stu-id="9e2f4-120">Right-click the DelayActivityTemplate project in **Solution Explorer** and choose **Add** and then **New Item** to open the **Add New Item** dialog box.</span></span>

11. <span data-ttu-id="9e2f4-121">选择**类**模板，其命名为 MyDelayTemplate，然后依次**确定**。</span><span class="sxs-lookup"><span data-stu-id="9e2f4-121">Select the **Class** template, name it MyDelayTemplate, and then click **OK**.</span></span>

12. <span data-ttu-id="9e2f4-122">打开 MyDelayTemplate.cs 文件并添加下面的语句。</span><span class="sxs-lookup"><span data-stu-id="9e2f4-122">Open the MyDelayTemplate.cs file and add the following statements.</span></span>

    ```
    //Namespaces added
    using System.Activities;
    using System.Activities.Statements;
    using System.Activities.Presentation;
    using System.Windows;
    ```

13. <span data-ttu-id="9e2f4-123">使用带有以下代码的 <xref:System.Activities.Presentation.IActivityTemplateFactory> 类来实现 `MyDelayActivity`。</span><span class="sxs-lookup"><span data-stu-id="9e2f4-123">Implement the <xref:System.Activities.Presentation.IActivityTemplateFactory> with the `MyDelayActivity` class with the following code.</span></span> <span data-ttu-id="9e2f4-124">这会将延迟时间配置为 10 秒。</span><span class="sxs-lookup"><span data-stu-id="9e2f4-124">This configures the delay to have a duration of 10 seconds.</span></span>

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

14. <span data-ttu-id="9e2f4-125">选择**生成解决方案**从**生成**菜单以生成 DelayActivityTemplate.dll 文件。</span><span class="sxs-lookup"><span data-stu-id="9e2f4-125">Select **Build Solution** from the **Build** menu to generate the DelayActivityTemplate.dll file.</span></span>

### <a name="to-make-the-template-available-in-a-workflow-designer"></a><span data-ttu-id="9e2f4-126">使模板在工作流设计器中可用</span><span class="sxs-lookup"><span data-stu-id="9e2f4-126">To make the template available in a Workflow Designer</span></span>

1.  <span data-ttu-id="9e2f4-127">右击 DelayActivityTemplate 解决方案中的**解决方案资源管理器**，然后选择**添加**，然后**新项目**以打开**添加新项目**对话框。</span><span class="sxs-lookup"><span data-stu-id="9e2f4-127">Right-click the DelayActivityTemplate solution in **Solution Explorer** and choose **Add** and then **New Project** to open the **Add New Project** dialog box.</span></span>

2.  <span data-ttu-id="9e2f4-128">选择**工作流控制台应用程序**模板，其命名`CustomActivityTemplateApp`，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="9e2f4-128">Select the **Workflow Console Application** template, name it `CustomActivityTemplateApp`, and then click **OK**.</span></span>

3.  <span data-ttu-id="9e2f4-129">右击 CustomActivityTemplateApp 项目中引用目录**解决方案资源管理器**，然后选择**添加引用**以打开**添加引用**对话框框。</span><span class="sxs-lookup"><span data-stu-id="9e2f4-129">Right-click the References directory of the CustomActivityTemplateApp project in **Solution Explorer** and choose **Add Reference** to open the **Add Reference** dialog box.</span></span>

4.  <span data-ttu-id="9e2f4-130">转到**项目**选项卡并选择**DelayActivityTemplate**从**项目名称**列在左侧和单击**确定**添加引用在第一个过程中创建的 DelayActivityTemplate.dll 文件。</span><span class="sxs-lookup"><span data-stu-id="9e2f4-130">Go to the **Projects** tab and select **DelayActivityTemplate** from the **Project Name** column on the left and click **OK** to add a reference to the DelayActivityTemplate.dll file that you created in the first procedure.</span></span>

5.  <span data-ttu-id="9e2f4-131">右击 CustomActivityTemplateApp 项目中的**解决方案资源管理器**，然后选择**生成**编译该应用程序。</span><span class="sxs-lookup"><span data-stu-id="9e2f4-131">Right-click the CustomActivityTemplateApp project in **Solution Explorer** and choose **Build** to compile the application.</span></span>

6.  <span data-ttu-id="9e2f4-132">右击 CustomActivityTemplateApp 项目中的**解决方案资源管理器**，然后选择**设为启动项目**。</span><span class="sxs-lookup"><span data-stu-id="9e2f4-132">Right-click the CustomActivityTemplateApp project in **Solution Explorer** and choose **Set as Startup Project**.</span></span>

7.  <span data-ttu-id="9e2f4-133">选择**启动但不调试**从**调试**菜单并按任意键以继续在 cmd.exe 窗口中出现提示时。</span><span class="sxs-lookup"><span data-stu-id="9e2f4-133">Select **Start Without Debugging** from the **Debug** menu and press any key to continue when prompted from the cmd.exe window.</span></span>

8.  <span data-ttu-id="9e2f4-134">打开 Workflow1.xaml 文件，并打开**工具箱**。</span><span class="sxs-lookup"><span data-stu-id="9e2f4-134">Open the Workflow1.xaml file and open the **Toolbox**.</span></span>

9. <span data-ttu-id="9e2f4-135">找到**MyDelayActivity**中的模板**DelayActivityTemplate**类别。</span><span class="sxs-lookup"><span data-stu-id="9e2f4-135">Locate the **MyDelayActivity** template in the **DelayActivityTemplate** category.</span></span> <span data-ttu-id="9e2f4-136">将此模板拖动到设计图面上。</span><span class="sxs-lookup"><span data-stu-id="9e2f4-136">Drag it onto the design surface.</span></span> <span data-ttu-id="9e2f4-137">在确认**属性**窗口的`Duration`属性设置为 10 秒。</span><span class="sxs-lookup"><span data-stu-id="9e2f4-137">Confirm in the **Properties** window that the `Duration` property has been set to 10 seconds.</span></span>

## <a name="example"></a><span data-ttu-id="9e2f4-138">示例</span><span class="sxs-lookup"><span data-stu-id="9e2f4-138">Example</span></span>
 <span data-ttu-id="9e2f4-139">MyDelayActivity.cs 文件应包含以下代码。</span><span class="sxs-lookup"><span data-stu-id="9e2f4-139">The MyDelayActivity.cs file should contain the following code.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="9e2f4-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="9e2f4-140">See Also</span></span>

- <xref:System.Activities.Presentation.IActivityTemplateFactory>
- [<span data-ttu-id="9e2f4-141">自定义工作流设计体验</span><span class="sxs-lookup"><span data-stu-id="9e2f4-141">Customizing the Workflow Design Experience</span></span>](../../../docs/framework/windows-workflow-foundation/customizing-the-workflow-design-experience.md)