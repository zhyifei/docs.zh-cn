---
title: My.Resources 对象
ms.date: 07/20/2015
f1_keywords:
- My.Resources
- My.Resources.MyResources.ResourceManager
- My.Resources.MyResources.Culture
helpviewer_keywords:
- My.Resources object
ms.assetid: 34c3f2dc-7b87-432c-9d5f-17ea666bb266
ms.openlocfilehash: 7f5d81194123ad2151a494a3cb79aa1955e0fdad
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350331"
---
# <a name="myresources-object"></a><span data-ttu-id="a5971-102">My.Resources 对象</span><span class="sxs-lookup"><span data-stu-id="a5971-102">My.Resources Object</span></span>
<span data-ttu-id="a5971-103">提供用于访问应用程序资源的属性和类。</span><span class="sxs-lookup"><span data-stu-id="a5971-103">Provides properties and classes for accessing the application's resources.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a5971-104">备注</span><span class="sxs-lookup"><span data-stu-id="a5971-104">Remarks</span></span>  
 <span data-ttu-id="a5971-105">`My.Resources` 对象提供对应用程序资源的访问权限，并允许你为应用程序动态检索资源。</span><span class="sxs-lookup"><span data-stu-id="a5971-105">The `My.Resources` object provides access to the application's resources and lets you dynamically retrieve resources for your application.</span></span> <span data-ttu-id="a5971-106">有关详细信息，请参阅[管理应用程序资源（.net）](/visualstudio/ide/managing-application-resources-dotnet)。</span><span class="sxs-lookup"><span data-stu-id="a5971-106">For more information, see [Managing Application Resources (.NET)](/visualstudio/ide/managing-application-resources-dotnet).</span></span>  
  
 <span data-ttu-id="a5971-107">`My.Resources` 对象只公开全局资源。</span><span class="sxs-lookup"><span data-stu-id="a5971-107">The `My.Resources` object exposes only global resources.</span></span> <span data-ttu-id="a5971-108">它不提供对与表单关联的资源文件的访问权限。</span><span class="sxs-lookup"><span data-stu-id="a5971-108">It does not provide access to resource files associated with forms.</span></span> <span data-ttu-id="a5971-109">您必须从窗体访问窗体资源。</span><span class="sxs-lookup"><span data-stu-id="a5971-109">You must access the form resources from the form.</span></span>  
  
 <span data-ttu-id="a5971-110">可以从 `My.Resources` 对象访问应用程序的区域性特定资源文件。</span><span class="sxs-lookup"><span data-stu-id="a5971-110">You can access the application's culture-specific resource files from the `My.Resources` object.</span></span> <span data-ttu-id="a5971-111">默认情况下，`My.Resources` 对象从与 <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.UICulture%2A> 属性中的区域性匹配的资源文件中查找资源。</span><span class="sxs-lookup"><span data-stu-id="a5971-111">By default, the `My.Resources` object looks up resources from the resource file that matches the culture in the <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.UICulture%2A> property.</span></span> <span data-ttu-id="a5971-112">不过，您可以重写此行为，并指定要用于资源的特定区域性。</span><span class="sxs-lookup"><span data-stu-id="a5971-112">However, you can override this behavior and specify a particular culture to use for the resources.</span></span> <span data-ttu-id="a5971-113">有关详细信息，请参阅[桌面应用中的资源](../../../framework/resources/index.md)。</span><span class="sxs-lookup"><span data-stu-id="a5971-113">For more information, see [Resources in Desktop Apps](../../../framework/resources/index.md).</span></span>  
  
