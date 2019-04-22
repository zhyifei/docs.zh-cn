---
title: My.Resources 对象 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- My.Resources
- My.Resources.MyResources.ResourceManager
- My.Resources.MyResources.Culture
helpviewer_keywords:
- My.Resources object
ms.assetid: 34c3f2dc-7b87-432c-9d5f-17ea666bb266
ms.openlocfilehash: ee4d30b82ceada5c4f3fc4ad95dc8eeedd9355b0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "58821733"
---
# <a name="myresources-object"></a><span data-ttu-id="7ed1b-102">My.Resources 对象</span><span class="sxs-lookup"><span data-stu-id="7ed1b-102">My.Resources Object</span></span>
<span data-ttu-id="7ed1b-103">提供用于访问应用程序的资源的属性和类。</span><span class="sxs-lookup"><span data-stu-id="7ed1b-103">Provides properties and classes for accessing the application's resources.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7ed1b-104">备注</span><span class="sxs-lookup"><span data-stu-id="7ed1b-104">Remarks</span></span>  
 <span data-ttu-id="7ed1b-105">`My.Resources`对象提供了对应用程序的资源的访问，并允许动态应用程序的检索资源。</span><span class="sxs-lookup"><span data-stu-id="7ed1b-105">The `My.Resources` object provides access to the application's resources and lets you dynamically retrieve resources for your application.</span></span> <span data-ttu-id="7ed1b-106">有关详细信息，请参阅[管理应用程序资源 (.NET)](/visualstudio/ide/managing-application-resources-dotnet)。</span><span class="sxs-lookup"><span data-stu-id="7ed1b-106">For more information, see [Managing Application Resources (.NET)](/visualstudio/ide/managing-application-resources-dotnet).</span></span>  
  
 <span data-ttu-id="7ed1b-107">`My.Resources`对象公开只有全局资源。</span><span class="sxs-lookup"><span data-stu-id="7ed1b-107">The `My.Resources` object exposes only global resources.</span></span> <span data-ttu-id="7ed1b-108">它不提供对与窗体相关联的资源文件的访问。</span><span class="sxs-lookup"><span data-stu-id="7ed1b-108">It does not provide access to resource files associated with forms.</span></span> <span data-ttu-id="7ed1b-109">必须从窗体来访问窗体资源。</span><span class="sxs-lookup"><span data-stu-id="7ed1b-109">You must access the form resources from the form.</span></span>  
  
 <span data-ttu-id="7ed1b-110">您可以访问应用程序的特定于区域性的资源文件从`My.Resources`对象。</span><span class="sxs-lookup"><span data-stu-id="7ed1b-110">You can access the application's culture-specific resource files from the `My.Resources` object.</span></span> <span data-ttu-id="7ed1b-111">默认情况下`My.Resources`对象查找匹配的区域中的资源文件中的资源<xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.UICulture%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="7ed1b-111">By default, the `My.Resources` object looks up resources from the resource file that matches the culture in the <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.UICulture%2A> property.</span></span> <span data-ttu-id="7ed1b-112">但是，可以重写此行为，并指定特定区域性的资源使用。</span><span class="sxs-lookup"><span data-stu-id="7ed1b-112">However, you can override this behavior and specify a particular culture to use for the resources.</span></span> <span data-ttu-id="7ed1b-113">有关详细信息，请参阅[桌面应用中的资源](../../../framework/resources/index.md)。</span><span class="sxs-lookup"><span data-stu-id="7ed1b-113">For more information, see [Resources in Desktop Apps](../../../framework/resources/index.md).</span></span>  
  
