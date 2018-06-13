---
title: 使用 ModelItem 编辑上下文
ms.date: 03/30/2017
ms.assetid: 7f9f1ea5-0147-4079-8eca-be94f00d3aa1
ms.openlocfilehash: 17334b5571148e494067683bdf96ebc4be4ea995
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33519144"
---
# <a name="using-the-modelitem-editing-context"></a><span data-ttu-id="4c5a8-102">使用 ModelItem 编辑上下文</span><span class="sxs-lookup"><span data-stu-id="4c5a8-102">Using the ModelItem Editing Context</span></span>
<span data-ttu-id="4c5a8-103"><xref:System.Activities.Presentation.Model.ModelItem> 编辑上下文是主机应用程序用来与设计器进行通信的对象。</span><span class="sxs-lookup"><span data-stu-id="4c5a8-103">The <xref:System.Activities.Presentation.Model.ModelItem> editing context is the object that the host application uses to communicate with the designer.</span></span> <span data-ttu-id="4c5a8-104"><xref:System.Activities.Presentation.EditingContext> 公开两个可以使用的方法：<xref:System.Activities.Presentation.EditingContext.Items%2A> 和 <xref:System.Activities.Presentation.EditingContext.Services%2A></span><span class="sxs-lookup"><span data-stu-id="4c5a8-104"><xref:System.Activities.Presentation.EditingContext> exposes two methods, <xref:System.Activities.Presentation.EditingContext.Items%2A> and <xref:System.Activities.Presentation.EditingContext.Services%2A>, which can be used</span></span>  
  
## <a name="the-items-collection"></a><span data-ttu-id="4c5a8-105">项集合</span><span class="sxs-lookup"><span data-stu-id="4c5a8-105">The Items collection</span></span>  
 <span data-ttu-id="4c5a8-106"><xref:System.Activities.Presentation.EditingContext.Items%2A> 集合用于访问主机与设计器之间共享的数据或所有设计器都可以使用的数据。</span><span class="sxs-lookup"><span data-stu-id="4c5a8-106">The <xref:System.Activities.Presentation.EditingContext.Items%2A> collection is used to access data that is shared between the host and the designer, or data that is available to all designers.</span></span> <span data-ttu-id="4c5a8-107">通过 <xref:System.Activities.Presentation.ContextItemManager> 类访问时，此集合具有以下功能：</span><span class="sxs-lookup"><span data-stu-id="4c5a8-107">This collection has the following capabilities, accessed via the <xref:System.Activities.Presentation.ContextItemManager> class:</span></span>  
  
1.  <xref:System.Activities.Presentation.ContextItemManager.GetValue%2A>  
  
2.  <xref:System.Activities.Presentation.ContextItemManager.Subscribe%2A>  
  
3.  <xref:System.Activities.Presentation.ContextItemManager.Unsubscribe%2A>  
  
4.  <xref:System.Activities.Presentation.ContextItemManager.SetValue%2A>  
  
## <a name="the-services-collection"></a><span data-ttu-id="4c5a8-108">服务集合</span><span class="sxs-lookup"><span data-stu-id="4c5a8-108">The Services collection</span></span>  
 <span data-ttu-id="4c5a8-109"><xref:System.Activities.Presentation.EditingContext.Services%2A> 集合用于访问设计器用来与主机交互的服务或访问所有设计器都使用的服务。</span><span class="sxs-lookup"><span data-stu-id="4c5a8-109">The <xref:System.Activities.Presentation.EditingContext.Services%2A> collection is used to access services that the designer uses to interact with the host, or services that all designers use.</span></span> <span data-ttu-id="4c5a8-110">此集合有以下需要注意的方法：</span><span class="sxs-lookup"><span data-stu-id="4c5a8-110">This collection has the following methods of note:</span></span>  
  
1.  <xref:System.Activities.Presentation.ServiceManager.Publish%2A>  
  
2.  <xref:System.Activities.Presentation.ServiceManager.Subscribe%2A>  
  
