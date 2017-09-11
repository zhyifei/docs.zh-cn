---
title: "My.Resources 对象 |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- My.Resources
- My.Resources.MyResources.ResourceManager
- My.Resources.MyResources.Culture
dev_langs:
- VB
helpviewer_keywords:
- My.Resources object
ms.assetid: 34c3f2dc-7b87-432c-9d5f-17ea666bb266
caps.latest.revision: 22
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 68d0ce69441f18f7a59cb84b0cf363eab9f98669
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="myresources-object"></a><span data-ttu-id="514c7-102">My.Resources 对象</span><span class="sxs-lookup"><span data-stu-id="514c7-102">My.Resources Object</span></span>
<span data-ttu-id="514c7-103">提供用于访问应用程序的资源的属性和类。</span><span class="sxs-lookup"><span data-stu-id="514c7-103">Provides properties and classes for accessing the application's resources.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="514c7-104">备注</span><span class="sxs-lookup"><span data-stu-id="514c7-104">Remarks</span></span>  
 <span data-ttu-id="514c7-105">`My.Resources`对象提供了对应用程序的资源的访问，并允许动态应用程序检索资源。</span><span class="sxs-lookup"><span data-stu-id="514c7-105">The `My.Resources` object provides access to the application's resources and lets you dynamically retrieve resources for your application.</span></span> <span data-ttu-id="514c7-106">有关详细信息，请参阅[管理应用程序资源 (.NET)](https://docs.microsoft.com/visualstudio/ide/managing-application-resources-dotnet)。</span><span class="sxs-lookup"><span data-stu-id="514c7-106">For more information, see [Managing Application Resources (.NET)](https://docs.microsoft.com/visualstudio/ide/managing-application-resources-dotnet).</span></span>  
  
 <span data-ttu-id="514c7-107">`My.Resources`对象仅公开全局资源。</span><span class="sxs-lookup"><span data-stu-id="514c7-107">The `My.Resources` object exposes only global resources.</span></span> <span data-ttu-id="514c7-108">它不提供对与窗体关联的资源文件的访问。</span><span class="sxs-lookup"><span data-stu-id="514c7-108">It does not provide access to resource files associated with forms.</span></span> <span data-ttu-id="514c7-109">必须从该窗体来访问窗体资源。</span><span class="sxs-lookup"><span data-stu-id="514c7-109">You must access the form resources from the form.</span></span> <span data-ttu-id="514c7-110">有关详细信息，请参阅[演练：本地化 Windows 窗体](http://msdn.microsoft.com/en-us/9a96220d-a19b-4de0-9f48-01e5d82679e5)。</span><span class="sxs-lookup"><span data-stu-id="514c7-110">For more information, see [Walkthrough: Localizing Windows Forms](http://msdn.microsoft.com/en-us/9a96220d-a19b-4de0-9f48-01e5d82679e5).</span></span>  
  
 <span data-ttu-id="514c7-111">您可以访问应用程序的区域性特定资源文件从`My.Resources`对象。</span><span class="sxs-lookup"><span data-stu-id="514c7-111">You can access the application's culture-specific resource files from the `My.Resources` object.</span></span> <span data-ttu-id="514c7-112">默认情况下，`My.Resources`对象内查找匹配的区域中的资源文件中的资源<xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.UICulture%2A>属性。</xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.UICulture%2A></span><span class="sxs-lookup"><span data-stu-id="514c7-112">By default, the `My.Resources` object looks up resources from the resource file that matches the culture in the <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.UICulture%2A> property.</span></span> <span data-ttu-id="514c7-113">但是，您可以重写此行为并指定特定区域性使用的资源。</span><span class="sxs-lookup"><span data-stu-id="514c7-113">However, you can override this behavior and specify a particular culture to use for the resources.</span></span> <span data-ttu-id="514c7-114">有关详细信息，请参阅[桌面应用中的资源](http://msdn.microsoft.com/library/8ad495d4-2941-40cf-bf64-e82e85825890)。</span><span class="sxs-lookup"><span data-stu-id="514c7-114">For more information, see [Resources in Desktop Apps](http://msdn.microsoft.com/library/8ad495d4-2941-40cf-bf64-e82e85825890).</span></span>  
  
## <a name="properties"></a><span data-ttu-id="514c7-115">属性</span><span class="sxs-lookup"><span data-stu-id="514c7-115">Properties</span></span>  
 <span data-ttu-id="514c7-116">属性的`My.Resources`对象提供对应用程序的资源的只读访问。</span><span class="sxs-lookup"><span data-stu-id="514c7-116">The properties of the `My.Resources` object provide read-only access to your application's resources.</span></span> <span data-ttu-id="514c7-117">若要添加或删除资源，请使用**项目设计器**。</span><span class="sxs-lookup"><span data-stu-id="514c7-117">To add or remove resources, use the **Project Designer**.</span></span> <span data-ttu-id="514c7-118">有关详细信息，请参阅[如何︰ 添加或移除资源](http://msdn.microsoft.com/en-us/7b77bc06-3952-4799-b029-def3f8f7f88d)。</span><span class="sxs-lookup"><span data-stu-id="514c7-118">For more information, see [How to: Add or Remove Resources](http://msdn.microsoft.com/en-us/7b77bc06-3952-4799-b029-def3f8f7f88d).</span></span> <span data-ttu-id="514c7-119">您可以访问资源通过添加**项目设计器**使用`My.Resources.``resourceName`。</span><span class="sxs-lookup"><span data-stu-id="514c7-119">You can access resources added through the **Project Designer** by using `My.Resources.``resourceName`.</span></span>  
  
 <span data-ttu-id="514c7-120">您还可以添加或移除通过选择你的项目中的资源文件**解决方案资源管理器**，然后单击**添加新项**或**添加现有项**从**项目**菜单。</span><span class="sxs-lookup"><span data-stu-id="514c7-120">You can also add or remove resource files by selecting your project in **Solution Explorer** and clicking **Add New Item** or **Add Existing Item** from the **Project** menu.</span></span> <span data-ttu-id="514c7-121">您可以访问通过这种方式添加的资源`My.Resources.``resourceFileName`。`resourceName`。</span><span class="sxs-lookup"><span data-stu-id="514c7-121">You can access resources added in this manner by using `My.Resources.``resourceFileName`.`resourceName`.</span></span>  
  
 <span data-ttu-id="514c7-122">每个资源具有名称、 类别和值，并且这些资源设置决定了用于访问该资源的属性中的显示方式`My.Resources`对象。</span><span class="sxs-lookup"><span data-stu-id="514c7-122">Each resource has a name, category, and value, and these resource settings determine how the property to access the resource appears in the `My.Resources` object.</span></span> <span data-ttu-id="514c7-123">在添加的资源**项目设计器**:</span><span class="sxs-lookup"><span data-stu-id="514c7-123">For resources added in the **Project Designer**:</span></span>  
  
-   <span data-ttu-id="514c7-124">名称确定该属性的名称</span><span class="sxs-lookup"><span data-stu-id="514c7-124">The name determines the name of the property,</span></span>  
  
-   <span data-ttu-id="514c7-125">资源数据是与属性的值</span><span class="sxs-lookup"><span data-stu-id="514c7-125">The resource data is the value of the property,</span></span>  
  
-   <span data-ttu-id="514c7-126">类别确定属性的类型︰</span><span class="sxs-lookup"><span data-stu-id="514c7-126">The category determines the type of the property:</span></span>  
  
|<span data-ttu-id="514c7-127">类别</span><span class="sxs-lookup"><span data-stu-id="514c7-127">Category</span></span>|<span data-ttu-id="514c7-128">属性数据类型</span><span class="sxs-lookup"><span data-stu-id="514c7-128">Property data type</span></span>|  
|---|---|  
|<span data-ttu-id="514c7-129">**字符串**</span><span class="sxs-lookup"><span data-stu-id="514c7-129">**Strings**</span></span>|[<span data-ttu-id="514c7-130">字符串</span><span class="sxs-lookup"><span data-stu-id="514c7-130">String</span></span>](../../../visual-basic/language-reference/data-types/string-data-type.md)|  
|<span data-ttu-id="514c7-131">**图像**</span><span class="sxs-lookup"><span data-stu-id="514c7-131">**Images**</span></span>|<span data-ttu-id="514c7-132"><xref:System.Drawing.Bitmap></xref:System.Drawing.Bitmap></span><span class="sxs-lookup"><span data-stu-id="514c7-132"><xref:System.Drawing.Bitmap></span></span>|  
|<span data-ttu-id="514c7-133">**图标**</span><span class="sxs-lookup"><span data-stu-id="514c7-133">**Icons**</span></span>|<span data-ttu-id="514c7-134"><xref:System.Drawing.Icon></xref:System.Drawing.Icon></span><span class="sxs-lookup"><span data-stu-id="514c7-134"><xref:System.Drawing.Icon></span></span>|  
|<span data-ttu-id="514c7-135">**音频**</span><span class="sxs-lookup"><span data-stu-id="514c7-135">**Audio**</span></span>|<span data-ttu-id="514c7-136"><xref:System.IO.UnmanagedMemoryStream></xref:System.IO.UnmanagedMemoryStream></span><span class="sxs-lookup"><span data-stu-id="514c7-136"><xref:System.IO.UnmanagedMemoryStream></span></span><br /><br /> <span data-ttu-id="514c7-137"><xref:System.IO.UnmanagedMemoryStream>类派生自<xref:System.IO.Stream>类，以便它可以用于以流，如方法<xref:Microsoft.VisualBasic.Devices.Audio.Play%2A>方法。</xref:Microsoft.VisualBasic.Devices.Audio.Play%2A> </xref:System.IO.Stream> </xref:System.IO.UnmanagedMemoryStream></span><span class="sxs-lookup"><span data-stu-id="514c7-137">The <xref:System.IO.UnmanagedMemoryStream> class derives from the <xref:System.IO.Stream> class, so it can be used with methods that take streams, such as the <xref:Microsoft.VisualBasic.Devices.Audio.Play%2A> method.</span></span>|  
|<span data-ttu-id="514c7-138">**文件**</span><span class="sxs-lookup"><span data-stu-id="514c7-138">**Files**</span></span>|<span data-ttu-id="514c7-139">-   [字符串](../../../visual-basic/language-reference/data-types/string-data-type.md)为文本文件。</span><span class="sxs-lookup"><span data-stu-id="514c7-139">-   [String](../../../visual-basic/language-reference/data-types/string-data-type.md) for text files.</span></span><br /><span data-ttu-id="514c7-140">-<xref:System.Drawing.Bitmap>图像文件。</xref:System.Drawing.Bitmap></span><span class="sxs-lookup"><span data-stu-id="514c7-140">-   <xref:System.Drawing.Bitmap> for image files.</span></span><br /><span data-ttu-id="514c7-141">-<xref:System.Drawing.Icon>图标文件。</xref:System.Drawing.Icon></span><span class="sxs-lookup"><span data-stu-id="514c7-141">-   <xref:System.Drawing.Icon> for icon files.</span></span><br /><span data-ttu-id="514c7-142">-<xref:System.IO.UnmanagedMemoryStream>的声音文件。</xref:System.IO.UnmanagedMemoryStream></span><span class="sxs-lookup"><span data-stu-id="514c7-142">-   <xref:System.IO.UnmanagedMemoryStream> for sound files.</span></span>|  
|<span data-ttu-id="514c7-143">**其他**</span><span class="sxs-lookup"><span data-stu-id="514c7-143">**Other**</span></span>|<span data-ttu-id="514c7-144">通过在设计器中的信息确定**类型**列。</span><span class="sxs-lookup"><span data-stu-id="514c7-144">Determined by the information in the designer's **Type** column.</span></span>|  
  
## <a name="classes"></a><span data-ttu-id="514c7-145">类</span><span class="sxs-lookup"><span data-stu-id="514c7-145">Classes</span></span>  
 <span data-ttu-id="514c7-146">`My.Resources`对象将作为具有共享属性的类公开每个资源文件。</span><span class="sxs-lookup"><span data-stu-id="514c7-146">The `My.Resources` object exposes each resource file as a class with shared properties.</span></span> <span data-ttu-id="514c7-147">类名是资源文件的名称相同。</span><span class="sxs-lookup"><span data-stu-id="514c7-147">The class name is the same as the name of the resource file.</span></span> <span data-ttu-id="514c7-148">如前一部分中所述，资源文件中的资源公开为类中的属性。</span><span class="sxs-lookup"><span data-stu-id="514c7-148">As described in the previous section, the resources in a resource file are exposed as properties in the class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="514c7-149">示例</span><span class="sxs-lookup"><span data-stu-id="514c7-149">Example</span></span>  
 <span data-ttu-id="514c7-150">此示例将窗体的标题设置为字符串资源名称为`Form1Title`应用程序资源文件中。</span><span class="sxs-lookup"><span data-stu-id="514c7-150">This example sets the title of a form to the string resource named `Form1Title` in the application resource file.</span></span> <span data-ttu-id="514c7-151">对于该示例能工作，该应用程序必须具有一个名为字符串`Form1Title`其资源文件中。</span><span class="sxs-lookup"><span data-stu-id="514c7-151">For the example to work, the application must have a string named `Form1Title` in its resource file.</span></span> <span data-ttu-id="514c7-152">有关详细信息，请参阅[如何︰ 添加或移除资源](http://msdn.microsoft.com/en-us/7b77bc06-3952-4799-b029-def3f8f7f88d)。</span><span class="sxs-lookup"><span data-stu-id="514c7-152">For more information, see [How to: Add or Remove Resources](http://msdn.microsoft.com/en-us/7b77bc06-3952-4799-b029-def3f8f7f88d).</span></span>  
  
 <span data-ttu-id="514c7-153">[!code-vb[VbVbalrMyResources #&1;](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-resources-object_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="514c7-153">[!code-vb[VbVbalrMyResources#1](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-resources-object_1.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="514c7-154">示例</span><span class="sxs-lookup"><span data-stu-id="514c7-154">Example</span></span>  
 <span data-ttu-id="514c7-155">本示例将窗体的图标名为图标为`Form1Icon`存储在应用程序的资源文件。</span><span class="sxs-lookup"><span data-stu-id="514c7-155">This example sets the icon of the form to the icon named `Form1Icon` that is stored in the application's resource file.</span></span> <span data-ttu-id="514c7-156">对于该示例能工作，应用程序必须具有名为图标`Form1Icon`其资源文件中。</span><span class="sxs-lookup"><span data-stu-id="514c7-156">For the example to work, the application must have an icon named `Form1Icon` in its resource file.</span></span>  
  
 <span data-ttu-id="514c7-157">[!code-vb[VbVbalrMyResources #&2;](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-resources-object_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="514c7-157">[!code-vb[VbVbalrMyResources#2](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-resources-object_2.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="514c7-158">示例</span><span class="sxs-lookup"><span data-stu-id="514c7-158">Example</span></span>  
 <span data-ttu-id="514c7-159">此示例将窗体的背景图像设置到名为的图像资源`Form1Background`，这是应用程序资源文件。</span><span class="sxs-lookup"><span data-stu-id="514c7-159">This example sets the background image of a form to the image resource named `Form1Background`, which is in the application resource file.</span></span> <span data-ttu-id="514c7-160">对于此示例正常工作，该应用程序必须具有名为的图像资源`Form1Background`其资源文件中。</span><span class="sxs-lookup"><span data-stu-id="514c7-160">For this example to work, the application must have an image resource named `Form1Background` in its resource file.</span></span>  
  
 <span data-ttu-id="514c7-161">[!code-vb[VbVbalrMyResources #&3;](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-resources-object_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="514c7-161">[!code-vb[VbVbalrMyResources#3](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-resources-object_3.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="514c7-162">示例</span><span class="sxs-lookup"><span data-stu-id="514c7-162">Example</span></span>  
 <span data-ttu-id="514c7-163">此示例播放的声音，作为名为音频资源存储`Form1Greeting`应用程序的资源文件中。</span><span class="sxs-lookup"><span data-stu-id="514c7-163">This example plays the sound that is stored as an audio resource named `Form1Greeting` in the application's resource file.</span></span> <span data-ttu-id="514c7-164">对于该示例能工作，应用程序必须具有名为音频资源`Form1Greeting`其资源文件中。</span><span class="sxs-lookup"><span data-stu-id="514c7-164">For the example to work, the application must have an audio resource named `Form1Greeting` in its resource file.</span></span> <span data-ttu-id="514c7-165">`My.Computer.Audio.Play`方法是仅适用于 Windows 窗体应用程序。</span><span class="sxs-lookup"><span data-stu-id="514c7-165">The `My.Computer.Audio.Play` method is available only for Windows Forms applications.</span></span>  
  
 <span data-ttu-id="514c7-166">[!code-vb[VbVbalrMyResources #&4;](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-resources-object_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="514c7-166">[!code-vb[VbVbalrMyResources#4](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-resources-object_4.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="514c7-167">示例</span><span class="sxs-lookup"><span data-stu-id="514c7-167">Example</span></span>  
 <span data-ttu-id="514c7-168">此示例检索字符串资源的应用程序的法语区域性版本。</span><span class="sxs-lookup"><span data-stu-id="514c7-168">This example retrieves the French-culture version of a  string resource of the application.</span></span> <span data-ttu-id="514c7-169">指定的资源`Message`。</span><span class="sxs-lookup"><span data-stu-id="514c7-169">The resource is named `Message`.</span></span> <span data-ttu-id="514c7-170">若要更改区域性，`My.Resources`对象使用，该示例使用<xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.ChangeUICulture%2A>。</xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.ChangeUICulture%2A></span><span class="sxs-lookup"><span data-stu-id="514c7-170">To change the culture that the `My.Resources` object uses, the example uses <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.ChangeUICulture%2A>.</span></span>  
  
 <span data-ttu-id="514c7-171">对于此示例正常工作，该应用程序必须具有一个名为字符串`Message`在其资源文件和应用程序应该有该资源文件中，Resources.fr-fr.resx，该文件的法语区域性版本。</span><span class="sxs-lookup"><span data-stu-id="514c7-171">For this example to work, the application must have a string named `Message` in its resource file, and the application should have the French-culture version of that resource file, Resources.fr-FR.resx.</span></span> <span data-ttu-id="514c7-172">有关详细信息，请参阅[如何︰ 添加或移除资源](http://msdn.microsoft.com/en-us/7b77bc06-3952-4799-b029-def3f8f7f88d)。</span><span class="sxs-lookup"><span data-stu-id="514c7-172">For more information, see [How to: Add or Remove Resources](http://msdn.microsoft.com/en-us/7b77bc06-3952-4799-b029-def3f8f7f88d).</span></span> <span data-ttu-id="514c7-173">如果应用程序不具有资源文件中，法语区域性版本`My.Resource`对象将从默认区域性资源文件中检索资源。</span><span class="sxs-lookup"><span data-stu-id="514c7-173">If the application does not have the French-culture version of the resource file, the `My.Resource` object retrieves the resource from the default-culture resource file.</span></span>  
  
 <span data-ttu-id="514c7-174">[!code-vb[VbVbalrMyResources #&10;](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-resources-object_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="514c7-174">[!code-vb[VbVbalrMyResources#10](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-resources-object_5.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="514c7-175">另请参阅</span><span class="sxs-lookup"><span data-stu-id="514c7-175">See Also</span></span>  
 <span data-ttu-id="514c7-176">[如何︰ 添加或删除资源](http://msdn.microsoft.com/en-us/7b77bc06-3952-4799-b029-def3f8f7f88d) </span><span class="sxs-lookup"><span data-stu-id="514c7-176">[How to: Add or Remove Resources](http://msdn.microsoft.com/en-us/7b77bc06-3952-4799-b029-def3f8f7f88d) </span></span>  
<span data-ttu-id="514c7-177"> [管理应用程序资源 (.NET)](https://docs.microsoft.com/visualstudio/ide/managing-application-resources-dotnet) </span><span class="sxs-lookup"><span data-stu-id="514c7-177"> [Managing Application Resources (.NET)](https://docs.microsoft.com/visualstudio/ide/managing-application-resources-dotnet) </span></span>  
<span data-ttu-id="514c7-178"> [桌面应用程序中的资源](http://msdn.microsoft.com/library/8ad495d4-2941-40cf-bf64-e82e85825890) </span><span class="sxs-lookup"><span data-stu-id="514c7-178"> [Resources in Desktop Apps](http://msdn.microsoft.com/library/8ad495d4-2941-40cf-bf64-e82e85825890) </span></span>  
<span data-ttu-id="514c7-179"> [演练︰ 本地化 Windows 窗体](http://msdn.microsoft.com/en-us/9a96220d-a19b-4de0-9f48-01e5d82679e5)</span><span class="sxs-lookup"><span data-stu-id="514c7-179"> [Walkthrough: Localizing Windows Forms](http://msdn.microsoft.com/en-us/9a96220d-a19b-4de0-9f48-01e5d82679e5)</span></span>
