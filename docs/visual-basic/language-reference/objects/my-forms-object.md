---
title: "My.Forms 对象"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- My.Forms
- My.MyProject.Forms
helpviewer_keywords: My.Forms object
ms.assetid: f6bff4e6-6769-4294-956b-037aa6106d2a
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a5aa7af1f07a29660335d968c1ecc17be5f8beec
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="myforms-object"></a><span data-ttu-id="b5a8a-102">My.Forms 对象</span><span class="sxs-lookup"><span data-stu-id="b5a8a-102">My.Forms Object</span></span>
<span data-ttu-id="b5a8a-103">提供用于访问在当前项目中声明每个 Windows 窗体的实例的属性。</span><span class="sxs-lookup"><span data-stu-id="b5a8a-103">Provides properties for accessing an instance of each Windows form declared in the current project.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b5a8a-104">备注</span><span class="sxs-lookup"><span data-stu-id="b5a8a-104">Remarks</span></span>  
 <span data-ttu-id="b5a8a-105">`My.Forms`对象提供当前项目中的每个窗体的实例。</span><span class="sxs-lookup"><span data-stu-id="b5a8a-105">The `My.Forms` object provides an instance of each form in the current project.</span></span> <span data-ttu-id="b5a8a-106">属性访问的表单的名称相同的属性名称。</span><span class="sxs-lookup"><span data-stu-id="b5a8a-106">The name of the property is the same as the name of the form that the property accesses.</span></span> <span data-ttu-id="b5a8a-107">有关向项目添加窗体的信息，请参阅[如何： 向项目添加 Windows 窗体](http://msdn.microsoft.com/en-us/3d7bb25f-fd90-47cf-9378-fa0d764686c1)。</span><span class="sxs-lookup"><span data-stu-id="b5a8a-107">For information about adding forms to a project, see [How to: Add Windows Forms to a Project](http://msdn.microsoft.com/en-us/3d7bb25f-fd90-47cf-9378-fa0d764686c1).</span></span>  
  
 <span data-ttu-id="b5a8a-108">你可以访问提供的表单`My.Forms`对象使用窗体上，而无需限定的名称。</span><span class="sxs-lookup"><span data-stu-id="b5a8a-108">You can access the forms provided by the `My.Forms` object by using the name of the form, without qualification.</span></span> <span data-ttu-id="b5a8a-109">属性名称为与窗体的类型名称相同，因为这允许你访问窗体，就像它在默认实例。</span><span class="sxs-lookup"><span data-stu-id="b5a8a-109">Because the property name is the same as the form's type name, this allows you to access a form as if it had a default instance.</span></span> <span data-ttu-id="b5a8a-110">例如，`My.Forms.Form1.Show` 与 `Form1.Show` 等效。</span><span class="sxs-lookup"><span data-stu-id="b5a8a-110">For example, `My.Forms.Form1.Show` is equivalent to `Form1.Show`.</span></span>  
  
 <span data-ttu-id="b5a8a-111">`My.Forms`对象公开仅与当前项目关联的窗体。</span><span class="sxs-lookup"><span data-stu-id="b5a8a-111">The `My.Forms` object exposes only the forms associated with the current project.</span></span> <span data-ttu-id="b5a8a-112">它不提供对在被引用的 Dll 中声明的表单的访问。</span><span class="sxs-lookup"><span data-stu-id="b5a8a-112">It does not provide access to forms declared in referenced DLLs.</span></span> <span data-ttu-id="b5a8a-113">若要访问 DLL 提供窗体，你必须使用窗体中，编写为的限定的名称*dll 名称*。*窗体名称*。</span><span class="sxs-lookup"><span data-stu-id="b5a8a-113">To access a form that a DLL provides, you must use the qualified name of the form, written as *DllName*.*FormName*.</span></span>  
  
 <span data-ttu-id="b5a8a-114">你可以使用<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A>属性来获取应用程序的所有打开窗体的集合。</span><span class="sxs-lookup"><span data-stu-id="b5a8a-114">You can use the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A> property to get a collection of all the application's open forms.</span></span>  
  
 <span data-ttu-id="b5a8a-115">对象和其属性是仅适用于 Windows 应用程序。</span><span class="sxs-lookup"><span data-stu-id="b5a8a-115">The object and its properties are available only for Windows applications.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="b5a8a-116">属性</span><span class="sxs-lookup"><span data-stu-id="b5a8a-116">Properties</span></span>  
 <span data-ttu-id="b5a8a-117">每个属性`My.Forms`对象提供对在当前项目的窗体的实例访问。</span><span class="sxs-lookup"><span data-stu-id="b5a8a-117">Each property of the `My.Forms` object provides access to an instance of a form in the current project.</span></span> <span data-ttu-id="b5a8a-118">属性的名称属性访问时，表单的名称相同，因此该属性类型是窗体的类型相同。</span><span class="sxs-lookup"><span data-stu-id="b5a8a-118">The name of the property is the same as the name of the form that the property accesses, and the property type is the same as the form's type.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b5a8a-119">如果没有名称冲突，属性名称来访问窗体是*RootNamespace*_*Namespace*\_*窗体名称*。</span><span class="sxs-lookup"><span data-stu-id="b5a8a-119">If there is a name collision, the property name to access a form is *RootNamespace*_*Namespace*\_*FormName*.</span></span> <span data-ttu-id="b5a8a-120">例如，考虑名为的两种形式`Form1.`这些窗体的其中一个是否根命名空间中`WindowsApplication1`和命名空间中`Namespace1`，你将访问该窗体通过`My.Forms.WindowsApplication1_Namespace1_Form1`。</span><span class="sxs-lookup"><span data-stu-id="b5a8a-120">For example, consider two forms named `Form1.`If one of these forms is in the root namespace `WindowsApplication1` and in the namespace `Namespace1`, you would access that form through `My.Forms.WindowsApplication1_Namespace1_Form1`.</span></span>  
  
 <span data-ttu-id="b5a8a-121">`My.Forms`对象提供对在启动时创建的应用程序的主窗体实例访问。</span><span class="sxs-lookup"><span data-stu-id="b5a8a-121">The `My.Forms` object provides access to the instance of the application's main form that was created on startup.</span></span> <span data-ttu-id="b5a8a-122">对于所有其他窗体，`My.Forms`对象时它访问，并将其存储创建的窗体的新实例。</span><span class="sxs-lookup"><span data-stu-id="b5a8a-122">For all other forms, the `My.Forms` object creates a new instance of the form when it is accessed and stores it.</span></span> <span data-ttu-id="b5a8a-123">若要访问该属性的后续尝试返回该实例的窗体。</span><span class="sxs-lookup"><span data-stu-id="b5a8a-123">Subsequent attempts to access that property return that instance of the form.</span></span>  
  
 <span data-ttu-id="b5a8a-124">您可以通过分配释放窗体的`Nothing`到该窗体的属性。</span><span class="sxs-lookup"><span data-stu-id="b5a8a-124">You can dispose of a form by assigning `Nothing` to the property for that form.</span></span> <span data-ttu-id="b5a8a-125">属性 setter 调用<xref:System.Windows.Forms.Form.Close%2A>方法的窗体，然后将分配`Nothing`与存储的值。</span><span class="sxs-lookup"><span data-stu-id="b5a8a-125">The property setter calls the <xref:System.Windows.Forms.Form.Close%2A> method of the form, and then assigns `Nothing` to the stored value.</span></span> <span data-ttu-id="b5a8a-126">如果不将任何值赋`Nothing`setter 的属性，将引发<xref:System.ArgumentException>异常。</span><span class="sxs-lookup"><span data-stu-id="b5a8a-126">If you assign any value other than `Nothing` to the property, the setter throws an <xref:System.ArgumentException> exception.</span></span>  
  
 <span data-ttu-id="b5a8a-127">你可以测试的属性是否`My.Forms`对象通过使用存储的窗体实例`Is`或`IsNot`运算符。</span><span class="sxs-lookup"><span data-stu-id="b5a8a-127">You can test whether a property of the `My.Forms` object stores an instance of the form by using the `Is` or `IsNot` operator.</span></span> <span data-ttu-id="b5a8a-128">你可以使用这些运算符检查属性的值是否为`Nothing`。</span><span class="sxs-lookup"><span data-stu-id="b5a8a-128">You can use those operators to check if the value of the property is `Nothing`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b5a8a-129">通常情况下，`Is`或`IsNot`运算符具有要读取的属性进行比较的值。</span><span class="sxs-lookup"><span data-stu-id="b5a8a-129">Typically, the `Is` or `IsNot` operator has to read the value of the property to perform the comparison.</span></span> <span data-ttu-id="b5a8a-130">但是，如果该属性当前存储`Nothing`，属性创建窗体的新实例，然后返回该实例。</span><span class="sxs-lookup"><span data-stu-id="b5a8a-130">However, if the property currently stores `Nothing`, the property creates a new instance of the form and then returns that instance.</span></span> <span data-ttu-id="b5a8a-131">但是，Visual Basic 编译器处理的属性`My.Forms`对象以不同的方式，并允许`Is`或`IsNot`运算符检查而不改变其值的属性的状态。</span><span class="sxs-lookup"><span data-stu-id="b5a8a-131">However, the Visual Basic compiler treats the properties of the `My.Forms` object differently and allows the `Is` or `IsNot` operator to check the status of the property without altering its value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b5a8a-132">示例</span><span class="sxs-lookup"><span data-stu-id="b5a8a-132">Example</span></span>  
 <span data-ttu-id="b5a8a-133">此示例将更改的默认标题`SidebarMenu`窗体。</span><span class="sxs-lookup"><span data-stu-id="b5a8a-133">This example changes the title of the default `SidebarMenu` form.</span></span>  
  
 [!code-vb[VbVbalrMyForms#2](../../../visual-basic/language-reference/objects/codesnippet/VisualBasic/my-forms-object_1.vb)]  
  
 <span data-ttu-id="b5a8a-134">对于此示例正常工作，你的项目必须具有名为窗体`SidebarMenu`。</span><span class="sxs-lookup"><span data-stu-id="b5a8a-134">For this example to work, your project must have a form named `SidebarMenu`.</span></span> <span data-ttu-id="b5a8a-135">有关详细信息，请参阅[如何： 向项目添加 Windows 窗体](http://msdn.microsoft.com/en-us/3d7bb25f-fd90-47cf-9378-fa0d764686c1)。</span><span class="sxs-lookup"><span data-stu-id="b5a8a-135">For more information, see [How to: Add Windows Forms to a Project](http://msdn.microsoft.com/en-us/3d7bb25f-fd90-47cf-9378-fa0d764686c1).</span></span>  
  
 <span data-ttu-id="b5a8a-136">此代码将仅适用于 Windows 应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="b5a8a-136">This code will work only in a Windows Application project.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b5a8a-137">要求</span><span class="sxs-lookup"><span data-stu-id="b5a8a-137">Requirements</span></span>  
  
### <a name="availability-by-project-type"></a><span data-ttu-id="b5a8a-138">项目类型的可用性</span><span class="sxs-lookup"><span data-stu-id="b5a8a-138">Availability by Project Type</span></span>  
  
|<span data-ttu-id="b5a8a-139">项目类型</span><span class="sxs-lookup"><span data-stu-id="b5a8a-139">Project type</span></span>|<span data-ttu-id="b5a8a-140">可用</span><span class="sxs-lookup"><span data-stu-id="b5a8a-140">Available</span></span>|  
|---|---|  
|<span data-ttu-id="b5a8a-141">Windows 应用程序</span><span class="sxs-lookup"><span data-stu-id="b5a8a-141">Windows Application</span></span>|<span data-ttu-id="b5a8a-142">**是**</span><span class="sxs-lookup"><span data-stu-id="b5a8a-142">**Yes**</span></span>|  
|<span data-ttu-id="b5a8a-143">类库</span><span class="sxs-lookup"><span data-stu-id="b5a8a-143">Class Library</span></span>|<span data-ttu-id="b5a8a-144">No</span><span class="sxs-lookup"><span data-stu-id="b5a8a-144">No</span></span>|  
|<span data-ttu-id="b5a8a-145">控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="b5a8a-145">Console Application</span></span>|<span data-ttu-id="b5a8a-146">No</span><span class="sxs-lookup"><span data-stu-id="b5a8a-146">No</span></span>|  
|<span data-ttu-id="b5a8a-147">Windows 控件库</span><span class="sxs-lookup"><span data-stu-id="b5a8a-147">Windows Control Library</span></span>|<span data-ttu-id="b5a8a-148">No</span><span class="sxs-lookup"><span data-stu-id="b5a8a-148">No</span></span>|  
|<span data-ttu-id="b5a8a-149">Web 控件库</span><span class="sxs-lookup"><span data-stu-id="b5a8a-149">Web Control Library</span></span>|<span data-ttu-id="b5a8a-150">No</span><span class="sxs-lookup"><span data-stu-id="b5a8a-150">No</span></span>|  
|<span data-ttu-id="b5a8a-151">Windows 服务</span><span class="sxs-lookup"><span data-stu-id="b5a8a-151">Windows Service</span></span>|<span data-ttu-id="b5a8a-152">No</span><span class="sxs-lookup"><span data-stu-id="b5a8a-152">No</span></span>|  
|<span data-ttu-id="b5a8a-153">网站</span><span class="sxs-lookup"><span data-stu-id="b5a8a-153">Web Site</span></span>|<span data-ttu-id="b5a8a-154">No</span><span class="sxs-lookup"><span data-stu-id="b5a8a-154">No</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b5a8a-155">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b5a8a-155">See Also</span></span>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A>  
 <xref:System.Windows.Forms.Form>  
 <xref:System.Windows.Forms.Form.Close%2A>  
 [<span data-ttu-id="b5a8a-156">对象</span><span class="sxs-lookup"><span data-stu-id="b5a8a-156">Objects</span></span>](../../../visual-basic/language-reference/objects/index.md)  
 [<span data-ttu-id="b5a8a-157">如何： 向项目中添加 Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="b5a8a-157">How to: Add Windows Forms to a Project</span></span>](http://msdn.microsoft.com/en-us/3d7bb25f-fd90-47cf-9378-fa0d764686c1)  
 [<span data-ttu-id="b5a8a-158">Is 运算符</span><span class="sxs-lookup"><span data-stu-id="b5a8a-158">Is Operator</span></span>](../../../visual-basic/language-reference/operators/is-operator.md)  
 [<span data-ttu-id="b5a8a-159">IsNot 运算符</span><span class="sxs-lookup"><span data-stu-id="b5a8a-159">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)  
 [<span data-ttu-id="b5a8a-160">访问应用程序窗体</span><span class="sxs-lookup"><span data-stu-id="b5a8a-160">Accessing Application Forms</span></span>](../../../visual-basic/developing-apps/programming/accessing-application-forms.md)