3.  <xref:System.Activities.Presentation.ServiceManager.Unsubscribe%2A>  
  
4.  <xref:System.Activities.Presentation.ServiceManager.GetService%2A>  
  
## <a name="assigning-a-designer-an-activity"></a><span data-ttu-id="4c5a8-111">为活动指定设计器</span><span class="sxs-lookup"><span data-stu-id="4c5a8-111">Assigning a designer an activity</span></span>  
 <span data-ttu-id="4c5a8-112">为指定活动要使用的设计器，使用了 Designer 属性。</span><span class="sxs-lookup"><span data-stu-id="4c5a8-112">To specify which designer an activity uses, the Designer attribute is used.</span></span>  
  
```  
[Designer(typeof(MyClassDesigner))]  
public sealed class MyClass : CodeActivity  
{  
```  
  
## <a name="creating-a-service"></a><span data-ttu-id="4c5a8-113">创建服务</span><span class="sxs-lookup"><span data-stu-id="4c5a8-113">Creating a service</span></span>  
 <span data-ttu-id="4c5a8-114">若要创建一个服务，充当设计器与主机之间的信息管道，必须创建一个接口和一个实现。</span><span class="sxs-lookup"><span data-stu-id="4c5a8-114">To create a service that serves as a conduit of information between the designer and the host, an interface and an implementation must be created.</span></span> <span data-ttu-id="4c5a8-115">接口由 <xref:System.Activities.Presentation.ServiceManager.Publish%2A> 方法用来定义服务的成员，而实现则包含服务的逻辑。</span><span class="sxs-lookup"><span data-stu-id="4c5a8-115">The interface is used by the <xref:System.Activities.Presentation.ServiceManager.Publish%2A> method to define the members of the service, and the implementation contains the logic for the service.</span></span> <span data-ttu-id="4c5a8-116">在下面的代码示例中，创建了一个服务接口和一个实现。</span><span class="sxs-lookup"><span data-stu-id="4c5a8-116">In the following code example, a service interface and implementation are created.</span></span>  
  
```  
public interface IMyService  
    {  
        IEnumerable<string> GetValues(string DisplayName);  
    }  
  
    public class MyServiceImpl : IMyService  
    {  
        public IEnumerable<string> GetValues(string DisplayName)  
        {  
            return new string[]  {   
                DisplayName + " One",   
                DisplayName + " Two",  
                "Three " + DisplayName  
            } ;  
        }  
    }  
```  
  
## <a name="publishing-a-service"></a><span data-ttu-id="4c5a8-117">发布服务</span><span class="sxs-lookup"><span data-stu-id="4c5a8-117">Publishing a service</span></span>  
 <span data-ttu-id="4c5a8-118">为使设计器能够使用服务，必须先由主机使用 <xref:System.Activities.Presentation.ServiceManager.Publish%2A> 方法将服务发布。</span><span class="sxs-lookup"><span data-stu-id="4c5a8-118">For a designer to consume a service, it must first be published by the host using the <xref:System.Activities.Presentation.ServiceManager.Publish%2A> method.</span></span>  
  
```  
this.Context.Services.Publish<IMyService>(new MyServiceImpl);  
```  
  
## <a name="subscribing-to-a-service"></a><span data-ttu-id="4c5a8-119">订阅服务</span><span class="sxs-lookup"><span data-stu-id="4c5a8-119">Subscribing to a service</span></span>  
 <span data-ttu-id="4c5a8-120">设计器在 <xref:System.Activities.Presentation.ServiceManager.Subscribe%2A> 方法中使用 <xref:System.Activities.Presentation.WorkflowViewElement.OnModelItemChanged%2A> 方法来获得对服务的访问。</span><span class="sxs-lookup"><span data-stu-id="4c5a8-120">The designer obtains access to the service using the <xref:System.Activities.Presentation.ServiceManager.Subscribe%2A> method in the <xref:System.Activities.Presentation.WorkflowViewElement.OnModelItemChanged%2A> method.</span></span> <span data-ttu-id="4c5a8-121">下列代码段演示了订阅服务的方法。</span><span class="sxs-lookup"><span data-stu-id="4c5a8-121">The following code snippet demonstrates how to subscribe to a service.</span></span>  
  