## <a name="properties"></a><span data-ttu-id="a5971-114">属性</span><span class="sxs-lookup"><span data-stu-id="a5971-114">Properties</span></span>  
 <span data-ttu-id="a5971-115">`My.Resources` 对象的属性提供对应用程序资源的只读访问。</span><span class="sxs-lookup"><span data-stu-id="a5971-115">The properties of the `My.Resources` object provide read-only access to your application's resources.</span></span> <span data-ttu-id="a5971-116">若要添加或删除资源，请使用 "**项目设计器**"。</span><span class="sxs-lookup"><span data-stu-id="a5971-116">To add or remove resources, use the **Project Designer**.</span></span> <span data-ttu-id="a5971-117">您可以使用 `My.Resources.`资源中心访问通过**项目设计器**添加*的资源*。</span><span class="sxs-lookup"><span data-stu-id="a5971-117">You can access resources added through the **Project Designer** by using `My.Resources.`*resourceName*.</span></span>  
  
 <span data-ttu-id="a5971-118">还可以通过在**解决方案资源管理器**中选择项目，然后在 "**项目**" 菜单中单击 "**添加新项**" 或 "**添加现有项**"，来添加或删除资源文件。</span><span class="sxs-lookup"><span data-stu-id="a5971-118">You can also add or remove resource files by selecting your project in **Solution Explorer** and clicking **Add New Item** or **Add Existing Item** from the **Project** menu.</span></span> <span data-ttu-id="a5971-119">你可以通过使用 `My.Resources.`*resourceFileName* *`.`资源*中心来访问以这种方式添加的资源。</span><span class="sxs-lookup"><span data-stu-id="a5971-119">You can access resources added in this manner by using `My.Resources.`*resourceFileName*`.`*resourceName*.</span></span>  
  
 <span data-ttu-id="a5971-120">每个资源都有一个名称、类别和值，这些资源设置决定了访问资源的属性在 `My.Resources` 对象中的显示方式。</span><span class="sxs-lookup"><span data-stu-id="a5971-120">Each resource has a name, category, and value, and these resource settings determine how the property to access the resource appears in the `My.Resources` object.</span></span> <span data-ttu-id="a5971-121">对于在**项目设计器**中添加的资源：</span><span class="sxs-lookup"><span data-stu-id="a5971-121">For resources added in the **Project Designer**:</span></span>  
  
- <span data-ttu-id="a5971-122">名称确定属性的名称。</span><span class="sxs-lookup"><span data-stu-id="a5971-122">The name determines the name of the property,</span></span>  
  
- <span data-ttu-id="a5971-123">资源数据是属性的值。</span><span class="sxs-lookup"><span data-stu-id="a5971-123">The resource data is the value of the property,</span></span>  
  
- <span data-ttu-id="a5971-124">类别确定属性的类型：</span><span class="sxs-lookup"><span data-stu-id="a5971-124">The category determines the type of the property:</span></span>  
  
|<span data-ttu-id="a5971-125">类别</span><span class="sxs-lookup"><span data-stu-id="a5971-125">Category</span></span>|<span data-ttu-id="a5971-126">属性数据类型</span><span class="sxs-lookup"><span data-stu-id="a5971-126">Property data type</span></span>|  
|---|---|  
|<span data-ttu-id="a5971-127">**字符串**</span><span class="sxs-lookup"><span data-stu-id="a5971-127">**Strings**</span></span>|[<span data-ttu-id="a5971-128">字符串</span><span class="sxs-lookup"><span data-stu-id="a5971-128">String</span></span>](../../../visual-basic/language-reference/data-types/string-data-type.md)|  
|<span data-ttu-id="a5971-129">**图像**</span><span class="sxs-lookup"><span data-stu-id="a5971-129">**Images**</span></span>|<xref:System.Drawing.Bitmap>|  
|<span data-ttu-id="a5971-130">**图标**</span><span class="sxs-lookup"><span data-stu-id="a5971-130">**Icons**</span></span>|<xref:System.Drawing.Icon>|  
|<span data-ttu-id="a5971-131">**音频**</span><span class="sxs-lookup"><span data-stu-id="a5971-131">**Audio**</span></span>|<xref:System.IO.UnmanagedMemoryStream><br /><br /> <span data-ttu-id="a5971-132"><xref:System.IO.UnmanagedMemoryStream> 类派生自 <xref:System.IO.Stream> 类，因此它可用于采用流的方法，如 <xref:Microsoft.VisualBasic.Devices.Audio.Play%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="a5971-132">The <xref:System.IO.UnmanagedMemoryStream> class derives from the <xref:System.IO.Stream> class, so it can be used with methods that take streams, such as the <xref:Microsoft.VisualBasic.Devices.Audio.Play%2A> method.</span></span>|  
|<span data-ttu-id="a5971-133">**文件**</span><span class="sxs-lookup"><span data-stu-id="a5971-133">**Files**</span></span>|<span data-ttu-id="a5971-134">文本文件的 -   [字符串](../../../visual-basic/language-reference/data-types/string-data-type.md)。</span><span class="sxs-lookup"><span data-stu-id="a5971-134">-   [String](../../../visual-basic/language-reference/data-types/string-data-type.md) for text files.</span></span><br /><span data-ttu-id="a5971-135">图像文件 -   <xref:System.Drawing.Bitmap>。</span><span class="sxs-lookup"><span data-stu-id="a5971-135">-   <xref:System.Drawing.Bitmap> for image files.</span></span><br /><span data-ttu-id="a5971-136">图标文件 -   <xref:System.Drawing.Icon>。</span><span class="sxs-lookup"><span data-stu-id="a5971-136">-   <xref:System.Drawing.Icon> for icon files.</span></span><br /><span data-ttu-id="a5971-137">-   声音文件的 <xref:System.IO.UnmanagedMemoryStream>。</span><span class="sxs-lookup"><span data-stu-id="a5971-137">-   <xref:System.IO.UnmanagedMemoryStream> for sound files.</span></span>|  
|<span data-ttu-id="a5971-138">**其他**</span><span class="sxs-lookup"><span data-stu-id="a5971-138">**Other**</span></span>|<span data-ttu-id="a5971-139">由设计器的**类型**列中的信息确定。</span><span class="sxs-lookup"><span data-stu-id="a5971-139">Determined by the information in the designer's **Type** column.</span></span>|  
  
