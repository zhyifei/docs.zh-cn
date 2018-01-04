---
title: "如何：使用设计器将 Windows 窗体控件绑定到类型"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- controls [Windows Forms], binding to a type
- BindingSource component [Windows Forms], binding to a type
- types [Windows Forms], binding controls to
ms.assetid: 5ab984b5-c2d0-4638-a572-1c84013e8746
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a25b0dc81a6511698394eb86343f09051befc87f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-bind-a-windows-forms-control-to-a-type-using-the-designer"></a><span data-ttu-id="fb3cc-102">如何：使用设计器将 Windows 窗体控件绑定到类型</span><span class="sxs-lookup"><span data-stu-id="fb3cc-102">How to: Bind a Windows Forms Control to a Type Using the Designer</span></span>
<span data-ttu-id="fb3cc-103">在生成与数据交互的控件时，有时需要将控件绑定到类型而非对象。</span><span class="sxs-lookup"><span data-stu-id="fb3cc-103">When you are building controls that interact with data, you sometimes need to bind a control to a type, rather than an object.</span></span> <span data-ttu-id="fb3cc-104">当数据可能不可用，但仍然希望数据绑定控件显示类型的公共接口中的信息时，通常需要在设计时将控件绑定到类型。</span><span class="sxs-lookup"><span data-stu-id="fb3cc-104">You typically need to bind a control to a type at design time, when data may not be available, but you still want your data-bound controls to display data from a type's public interface.</span></span> <span data-ttu-id="fb3cc-105">以下过程演示如何创建一个新<xref:System.Windows.Forms.BindingSource>，它是绑定到一种类型，然后如何将绑定到该类型的属性之一<xref:System.Windows.Forms.TextBox.Text%2A>属性<xref:System.Windows.Forms.TextBox>。</span><span class="sxs-lookup"><span data-stu-id="fb3cc-105">The following procedures demonstrate how to create a new <xref:System.Windows.Forms.BindingSource> that is bound to a type, and then how to bind one of the type's properties to the <xref:System.Windows.Forms.TextBox.Text%2A> property of a <xref:System.Windows.Forms.TextBox>.</span></span>  
  
### <a name="to-bind-the-bindingsource-to-a-type"></a><span data-ttu-id="fb3cc-106">将 BindingSource 绑定到类型</span><span class="sxs-lookup"><span data-stu-id="fb3cc-106">To bind the BindingSource to a type</span></span>  
  
1.  <span data-ttu-id="fb3cc-107">创建 Windows 窗体项目。</span><span class="sxs-lookup"><span data-stu-id="fb3cc-107">Create a Windows Forms project.</span></span>  
  
     <span data-ttu-id="fb3cc-108">有关详细信息，请参阅 [How to: Create a Windows Application Project](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa)。</span><span class="sxs-lookup"><span data-stu-id="fb3cc-108">For more information, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa).</span></span>  
  
2.  <span data-ttu-id="fb3cc-109">在**设计**视图中，将<xref:System.Windows.Forms.BindingSource>组件拖放到窗体。</span><span class="sxs-lookup"><span data-stu-id="fb3cc-109">In **Design** view, drag a <xref:System.Windows.Forms.BindingSource> component onto the form.</span></span>  
  
3.  <span data-ttu-id="fb3cc-110">在**属性**窗口中，单击的箭头<xref:System.Windows.Forms.BindingSource.DataSource%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="fb3cc-110">In the **Properties** window, click the arrow for the <xref:System.Windows.Forms.BindingSource.DataSource%2A> property.</span></span>  
  
4.  <span data-ttu-id="fb3cc-111">在“DataSource UI 类型编辑器”中，单击“添加项目数据源”。</span><span class="sxs-lookup"><span data-stu-id="fb3cc-111">In the **DataSource UI Type Editor**, click **Add Project Data Source**.</span></span>  
  
5.  <span data-ttu-id="fb3cc-112">在“选择数据源类型”页上，选择“对象”，并单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="fb3cc-112">On the **Choose a Data Source Type** page, select **Object** and click **Next**.</span></span>  
  