```  
protected override void OnModelItemChanged(object newItem)  
{  
    if (!subscribed)  
    {  
        this.Context.Services.Subscribe<IMyService>(  
            servInstance =>  
            {  
                listBox1.ItemsSource = servInstance.GetValues(this.ModelItem.Properties["DisplayName"].ComputedValue.ToString());  
            }  
            );  
        subscribed = true;   
    }  
}  
```  
  
## <a name="sharing-data-using-the-items-collection"></a><span data-ttu-id="4c5a8-122">使用项集合共享数据</span><span class="sxs-lookup"><span data-stu-id="4c5a8-122">Sharing data using the Items collection</span></span>  
 <span data-ttu-id="4c5a8-123">使用项集合与使用服务集合类似，但使用的是 <xref:System.Activities.Presentation.ContextItemManager.SetValue%2A>，而不是 Publish。</span><span class="sxs-lookup"><span data-stu-id="4c5a8-123">Using the Items collection is similar to using the Services collection, except that <xref:System.Activities.Presentation.ContextItemManager.SetValue%2A> is used instead of Publish.</span></span> <span data-ttu-id="4c5a8-124">此集合更适合在设计器与主机之间的共享简单的数据，不适合复杂的功能。</span><span class="sxs-lookup"><span data-stu-id="4c5a8-124">This collection is more appropriate for sharing simple data between the designers and the host, rather than complex functionality.</span></span>  
  
## <a name="editingcontext-host-items-and-services"></a><span data-ttu-id="4c5a8-125">EditingContext 主机项和服务</span><span class="sxs-lookup"><span data-stu-id="4c5a8-125">EditingContext host items and services</span></span>  
 <span data-ttu-id="4c5a8-126">.Net Framework 提供了大量通过编辑上下文访问的内置项和服务。</span><span class="sxs-lookup"><span data-stu-id="4c5a8-126">The .Net Framework provides a number of built-in items and services accessed through the editing context.</span></span>  
  
 <span data-ttu-id="4c5a8-127">项：</span><span class="sxs-lookup"><span data-stu-id="4c5a8-127">Items:</span></span>  
  
-   <span data-ttu-id="4c5a8-128"><xref:System.Activities.Presentation.Hosting.AssemblyContextControlItem>：管理将在控件（如表达式编辑器）的工作流内部使用的引用和本地程序集的列表。</span><span class="sxs-lookup"><span data-stu-id="4c5a8-128"><xref:System.Activities.Presentation.Hosting.AssemblyContextControlItem>: Manages the list of referenced local assemblies that will be used inside the workflow for controls (such as the expression editor).</span></span>  
  
-   <span data-ttu-id="4c5a8-129"><xref:System.Activities.Presentation.Hosting.ReadOnlyState>：指示设计器是否处于只读状态。</span><span class="sxs-lookup"><span data-stu-id="4c5a8-129"><xref:System.Activities.Presentation.Hosting.ReadOnlyState>: Indicates whether the designer is in a read-only state.</span></span>  
  
-   <span data-ttu-id="4c5a8-130"><xref:System.Activities.Presentation.View.Selection>：定义当前所选对象的集合。</span><span class="sxs-lookup"><span data-stu-id="4c5a8-130"><xref:System.Activities.Presentation.View.Selection>: Defines the collection of objects that are currently selected.</span></span>  
  
-   <span data-ttu-id="4c5a8-131"><xref:System.Activities.Presentation.Hosting.WorkflowCommandExtensionItem>：</span><span class="sxs-lookup"><span data-stu-id="4c5a8-131"><xref:System.Activities.Presentation.Hosting.WorkflowCommandExtensionItem>:</span></span>  
  
