---
title: My.Forms 对象 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- My.Forms
- My.MyProject.Forms
helpviewer_keywords:
- My.Forms object
ms.assetid: f6bff4e6-6769-4294-956b-037aa6106d2a
ms.openlocfilehash: d15765b7673f321d4362ceea0adb73959a7e7726
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2018
ms.locfileid: "44185936"
---
# <a name="myforms-object"></a><span data-ttu-id="34e5b-102">My.Forms 对象</span><span class="sxs-lookup"><span data-stu-id="34e5b-102">My.Forms Object</span></span>
<span data-ttu-id="34e5b-103">提供用于访问当前项目中声明每个 Windows 窗体的实例的属性。</span><span class="sxs-lookup"><span data-stu-id="34e5b-103">Provides properties for accessing an instance of each Windows form declared in the current project.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="34e5b-104">备注</span><span class="sxs-lookup"><span data-stu-id="34e5b-104">Remarks</span></span>  
 <span data-ttu-id="34e5b-105">`My.Forms`对象提供当前项目中每个窗体的实例。</span><span class="sxs-lookup"><span data-stu-id="34e5b-105">The `My.Forms` object provides an instance of each form in the current project.</span></span> <span data-ttu-id="34e5b-106">该属性所访问的窗体的名称相同的属性的名称。</span><span class="sxs-lookup"><span data-stu-id="34e5b-106">The name of the property is the same as the name of the form that the property accesses.</span></span>   
  
 <span data-ttu-id="34e5b-107">您可以访问提供的窗体`My.Forms`对象使用的窗体，而无需限定名称。</span><span class="sxs-lookup"><span data-stu-id="34e5b-107">You can access the forms provided by the `My.Forms` object by using the name of the form, without qualification.</span></span> <span data-ttu-id="34e5b-108">由于属性名称是窗体的类型名称相同，这样即可访问窗体，如同它具有默认实例。</span><span class="sxs-lookup"><span data-stu-id="34e5b-108">Because the property name is the same as the form's type name, this allows you to access a form as if it had a default instance.</span></span> <span data-ttu-id="34e5b-109">例如，`My.Forms.Form1.Show` 与 `Form1.Show` 等效。</span><span class="sxs-lookup"><span data-stu-id="34e5b-109">For example, `My.Forms.Form1.Show` is equivalent to `Form1.Show`.</span></span>  
  
 <span data-ttu-id="34e5b-110">`My.Forms`对象公开仅与当前项目关联的窗体。</span><span class="sxs-lookup"><span data-stu-id="34e5b-110">The `My.Forms` object exposes only the forms associated with the current project.</span></span> <span data-ttu-id="34e5b-111">它不提供对窗体在被引用的 Dll 中声明的访问。</span><span class="sxs-lookup"><span data-stu-id="34e5b-111">It does not provide access to forms declared in referenced DLLs.</span></span> <span data-ttu-id="34e5b-112">若要访问 DLL 提供的窗体，必须使用窗体，作为写入的限定的名称*DllName*。*窗体名称*。</span><span class="sxs-lookup"><span data-stu-id="34e5b-112">To access a form that a DLL provides, you must use the qualified name of the form, written as *DllName*.*FormName*.</span></span>  
  
 <span data-ttu-id="34e5b-113">可以使用<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A>属性来获取应用程序的所有打开窗体的集合。</span><span class="sxs-lookup"><span data-stu-id="34e5b-113">You can use the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A> property to get a collection of all the application's open forms.</span></span>  
  
 <span data-ttu-id="34e5b-114">仅适用于 Windows 应用程序对象和其属性。</span><span class="sxs-lookup"><span data-stu-id="34e5b-114">The object and its properties are available only for Windows applications.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="34e5b-115">属性</span><span class="sxs-lookup"><span data-stu-id="34e5b-115">Properties</span></span>  
 <span data-ttu-id="34e5b-116">每个属性`My.Forms`对象提供对当前项目中的窗体的实例访问。</span><span class="sxs-lookup"><span data-stu-id="34e5b-116">Each property of the `My.Forms` object provides access to an instance of a form in the current project.</span></span> <span data-ttu-id="34e5b-117">属性的名称的窗体的属性访问，名称相同，属性类型是窗体的类型相同。</span><span class="sxs-lookup"><span data-stu-id="34e5b-117">The name of the property is the same as the name of the form that the property accesses, and the property type is the same as the form's type.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="34e5b-118">如果没有名称冲突，是要访问窗体的属性名称*RootNamespace*_*Namespace*\_*窗体名称*。</span><span class="sxs-lookup"><span data-stu-id="34e5b-118">If there is a name collision, the property name to access a form is *RootNamespace*_*Namespace*\_*FormName*.</span></span> <span data-ttu-id="34e5b-119">例如，考虑名为两个窗体`Form1.`这些窗体的其中一个是否在根命名空间`WindowsApplication1`和命名空间`Namespace1`，将访问通过该窗体`My.Forms.WindowsApplication1_Namespace1_Form1`。</span><span class="sxs-lookup"><span data-stu-id="34e5b-119">For example, consider two forms named `Form1.`If one of these forms is in the root namespace `WindowsApplication1` and in the namespace `Namespace1`, you would access that form through `My.Forms.WindowsApplication1_Namespace1_Form1`.</span></span>  
  
 <span data-ttu-id="34e5b-120">`My.Forms`对象提供对在启动时创建的应用程序的主窗体的实例访问。</span><span class="sxs-lookup"><span data-stu-id="34e5b-120">The `My.Forms` object provides access to the instance of the application's main form that was created on startup.</span></span> <span data-ttu-id="34e5b-121">对于所有其他窗体，`My.Forms`对象时它将访问并将其存储创建窗体的新实例。</span><span class="sxs-lookup"><span data-stu-id="34e5b-121">For all other forms, the `My.Forms` object creates a new instance of the form when it is accessed and stores it.</span></span> <span data-ttu-id="34e5b-122">后续尝试访问该属性返回该窗体的实例。</span><span class="sxs-lookup"><span data-stu-id="34e5b-122">Subsequent attempts to access that property return that instance of the form.</span></span>  
  
 <span data-ttu-id="34e5b-123">您可以通过将分配释放窗体的`Nothing`到该窗体的属性。</span><span class="sxs-lookup"><span data-stu-id="34e5b-123">You can dispose of a form by assigning `Nothing` to the property for that form.</span></span> <span data-ttu-id="34e5b-124">属性 setter 调用<xref:System.Windows.Forms.Form.Close%2A>方法的窗体，然后分配`Nothing`与存储的值。</span><span class="sxs-lookup"><span data-stu-id="34e5b-124">The property setter calls the <xref:System.Windows.Forms.Form.Close%2A> method of the form, and then assigns `Nothing` to the stored value.</span></span> <span data-ttu-id="34e5b-125">如果不是将任何值赋`Nothing`与属性 setter 引发<xref:System.ArgumentException>异常。</span><span class="sxs-lookup"><span data-stu-id="34e5b-125">If you assign any value other than `Nothing` to the property, the setter throws an <xref:System.ArgumentException> exception.</span></span>  
  
 <span data-ttu-id="34e5b-126">你可以测试的属性是否`My.Forms`对象将窗体的实例存储通过使用`Is`或`IsNot`运算符。</span><span class="sxs-lookup"><span data-stu-id="34e5b-126">You can test whether a property of the `My.Forms` object stores an instance of the form by using the `Is` or `IsNot` operator.</span></span> <span data-ttu-id="34e5b-127">可以使用这些运算符来检查属性的值是否为`Nothing`。</span><span class="sxs-lookup"><span data-stu-id="34e5b-127">You can use those operators to check if the value of the property is `Nothing`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="34e5b-128">通常情况下，`Is`或`IsNot`操作员必须读取的属性进行比较的值。</span><span class="sxs-lookup"><span data-stu-id="34e5b-128">Typically, the `Is` or `IsNot` operator has to read the value of the property to perform the comparison.</span></span> <span data-ttu-id="34e5b-129">但是，如果该属性将当前存储`Nothing`，该属性创建窗体的新实例，然后返回该实例。</span><span class="sxs-lookup"><span data-stu-id="34e5b-129">However, if the property currently stores `Nothing`, the property creates a new instance of the form and then returns that instance.</span></span> <span data-ttu-id="34e5b-130">但是，Visual Basic 编译器处理的属性`My.Forms`对象以不同的方式，并允许`Is`或`IsNot`运算符来检查属性的状态，而无需更改其值。</span><span class="sxs-lookup"><span data-stu-id="34e5b-130">However, the Visual Basic compiler treats the properties of the `My.Forms` object differently and allows the `Is` or `IsNot` operator to check the status of the property without altering its value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="34e5b-131">示例</span><span class="sxs-lookup"><span data-stu-id="34e5b-131">Example</span></span>  
 <span data-ttu-id="34e5b-132">此示例将更改的默认标题`SidebarMenu`窗体。</span><span class="sxs-lookup"><span data-stu-id="34e5b-132">This example changes the title of the default `SidebarMenu` form.</span></span>  
  
 [!code-vb[VbVbalrMyForms#2](../../../visual-basic/language-reference/objects/codesnippet/VisualBasic/my-forms-object_1.vb)]  
  
 <span data-ttu-id="34e5b-133">对于此示例正常工作，你的项目必须具有名为窗体`SidebarMenu`。</span><span class="sxs-lookup"><span data-stu-id="34e5b-133">For this example to work, your project must have a form named `SidebarMenu`.</span></span>  
  
 <span data-ttu-id="34e5b-134">此代码将仅适用于 Windows 应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="34e5b-134">This code will work only in a Windows Application project.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34e5b-135">要求</span><span class="sxs-lookup"><span data-stu-id="34e5b-135">Requirements</span></span>  
  
### <a name="availability-by-project-type"></a><span data-ttu-id="34e5b-136">项目类型的可用性</span><span class="sxs-lookup"><span data-stu-id="34e5b-136">Availability by Project Type</span></span>  
  
|<span data-ttu-id="34e5b-137">项目类型</span><span class="sxs-lookup"><span data-stu-id="34e5b-137">Project type</span></span>|<span data-ttu-id="34e5b-138">可用</span><span class="sxs-lookup"><span data-stu-id="34e5b-138">Available</span></span>|  
|---|---|  
|<span data-ttu-id="34e5b-139">Windows 应用程序</span><span class="sxs-lookup"><span data-stu-id="34e5b-139">Windows Application</span></span>|<span data-ttu-id="34e5b-140">**是**</span><span class="sxs-lookup"><span data-stu-id="34e5b-140">**Yes**</span></span>|  
|<span data-ttu-id="34e5b-141">类库</span><span class="sxs-lookup"><span data-stu-id="34e5b-141">Class Library</span></span>|<span data-ttu-id="34e5b-142">否</span><span class="sxs-lookup"><span data-stu-id="34e5b-142">No</span></span>|  
|<span data-ttu-id="34e5b-143">控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="34e5b-143">Console Application</span></span>|<span data-ttu-id="34e5b-144">否</span><span class="sxs-lookup"><span data-stu-id="34e5b-144">No</span></span>|  
|<span data-ttu-id="34e5b-145">Windows 控件库</span><span class="sxs-lookup"><span data-stu-id="34e5b-145">Windows Control Library</span></span>|<span data-ttu-id="34e5b-146">否</span><span class="sxs-lookup"><span data-stu-id="34e5b-146">No</span></span>|  
|<span data-ttu-id="34e5b-147">Web 控件库</span><span class="sxs-lookup"><span data-stu-id="34e5b-147">Web Control Library</span></span>|<span data-ttu-id="34e5b-148">否</span><span class="sxs-lookup"><span data-stu-id="34e5b-148">No</span></span>|  
|<span data-ttu-id="34e5b-149">Windows 服务</span><span class="sxs-lookup"><span data-stu-id="34e5b-149">Windows Service</span></span>|<span data-ttu-id="34e5b-150">否</span><span class="sxs-lookup"><span data-stu-id="34e5b-150">No</span></span>|  
|<span data-ttu-id="34e5b-151">网站</span><span class="sxs-lookup"><span data-stu-id="34e5b-151">Web Site</span></span>|<span data-ttu-id="34e5b-152">否</span><span class="sxs-lookup"><span data-stu-id="34e5b-152">No</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="34e5b-153">请参阅</span><span class="sxs-lookup"><span data-stu-id="34e5b-153">See Also</span></span>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A>  
 <xref:System.Windows.Forms.Form>  
 <xref:System.Windows.Forms.Form.Close%2A>  
 [<span data-ttu-id="34e5b-154">对象</span><span class="sxs-lookup"><span data-stu-id="34e5b-154">Objects</span></span>](../../../visual-basic/language-reference/objects/index.md)  
 [<span data-ttu-id="34e5b-155">Is 运算符</span><span class="sxs-lookup"><span data-stu-id="34e5b-155">Is Operator</span></span>](../../../visual-basic/language-reference/operators/is-operator.md)  
 [<span data-ttu-id="34e5b-156">IsNot 运算符</span><span class="sxs-lookup"><span data-stu-id="34e5b-156">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)  
 [<span data-ttu-id="34e5b-157">访问应用程序窗体</span><span class="sxs-lookup"><span data-stu-id="34e5b-157">Accessing Application Forms</span></span>](../../../visual-basic/developing-apps/programming/accessing-application-forms.md)