## <a name="classes"></a><span data-ttu-id="a5971-140">类</span><span class="sxs-lookup"><span data-stu-id="a5971-140">Classes</span></span>  
 <span data-ttu-id="a5971-141">`My.Resources` 对象将每个资源文件作为具有共享属性的类公开。</span><span class="sxs-lookup"><span data-stu-id="a5971-141">The `My.Resources` object exposes each resource file as a class with shared properties.</span></span> <span data-ttu-id="a5971-142">类名称与资源文件的名称相同。</span><span class="sxs-lookup"><span data-stu-id="a5971-142">The class name is the same as the name of the resource file.</span></span> <span data-ttu-id="a5971-143">如上一节所述，资源文件中的资源作为类中的属性公开。</span><span class="sxs-lookup"><span data-stu-id="a5971-143">As described in the previous section, the resources in a resource file are exposed as properties in the class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a5971-144">示例</span><span class="sxs-lookup"><span data-stu-id="a5971-144">Example</span></span>  
 <span data-ttu-id="a5971-145">此示例将窗体的标题设置为应用程序资源文件中名为 `Form1Title` 的字符串资源。</span><span class="sxs-lookup"><span data-stu-id="a5971-145">This example sets the title of a form to the string resource named `Form1Title` in the application resource file.</span></span> <span data-ttu-id="a5971-146">要使此示例正常运行，应用程序的资源文件中必须具有一个名为 `Form1Title` 的字符串。</span><span class="sxs-lookup"><span data-stu-id="a5971-146">For the example to work, the application must have a string named `Form1Title` in its resource file.</span></span>  
  
 [!code-vb[VbVbalrMyResources#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="a5971-147">示例</span><span class="sxs-lookup"><span data-stu-id="a5971-147">Example</span></span>  
 <span data-ttu-id="a5971-148">此示例将窗体的图标设置为存储在应用程序的资源文件中名为 `Form1Icon` 的图标。</span><span class="sxs-lookup"><span data-stu-id="a5971-148">This example sets the icon of the form to the icon named `Form1Icon` that is stored in the application's resource file.</span></span> <span data-ttu-id="a5971-149">要使此示例正常运行，应用程序的资源文件中必须具有一个名为 `Form1Icon` 的图标。</span><span class="sxs-lookup"><span data-stu-id="a5971-149">For the example to work, the application must have an icon named `Form1Icon` in its resource file.</span></span>  
  
 [!code-vb[VbVbalrMyResources#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#2)]  
  
## <a name="example"></a><span data-ttu-id="a5971-150">示例</span><span class="sxs-lookup"><span data-stu-id="a5971-150">Example</span></span>  
 <span data-ttu-id="a5971-151">此示例将窗体的背景图像设置为在应用程序资源文件中名为 `Form1Background`的图像资源。</span><span class="sxs-lookup"><span data-stu-id="a5971-151">This example sets the background image of a form to the image resource named `Form1Background`, which is in the application resource file.</span></span> <span data-ttu-id="a5971-152">要使此示例正常运行，应用程序的资源文件中必须具有名为 `Form1Background` 的映像资源。</span><span class="sxs-lookup"><span data-stu-id="a5971-152">For this example to work, the application must have an image resource named `Form1Background` in its resource file.</span></span>  
  
 [!code-vb[VbVbalrMyResources#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="a5971-153">示例</span><span class="sxs-lookup"><span data-stu-id="a5971-153">Example</span></span>  
 <span data-ttu-id="a5971-154">此示例在应用程序的资源文件中播放存储为名为 `Form1Greeting` 的音频资源的声音。</span><span class="sxs-lookup"><span data-stu-id="a5971-154">This example plays the sound that is stored as an audio resource named `Form1Greeting` in the application's resource file.</span></span> <span data-ttu-id="a5971-155">要使此示例正常运行，应用程序的资源文件中必须具有名为 `Form1Greeting` 的音频资源。</span><span class="sxs-lookup"><span data-stu-id="a5971-155">For the example to work, the application must have an audio resource named `Form1Greeting` in its resource file.</span></span> <span data-ttu-id="a5971-156">`My.Computer.Audio.Play` 方法仅适用于 Windows 窗体应用程序。</span><span class="sxs-lookup"><span data-stu-id="a5971-156">The `My.Computer.Audio.Play` method is available only for Windows Forms applications.</span></span>  
  
 [!code-vb[VbVbalrMyResources#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#4)]  
  
## <a name="example"></a><span data-ttu-id="a5971-157">示例</span><span class="sxs-lookup"><span data-stu-id="a5971-157">Example</span></span>  
 <span data-ttu-id="a5971-158">此示例检索应用程序的字符串资源的法语区域性版本。</span><span class="sxs-lookup"><span data-stu-id="a5971-158">This example retrieves the French-culture version of a  string resource of the application.</span></span> <span data-ttu-id="a5971-159">资源名为 `Message`。</span><span class="sxs-lookup"><span data-stu-id="a5971-159">The resource is named `Message`.</span></span> <span data-ttu-id="a5971-160">若要更改 `My.Resources` 对象使用的区域性，该示例使用 <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.ChangeUICulture%2A>。</span><span class="sxs-lookup"><span data-stu-id="a5971-160">To change the culture that the `My.Resources` object uses, the example uses <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.ChangeUICulture%2A>.</span></span>  
  
 <span data-ttu-id="a5971-161">要使此示例正常运行，应用程序的资源文件中必须具有一个名为 `Message` 的字符串，应用程序应具有该资源文件的法语区域性版本 Resources.fr。</span><span class="sxs-lookup"><span data-stu-id="a5971-161">For this example to work, the application must have a string named `Message` in its resource file, and the application should have the French-culture version of that resource file, Resources.fr-FR.resx.</span></span> <span data-ttu-id="a5971-162">如果应用程序没有资源文件的法语区域性版本，则 `My.Resource` 对象将从默认区域性资源文件中检索资源。</span><span class="sxs-lookup"><span data-stu-id="a5971-162">If the application does not have the French-culture version of the resource file, the `My.Resource` object retrieves the resource from the default-culture resource file.</span></span>  
  
 [!code-vb[VbVbalrMyResources#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#10)]  
  
## <a name="see-also"></a><span data-ttu-id="a5971-163">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a5971-163">See also</span></span>

- [<span data-ttu-id="a5971-164">管理应用程序资源 (.NET)</span><span class="sxs-lookup"><span data-stu-id="a5971-164">Managing Application Resources (.NET)</span></span>](/visualstudio/ide/managing-application-resources-dotnet)
- [<span data-ttu-id="a5971-165">桌面应用中的资源</span><span class="sxs-lookup"><span data-stu-id="a5971-165">Resources in Desktop Apps</span></span>](../../../framework/resources/index.md)