-   <span data-ttu-id="4c5a8-132"><xref:System.Activities.Presentation.WorkflowFileItem>：提供有关当前编辑会话所基于的文件的信息。</span><span class="sxs-lookup"><span data-stu-id="4c5a8-132"><xref:System.Activities.Presentation.WorkflowFileItem>: Provides information on the file that the current editing session is based on.</span></span>  
  
 <span data-ttu-id="4c5a8-133">服务：</span><span class="sxs-lookup"><span data-stu-id="4c5a8-133">Services:</span></span>  
  
-   <span data-ttu-id="4c5a8-134"><xref:System.Activities.Presentation.Model.AttachedPropertiesService>：允许使用 <xref:System.Activities.Presentation.Model.AttachedPropertiesService.AddProperty%2A> 将属性添加到当前实例中。</span><span class="sxs-lookup"><span data-stu-id="4c5a8-134"><xref:System.Activities.Presentation.Model.AttachedPropertiesService>: Allows properties to be added to the current instance, using <xref:System.Activities.Presentation.Model.AttachedPropertiesService.AddProperty%2A>.</span></span>  
  
-   <span data-ttu-id="4c5a8-135"><xref:System.Activities.Presentation.View.DesignerView>：允许访问设计器画布的属性。</span><span class="sxs-lookup"><span data-stu-id="4c5a8-135"><xref:System.Activities.Presentation.View.DesignerView>: Allows access to the properties of the designer canvas.</span></span>  
  
-   <span data-ttu-id="4c5a8-136"><xref:System.Activities.Presentation.IActivityToolboxService>：允许更新工具箱的内容。</span><span class="sxs-lookup"><span data-stu-id="4c5a8-136"><xref:System.Activities.Presentation.IActivityToolboxService>: Allows the contents of the toolbox to be updated.</span></span>  
  
-   <span data-ttu-id="4c5a8-137"><xref:System.Activities.Presentation.Hosting.ICommandService>：用于将设计器命令（如上下文菜单）与自定义的服务实现集成。</span><span class="sxs-lookup"><span data-stu-id="4c5a8-137"><xref:System.Activities.Presentation.Hosting.ICommandService>: Used to integrate designer commands (such as Context Menu) with custom-provided service implementations.</span></span>  
  
-   <span data-ttu-id="4c5a8-138"><xref:System.Activities.Presentation.Debug.IDesignerDebugView>：为设计器调试器提供功能。</span><span class="sxs-lookup"><span data-stu-id="4c5a8-138"><xref:System.Activities.Presentation.Debug.IDesignerDebugView>: Provides functionality for the designer debugger.</span></span>  
  
-   <span data-ttu-id="4c5a8-139"><xref:System.Activities.Presentation.View.IExpressionEditorService>：提供对“表达式编辑器”对话框的访问。</span><span class="sxs-lookup"><span data-stu-id="4c5a8-139"><xref:System.Activities.Presentation.View.IExpressionEditorService>: Provides access to the Expression Editor dialog.</span></span>  
  
-   <span data-ttu-id="4c5a8-140"><xref:System.Activities.Presentation.IIntegratedHelpService>：为设计器提供集成的帮助功能。</span><span class="sxs-lookup"><span data-stu-id="4c5a8-140"><xref:System.Activities.Presentation.IIntegratedHelpService>: Provides the designer with integrated help functionality.</span></span>  
  
-   <span data-ttu-id="4c5a8-141"><xref:System.Activities.Presentation.Validation.IValidationErrorService>：使用 <xref:System.Activities.Presentation.Validation.IValidationErrorService.ShowValidationErrors%2A> 提供对验证错误的访问。</span><span class="sxs-lookup"><span data-stu-id="4c5a8-141"><xref:System.Activities.Presentation.Validation.IValidationErrorService>: Provides access to validation errors using <xref:System.Activities.Presentation.Validation.IValidationErrorService.ShowValidationErrors%2A>.</span></span>  
  