## <a name="properties"></a><span data-ttu-id="7ed1b-114">属性</span><span class="sxs-lookup"><span data-stu-id="7ed1b-114">Properties</span></span>  
 <span data-ttu-id="7ed1b-115">属性`My.Resources`对象提供对应用程序的资源的只读访问。</span><span class="sxs-lookup"><span data-stu-id="7ed1b-115">The properties of the `My.Resources` object provide read-only access to your application's resources.</span></span> <span data-ttu-id="7ed1b-116">若要添加或删除资源，请使用**项目设计器**。</span><span class="sxs-lookup"><span data-stu-id="7ed1b-116">To add or remove resources, use the **Project Designer**.</span></span> <span data-ttu-id="7ed1b-117">您可以访问资源通过添加**项目设计器**通过使用`My.Resources.` *resourceName*。</span><span class="sxs-lookup"><span data-stu-id="7ed1b-117">You can access resources added through the **Project Designer** by using `My.Resources.`*resourceName*.</span></span>  
  
 <span data-ttu-id="7ed1b-118">此外可以添加或删除选择的项目中的资源文件**解决方案资源管理器**，然后单击**添加新项**或**添加现有项**从**项目**菜单。</span><span class="sxs-lookup"><span data-stu-id="7ed1b-118">You can also add or remove resource files by selecting your project in **Solution Explorer** and clicking **Add New Item** or **Add Existing Item** from the **Project** menu.</span></span> <span data-ttu-id="7ed1b-119">您可以访问资源使用，以这种方式添加了`My.Resources.` *resourceFileName*`.`*resourceName*。</span><span class="sxs-lookup"><span data-stu-id="7ed1b-119">You can access resources added in this manner by using `My.Resources.`*resourceFileName*`.`*resourceName*.</span></span>  
  
 <span data-ttu-id="7ed1b-120">每个资源都有名称、 类别和值，并且这些资源设置确定要访问的资源的属性中的显示方式`My.Resources`对象。</span><span class="sxs-lookup"><span data-stu-id="7ed1b-120">Each resource has a name, category, and value, and these resource settings determine how the property to access the resource appears in the `My.Resources` object.</span></span> <span data-ttu-id="7ed1b-121">在中添加的资源**项目设计器**:</span><span class="sxs-lookup"><span data-stu-id="7ed1b-121">For resources added in the **Project Designer**:</span></span>  
  
-   <span data-ttu-id="7ed1b-122">名称确定属性的名称</span><span class="sxs-lookup"><span data-stu-id="7ed1b-122">The name determines the name of the property,</span></span>  
  
-   <span data-ttu-id="7ed1b-123">资源数据是属性的值</span><span class="sxs-lookup"><span data-stu-id="7ed1b-123">The resource data is the value of the property,</span></span>  
  
-   <span data-ttu-id="7ed1b-124">类别设置确定属性的类型：</span><span class="sxs-lookup"><span data-stu-id="7ed1b-124">The category determines the type of the property:</span></span>  
  
|<span data-ttu-id="7ed1b-125">类别</span><span class="sxs-lookup"><span data-stu-id="7ed1b-125">Category</span></span>|<span data-ttu-id="7ed1b-126">属性数据类型</span><span class="sxs-lookup"><span data-stu-id="7ed1b-126">Property data type</span></span>|  
|---|---|  
|<span data-ttu-id="7ed1b-127">**字符串**</span><span class="sxs-lookup"><span data-stu-id="7ed1b-127">**Strings**</span></span>|[<span data-ttu-id="7ed1b-128">String</span><span class="sxs-lookup"><span data-stu-id="7ed1b-128">String</span></span>](../../../visual-basic/language-reference/data-types/string-data-type.md)|  
|<span data-ttu-id="7ed1b-129">**图像**</span><span class="sxs-lookup"><span data-stu-id="7ed1b-129">**Images**</span></span>|<xref:System.Drawing.Bitmap>|  
|<span data-ttu-id="7ed1b-130">**图标**</span><span class="sxs-lookup"><span data-stu-id="7ed1b-130">**Icons**</span></span>|<xref:System.Drawing.Icon>|  
|<span data-ttu-id="7ed1b-131">**音频**</span><span class="sxs-lookup"><span data-stu-id="7ed1b-131">**Audio**</span></span>|<xref:System.IO.UnmanagedMemoryStream><br /><br /> <span data-ttu-id="7ed1b-132"><xref:System.IO.UnmanagedMemoryStream>类派生自<xref:System.IO.Stream>类，因此它可以用于采用流，例如方法<xref:Microsoft.VisualBasic.Devices.Audio.Play%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="7ed1b-132">The <xref:System.IO.UnmanagedMemoryStream> class derives from the <xref:System.IO.Stream> class, so it can be used with methods that take streams, such as the <xref:Microsoft.VisualBasic.Devices.Audio.Play%2A> method.</span></span>|  
|<span data-ttu-id="7ed1b-133">**文件**</span><span class="sxs-lookup"><span data-stu-id="7ed1b-133">**Files**</span></span>|<span data-ttu-id="7ed1b-134">-   [字符串](../../../visual-basic/language-reference/data-types/string-data-type.md)的文本文件。</span><span class="sxs-lookup"><span data-stu-id="7ed1b-134">-   [String](../../../visual-basic/language-reference/data-types/string-data-type.md) for text files.</span></span><br /><span data-ttu-id="7ed1b-135">-   <xref:System.Drawing.Bitmap> 为图像文件。</span><span class="sxs-lookup"><span data-stu-id="7ed1b-135">-   <xref:System.Drawing.Bitmap> for image files.</span></span><br /><span data-ttu-id="7ed1b-136">-   <xref:System.Drawing.Icon> 图标文件。</span><span class="sxs-lookup"><span data-stu-id="7ed1b-136">-   <xref:System.Drawing.Icon> for icon files.</span></span><br /><span data-ttu-id="7ed1b-137">-   <xref:System.IO.UnmanagedMemoryStream> 声音文件。</span><span class="sxs-lookup"><span data-stu-id="7ed1b-137">-   <xref:System.IO.UnmanagedMemoryStream> for sound files.</span></span>|  
|<span data-ttu-id="7ed1b-138">**其他**</span><span class="sxs-lookup"><span data-stu-id="7ed1b-138">**Other**</span></span>|<span data-ttu-id="7ed1b-139">通过在设计器中的信息确定**类型**列。</span><span class="sxs-lookup"><span data-stu-id="7ed1b-139">Determined by the information in the designer's **Type** column.</span></span>|  
  