6.  <span data-ttu-id="fb3cc-113">选择要绑定到的类型：</span><span class="sxs-lookup"><span data-stu-id="fb3cc-113">Select the type to bind to:</span></span>  
  
    -   <span data-ttu-id="fb3cc-114">如果要绑定到的类型位于当前项目，或者包含该类型的程序集已经作为引用添加，请展开节点以找到所需类型，然后选择它。</span><span class="sxs-lookup"><span data-stu-id="fb3cc-114">If the type you want to bind to is in the current project, or the assembly that contains the type is already added as a reference, expand the nodes to find the type you want, and then select it.</span></span>  
  
         <span data-ttu-id="fb3cc-115">或</span><span class="sxs-lookup"><span data-stu-id="fb3cc-115">-or-</span></span>  
  
    -   <span data-ttu-id="fb3cc-116">如果要绑定到的类型在另一个程序集中，当前不在引用列表中，请单击“添加引用”，然后单击“项目”选项卡。选择包含所需业务对象的项目，然后单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="fb3cc-116">If the type you want to bind to is in another assembly, not currently in the list of references, click **Add Reference**, and then click the **Projects** tab. Select the project that contains the business object you want and click **OK**.</span></span> <span data-ttu-id="fb3cc-117">此项目将显示在程序集列表中，因此可以展开节点以查找所需类型，然后选择它。</span><span class="sxs-lookup"><span data-stu-id="fb3cc-117">This project will appear in the list of assemblies, so you can expand the nodes to find the type you want, and then select it.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="fb3cc-118">如果要绑定到框架或 Microsoft 程序集中的类型，请清除“隐藏以 Microsoft 或 System 开头的程序集”复选框。</span><span class="sxs-lookup"><span data-stu-id="fb3cc-118">If you want to bind to a type in a framework or Microsoft assembly, clear the **Hide assemblies that begin with Microsoft or System** check box.</span></span>  
  
7.  <span data-ttu-id="fb3cc-119">单击“下一步” ，再单击“完成” 。</span><span class="sxs-lookup"><span data-stu-id="fb3cc-119">Click **Next**, and then click **Finish**.</span></span>  
  
### <a name="to-bind-the-control-to-the-bindingsource"></a><span data-ttu-id="fb3cc-120">将控件绑定到 BindingSource</span><span class="sxs-lookup"><span data-stu-id="fb3cc-120">To bind the control to the BindingSource</span></span>  
  
1.  <span data-ttu-id="fb3cc-121">在窗体上添加一个 <xref:System.Windows.Forms.TextBox> 控件。</span><span class="sxs-lookup"><span data-stu-id="fb3cc-121">Add a <xref:System.Windows.Forms.TextBox> to the form.</span></span>  
  
2.  <span data-ttu-id="fb3cc-122">在“属性”窗口中，展开“(DataBindings)”节点。</span><span class="sxs-lookup"><span data-stu-id="fb3cc-122">In the **Properties** window, expand the **(DataBindings)** node.</span></span>  
  
3.  <span data-ttu-id="fb3cc-123">单击箭头旁边<xref:System.Windows.Forms.TextBox.Text%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="fb3cc-123">Click the arrow next to the <xref:System.Windows.Forms.TextBox.Text%2A> property.</span></span>  
  
4.  <span data-ttu-id="fb3cc-124">在**数据源的 UI 类型编辑器**，展开的节点<xref:System.Windows.Forms.BindingSource>之前，添加并选择你想要将绑定到绑定类型的属性<xref:System.Windows.Forms.TextBox.Text%2A>属性<xref:System.Windows.Forms.TextBox>。</span><span class="sxs-lookup"><span data-stu-id="fb3cc-124">In the **DataSource UI Type Editor**, expand the node for the <xref:System.Windows.Forms.BindingSource> added previously, and select the property of the bound type you want to bind to the <xref:System.Windows.Forms.TextBox.Text%2A> property of the <xref:System.Windows.Forms.TextBox>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb3cc-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="fb3cc-125">See Also</span></span>  
 [<span data-ttu-id="fb3cc-126">BindingSource 组件</span><span class="sxs-lookup"><span data-stu-id="fb3cc-126">BindingSource Component</span></span>](../../../../docs/framework/winforms/controls/bindingsource-component.md)  
 [<span data-ttu-id="fb3cc-127">如何：将 Windows 窗体控件绑定到类型</span><span class="sxs-lookup"><span data-stu-id="fb3cc-127">How to: Bind a Windows Forms Control to a Type</span></span>](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-type.md)  
 [<span data-ttu-id="fb3cc-128">在 Visual Studio 中将控件绑定到数据</span><span class="sxs-lookup"><span data-stu-id="fb3cc-128">Bind controls to data in Visual Studio</span></span>](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio)