-   <span data-ttu-id="4c5a8-142"><xref:System.Activities.Presentation.IWorkflowDesignerStorageService>：提供内部服务以存储和检索数据。</span><span class="sxs-lookup"><span data-stu-id="4c5a8-142"><xref:System.Activities.Presentation.IWorkflowDesignerStorageService>: Provides an internal service to store and retrieve data.</span></span> <span data-ttu-id="4c5a8-143">此服务由 .Net Framework 内部使用，不能在外部使用。</span><span class="sxs-lookup"><span data-stu-id="4c5a8-143">This service is used internally by the .Net Framework, and is not intended for external use.</span></span>  
  
-   <span data-ttu-id="4c5a8-144"><xref:System.Activities.Presentation.IXamlLoadErrorService>：使用 <xref:System.Activities.Presentation.IXamlLoadErrorService.ShowXamlLoadErrors%2A> 提供对 XAML 加载错误集合的访问。</span><span class="sxs-lookup"><span data-stu-id="4c5a8-144"><xref:System.Activities.Presentation.IXamlLoadErrorService>: Provides access to the XAML load error collection using <xref:System.Activities.Presentation.IXamlLoadErrorService.ShowXamlLoadErrors%2A>.</span></span>  
  
-   <span data-ttu-id="4c5a8-145"><xref:System.Activities.Presentation.Services.ModelService>：由设计器用来与正在编辑的工作流模型进行交互。</span><span class="sxs-lookup"><span data-stu-id="4c5a8-145"><xref:System.Activities.Presentation.Services.ModelService>: Used by the designer to interact with the model of the workflow being edited.</span></span>  
  
-   <span data-ttu-id="4c5a8-146"><xref:System.Activities.Presentation.Model.ModelTreeManager>：使用 <xref:System.Activities.Presentation.Model.ModelItem.Root%2A> 提供对模型项树根的访问。</span><span class="sxs-lookup"><span data-stu-id="4c5a8-146"><xref:System.Activities.Presentation.Model.ModelTreeManager>: Provides access to the root of the model item tree using <xref:System.Activities.Presentation.Model.ModelItem.Root%2A>.</span></span>  
  
-   <span data-ttu-id="4c5a8-147"><xref:System.Activities.Presentation.UndoEngine>：提供撤消和重做功能。</span><span class="sxs-lookup"><span data-stu-id="4c5a8-147"><xref:System.Activities.Presentation.UndoEngine>: Provides undo and redo functionality.</span></span>  
  
-   <span data-ttu-id="4c5a8-148"><xref:System.Activities.Presentation.Services.ViewService>：将可视元素映射到基础模型项。</span><span class="sxs-lookup"><span data-stu-id="4c5a8-148"><xref:System.Activities.Presentation.Services.ViewService>: Maps visual elements to underlying model items.</span></span>  
  
-   <span data-ttu-id="4c5a8-149"><xref:System.Activities.Presentation.View.ViewStateService>：存储模型项的视图状态。</span><span class="sxs-lookup"><span data-stu-id="4c5a8-149"><xref:System.Activities.Presentation.View.ViewStateService>: Stores view states for model items.</span></span>  
  
-   <span data-ttu-id="4c5a8-150"><xref:System.Activities.Presentation.View.VirtualizedContainerService>：用于自定义虚拟容器 UI 行为。</span><span class="sxs-lookup"><span data-stu-id="4c5a8-150"><xref:System.Activities.Presentation.View.VirtualizedContainerService>: Used to customize the virtual container UI behavior.</span></span>  
  
-   <span data-ttu-id="4c5a8-151"><xref:System.Activities.Presentation.Hosting.WindowHelperService>：用于注册和注销事件通知的委托。</span><span class="sxs-lookup"><span data-stu-id="4c5a8-151"><xref:System.Activities.Presentation.Hosting.WindowHelperService>: Used to register and unregister delegates for event notifications.</span></span> <span data-ttu-id="4c5a8-152">还允许设置一个窗口所有者。</span><span class="sxs-lookup"><span data-stu-id="4c5a8-152">Also allows a window owner to be set.</span></span>