## <a name="classes"></a><span data-ttu-id="7ed1b-140">类</span><span class="sxs-lookup"><span data-stu-id="7ed1b-140">Classes</span></span>  
 <span data-ttu-id="7ed1b-141">`My.Resources`对象将作为具有共享属性的类公开的每个资源文件。</span><span class="sxs-lookup"><span data-stu-id="7ed1b-141">The `My.Resources` object exposes each resource file as a class with shared properties.</span></span> <span data-ttu-id="7ed1b-142">类名是资源文件的名称相同。</span><span class="sxs-lookup"><span data-stu-id="7ed1b-142">The class name is the same as the name of the resource file.</span></span> <span data-ttu-id="7ed1b-143">如前一部分中所述，在资源文件中的资源被称为类中的属性。</span><span class="sxs-lookup"><span data-stu-id="7ed1b-143">As described in the previous section, the resources in a resource file are exposed as properties in the class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7ed1b-144">示例</span><span class="sxs-lookup"><span data-stu-id="7ed1b-144">Example</span></span>  
 <span data-ttu-id="7ed1b-145">此示例将窗体的标题设置为命名的字符串资源`Form1Title`在应用程序资源文件中。</span><span class="sxs-lookup"><span data-stu-id="7ed1b-145">This example sets the title of a form to the string resource named `Form1Title` in the application resource file.</span></span> <span data-ttu-id="7ed1b-146">若要运行示例，应用程序必须具有一个名为字符串`Form1Title`其资源文件中。</span><span class="sxs-lookup"><span data-stu-id="7ed1b-146">For the example to work, the application must have a string named `Form1Title` in its resource file.</span></span>  
  
 [!code-vb[VbVbalrMyResources#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="7ed1b-147">示例</span><span class="sxs-lookup"><span data-stu-id="7ed1b-147">Example</span></span>  
 <span data-ttu-id="7ed1b-148">此示例设置窗体的图标名为的图标为`Form1Icon`存储在应用程序的资源文件。</span><span class="sxs-lookup"><span data-stu-id="7ed1b-148">This example sets the icon of the form to the icon named `Form1Icon` that is stored in the application's resource file.</span></span> <span data-ttu-id="7ed1b-149">若要运行示例，应用程序必须具有名为一个图标`Form1Icon`其资源文件中。</span><span class="sxs-lookup"><span data-stu-id="7ed1b-149">For the example to work, the application must have an icon named `Form1Icon` in its resource file.</span></span>  
  
 [!code-vb[VbVbalrMyResources#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#2)]  
  
## <a name="example"></a><span data-ttu-id="7ed1b-150">示例</span><span class="sxs-lookup"><span data-stu-id="7ed1b-150">Example</span></span>  
 <span data-ttu-id="7ed1b-151">此示例将一个窗体的背景图像设置为命名的图像资源`Form1Background`，这是应用程序资源文件中。</span><span class="sxs-lookup"><span data-stu-id="7ed1b-151">This example sets the background image of a form to the image resource named `Form1Background`, which is in the application resource file.</span></span> <span data-ttu-id="7ed1b-152">此示例正常工作，应用程序必须有一个名为映像资源`Form1Background`其资源文件中。</span><span class="sxs-lookup"><span data-stu-id="7ed1b-152">For this example to work, the application must have an image resource named `Form1Background` in its resource file.</span></span>  
  
 [!code-vb[VbVbalrMyResources#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="7ed1b-153">示例</span><span class="sxs-lookup"><span data-stu-id="7ed1b-153">Example</span></span>  
 <span data-ttu-id="7ed1b-154">此示例中播放的声音，存储为一个名为的音频资源`Form1Greeting`在应用程序的资源文件中。</span><span class="sxs-lookup"><span data-stu-id="7ed1b-154">This example plays the sound that is stored as an audio resource named `Form1Greeting` in the application's resource file.</span></span> <span data-ttu-id="7ed1b-155">若要运行示例，该应用程序必须具有一个名为的音频资源`Form1Greeting`其资源文件中。</span><span class="sxs-lookup"><span data-stu-id="7ed1b-155">For the example to work, the application must have an audio resource named `Form1Greeting` in its resource file.</span></span> <span data-ttu-id="7ed1b-156">`My.Computer.Audio.Play`方法是仅适用于 Windows 窗体应用程序。</span><span class="sxs-lookup"><span data-stu-id="7ed1b-156">The `My.Computer.Audio.Play` method is available only for Windows Forms applications.</span></span>  
  
 [!code-vb[VbVbalrMyResources#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#4)]  
  
## <a name="example"></a><span data-ttu-id="7ed1b-157">示例</span><span class="sxs-lookup"><span data-stu-id="7ed1b-157">Example</span></span>  
 <span data-ttu-id="7ed1b-158">此示例检索字符串资源的应用程序的法语区域性版本。</span><span class="sxs-lookup"><span data-stu-id="7ed1b-158">This example retrieves the French-culture version of a  string resource of the application.</span></span> <span data-ttu-id="7ed1b-159">资源名为`Message`。</span><span class="sxs-lookup"><span data-stu-id="7ed1b-159">The resource is named `Message`.</span></span> <span data-ttu-id="7ed1b-160">若要更改区域性的`My.Resources`对象使用，该示例使用<xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.ChangeUICulture%2A>。</span><span class="sxs-lookup"><span data-stu-id="7ed1b-160">To change the culture that the `My.Resources` object uses, the example uses <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.ChangeUICulture%2A>.</span></span>  
  
 <span data-ttu-id="7ed1b-161">此示例正常工作，程序必须具有一个名为字符串`Message`在其资源文件和应用程序应具有的资源文件，Resources.fr-FR.resx 法语区域性版本。</span><span class="sxs-lookup"><span data-stu-id="7ed1b-161">For this example to work, the application must have a string named `Message` in its resource file, and the application should have the French-culture version of that resource file, Resources.fr-FR.resx.</span></span> <span data-ttu-id="7ed1b-162">如果应用程序不具有的资源文件中，法语区域性版本`My.Resource`对象将从默认区域性资源文件中检索资源。</span><span class="sxs-lookup"><span data-stu-id="7ed1b-162">If the application does not have the French-culture version of the resource file, the `My.Resource` object retrieves the resource from the default-culture resource file.</span></span>  
  
 [!code-vb[VbVbalrMyResources#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#10)]  
  
## <a name="see-also"></a><span data-ttu-id="7ed1b-163">请参阅</span><span class="sxs-lookup"><span data-stu-id="7ed1b-163">See also</span></span>

- [<span data-ttu-id="7ed1b-164">管理应用程序资源 (.NET)</span><span class="sxs-lookup"><span data-stu-id="7ed1b-164">Managing Application Resources (.NET)</span></span>](/visualstudio/ide/managing-application-resources-dotnet)
- [<span data-ttu-id="7ed1b-165">桌面应用中的资源</span><span class="sxs-lookup"><span data-stu-id="7ed1b-165">Resources in Desktop Apps</span></span>](../../../framework/resources/index.md)
