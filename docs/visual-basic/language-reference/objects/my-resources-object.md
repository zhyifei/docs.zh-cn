---
title: "My.Resources 对象"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- My.Resources
- My.Resources.MyResources.ResourceManager
- My.Resources.MyResources.Culture
helpviewer_keywords: My.Resources object
ms.assetid: 34c3f2dc-7b87-432c-9d5f-17ea666bb266
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b2a2de7229f59e7deea29fe4186a5e466459d9fa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="myresources-object"></a><span data-ttu-id="7e52e-102">My.Resources 对象</span><span class="sxs-lookup"><span data-stu-id="7e52e-102">My.Resources Object</span></span>
<span data-ttu-id="7e52e-103">提供用于访问应用程序的资源的属性和类。</span><span class="sxs-lookup"><span data-stu-id="7e52e-103">Provides properties and classes for accessing the application's resources.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7e52e-104">备注</span><span class="sxs-lookup"><span data-stu-id="7e52e-104">Remarks</span></span>  
 <span data-ttu-id="7e52e-105">`My.Resources`对象提供了对应用程序的资源的访问，并允许动态检索应用程序的资源。</span><span class="sxs-lookup"><span data-stu-id="7e52e-105">The `My.Resources` object provides access to the application's resources and lets you dynamically retrieve resources for your application.</span></span> <span data-ttu-id="7e52e-106">有关详细信息，请参阅[管理应用程序资源 (.NET)](/visualstudio/ide/managing-application-resources-dotnet)。</span><span class="sxs-lookup"><span data-stu-id="7e52e-106">For more information, see [Managing Application Resources (.NET)](/visualstudio/ide/managing-application-resources-dotnet).</span></span>  
  
 <span data-ttu-id="7e52e-107">`My.Resources`对象公开仅全局资源。</span><span class="sxs-lookup"><span data-stu-id="7e52e-107">The `My.Resources` object exposes only global resources.</span></span> <span data-ttu-id="7e52e-108">它不提供对与窗体关联的资源文件的访问。</span><span class="sxs-lookup"><span data-stu-id="7e52e-108">It does not provide access to resource files associated with forms.</span></span> <span data-ttu-id="7e52e-109">必须从窗体来访问窗体资源。</span><span class="sxs-lookup"><span data-stu-id="7e52e-109">You must access the form resources from the form.</span></span> <span data-ttu-id="7e52e-110">有关详细信息，请参阅[演练：本地化 Windows 窗体](http://msdn.microsoft.com/en-us/9a96220d-a19b-4de0-9f48-01e5d82679e5)。</span><span class="sxs-lookup"><span data-stu-id="7e52e-110">For more information, see [Walkthrough: Localizing Windows Forms](http://msdn.microsoft.com/en-us/9a96220d-a19b-4de0-9f48-01e5d82679e5).</span></span>  
  
 <span data-ttu-id="7e52e-111">你可以访问应用程序的区域性特定资源文件从`My.Resources`对象。</span><span class="sxs-lookup"><span data-stu-id="7e52e-111">You can access the application's culture-specific resource files from the `My.Resources` object.</span></span> <span data-ttu-id="7e52e-112">默认情况下，`My.Resources`对象查找中的区域性匹配的资源文件中的资源<xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.UICulture%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="7e52e-112">By default, the `My.Resources` object looks up resources from the resource file that matches the culture in the <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.UICulture%2A> property.</span></span> <span data-ttu-id="7e52e-113">但是，你可以重写此行为并指定特定区域性的资源使用。</span><span class="sxs-lookup"><span data-stu-id="7e52e-113">However, you can override this behavior and specify a particular culture to use for the resources.</span></span> <span data-ttu-id="7e52e-114">有关详细信息，请参阅[桌面应用中的资源](../../../framework/resources/index.md)。</span><span class="sxs-lookup"><span data-stu-id="7e52e-114">For more information, see [Resources in Desktop Apps](../../../framework/resources/index.md).</span></span>  
  
## <a name="properties"></a><span data-ttu-id="7e52e-115">属性</span><span class="sxs-lookup"><span data-stu-id="7e52e-115">Properties</span></span>  
 <span data-ttu-id="7e52e-116">属性`My.Resources`对象提供对应用程序的资源的只读访问。</span><span class="sxs-lookup"><span data-stu-id="7e52e-116">The properties of the `My.Resources` object provide read-only access to your application's resources.</span></span> <span data-ttu-id="7e52e-117">若要添加或删除资源，使用**项目设计器**。</span><span class="sxs-lookup"><span data-stu-id="7e52e-117">To add or remove resources, use the **Project Designer**.</span></span> <span data-ttu-id="7e52e-118">有关详细信息，请参阅[如何： 添加或删除资源](http://msdn.microsoft.com/en-us/7b77bc06-3952-4799-b029-def3f8f7f88d)。</span><span class="sxs-lookup"><span data-stu-id="7e52e-118">For more information, see [How to: Add or Remove Resources](http://msdn.microsoft.com/en-us/7b77bc06-3952-4799-b029-def3f8f7f88d).</span></span> <span data-ttu-id="7e52e-119">你可以访问通过添加资源**项目设计器**使用`My.Resources.``resourceName`。</span><span class="sxs-lookup"><span data-stu-id="7e52e-119">You can access resources added through the **Project Designer** by using `My.Resources.``resourceName`.</span></span>  
  
 <span data-ttu-id="7e52e-120">你还可以添加或移除通过选择你的项目中的资源文件**解决方案资源管理器**并单击**添加新项**或**添加现有项**从**项目**菜单。</span><span class="sxs-lookup"><span data-stu-id="7e52e-120">You can also add or remove resource files by selecting your project in **Solution Explorer** and clicking **Add New Item** or **Add Existing Item** from the **Project** menu.</span></span> <span data-ttu-id="7e52e-121">你可以访问通过使用这种方式添加的资源`My.Resources.``resourceFileName`.`resourceName`。</span><span class="sxs-lookup"><span data-stu-id="7e52e-121">You can access resources added in this manner by using `My.Resources.``resourceFileName`.`resourceName`.</span></span>  
  
 <span data-ttu-id="7e52e-122">每个资源具有名称、 类别和值，并且这些资源设置确定要访问该资源的属性中的显示方式`My.Resources`对象。</span><span class="sxs-lookup"><span data-stu-id="7e52e-122">Each resource has a name, category, and value, and these resource settings determine how the property to access the resource appears in the `My.Resources` object.</span></span> <span data-ttu-id="7e52e-123">在中添加的资源**项目设计器**:</span><span class="sxs-lookup"><span data-stu-id="7e52e-123">For resources added in the **Project Designer**:</span></span>  
  
-   <span data-ttu-id="7e52e-124">名称确定该属性的名称</span><span class="sxs-lookup"><span data-stu-id="7e52e-124">The name determines the name of the property,</span></span>  
  
-   <span data-ttu-id="7e52e-125">资源数据是，将该属性的值</span><span class="sxs-lookup"><span data-stu-id="7e52e-125">The resource data is the value of the property,</span></span>  
  
-   <span data-ttu-id="7e52e-126">类别确定属性的类型：</span><span class="sxs-lookup"><span data-stu-id="7e52e-126">The category determines the type of the property:</span></span>  
  
|<span data-ttu-id="7e52e-127">类别</span><span class="sxs-lookup"><span data-stu-id="7e52e-127">Category</span></span>|<span data-ttu-id="7e52e-128">属性数据类型</span><span class="sxs-lookup"><span data-stu-id="7e52e-128">Property data type</span></span>|  
|---|---|  
|<span data-ttu-id="7e52e-129">**字符串**</span><span class="sxs-lookup"><span data-stu-id="7e52e-129">**Strings**</span></span>|[<span data-ttu-id="7e52e-130">字符串</span><span class="sxs-lookup"><span data-stu-id="7e52e-130">String</span></span>](../../../visual-basic/language-reference/data-types/string-data-type.md)|  
|<span data-ttu-id="7e52e-131">**图像**</span><span class="sxs-lookup"><span data-stu-id="7e52e-131">**Images**</span></span>|<xref:System.Drawing.Bitmap>|  
|<span data-ttu-id="7e52e-132">**图标**</span><span class="sxs-lookup"><span data-stu-id="7e52e-132">**Icons**</span></span>|<xref:System.Drawing.Icon>|  
|<span data-ttu-id="7e52e-133">**音频**</span><span class="sxs-lookup"><span data-stu-id="7e52e-133">**Audio**</span></span>|<xref:System.IO.UnmanagedMemoryStream><br /><br /> <span data-ttu-id="7e52e-134"><xref:System.IO.UnmanagedMemoryStream>类派生自<xref:System.IO.Stream>类，以便它可使用的方法来以流，如<xref:Microsoft.VisualBasic.Devices.Audio.Play%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="7e52e-134">The <xref:System.IO.UnmanagedMemoryStream> class derives from the <xref:System.IO.Stream> class, so it can be used with methods that take streams, such as the <xref:Microsoft.VisualBasic.Devices.Audio.Play%2A> method.</span></span>|  
|<span data-ttu-id="7e52e-135">**文件**</span><span class="sxs-lookup"><span data-stu-id="7e52e-135">**Files**</span></span>|<span data-ttu-id="7e52e-136">-   [字符串](../../../visual-basic/language-reference/data-types/string-data-type.md)的文本文件。</span><span class="sxs-lookup"><span data-stu-id="7e52e-136">-   [String](../../../visual-basic/language-reference/data-types/string-data-type.md) for text files.</span></span><br /><span data-ttu-id="7e52e-137">-   <xref:System.Drawing.Bitmap>用于图像文件。</span><span class="sxs-lookup"><span data-stu-id="7e52e-137">-   <xref:System.Drawing.Bitmap> for image files.</span></span><br /><span data-ttu-id="7e52e-138">-   <xref:System.Drawing.Icon>图标文件。</span><span class="sxs-lookup"><span data-stu-id="7e52e-138">-   <xref:System.Drawing.Icon> for icon files.</span></span><br /><span data-ttu-id="7e52e-139">-   <xref:System.IO.UnmanagedMemoryStream>声音文件。</span><span class="sxs-lookup"><span data-stu-id="7e52e-139">-   <xref:System.IO.UnmanagedMemoryStream> for sound files.</span></span>|  
|<span data-ttu-id="7e52e-140">**其他**</span><span class="sxs-lookup"><span data-stu-id="7e52e-140">**Other**</span></span>|<span data-ttu-id="7e52e-141">由设计器中的信息确定**类型**列。</span><span class="sxs-lookup"><span data-stu-id="7e52e-141">Determined by the information in the designer's **Type** column.</span></span>|  
  
## <a name="classes"></a><span data-ttu-id="7e52e-142">类</span><span class="sxs-lookup"><span data-stu-id="7e52e-142">Classes</span></span>  
 <span data-ttu-id="7e52e-143">`My.Resources`对象将作为具有共享属性的类公开每个资源文件。</span><span class="sxs-lookup"><span data-stu-id="7e52e-143">The `My.Resources` object exposes each resource file as a class with shared properties.</span></span> <span data-ttu-id="7e52e-144">类名称是资源文件的名称相同。</span><span class="sxs-lookup"><span data-stu-id="7e52e-144">The class name is the same as the name of the resource file.</span></span> <span data-ttu-id="7e52e-145">如前一部分中所述，作为在类中的属性被公开资源文件中的资源。</span><span class="sxs-lookup"><span data-stu-id="7e52e-145">As described in the previous section, the resources in a resource file are exposed as properties in the class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7e52e-146">示例</span><span class="sxs-lookup"><span data-stu-id="7e52e-146">Example</span></span>  
 <span data-ttu-id="7e52e-147">此示例将窗体的标题设置为字符串资源名称为`Form1Title`应用程序资源文件中。</span><span class="sxs-lookup"><span data-stu-id="7e52e-147">This example sets the title of a form to the string resource named `Form1Title` in the application resource file.</span></span> <span data-ttu-id="7e52e-148">对于该示例能工作，应用程序必须具有名为一个字符串`Form1Title`其资源文件中。</span><span class="sxs-lookup"><span data-stu-id="7e52e-148">For the example to work, the application must have a string named `Form1Title` in its resource file.</span></span> <span data-ttu-id="7e52e-149">有关详细信息，请参阅[如何： 添加或删除资源](http://msdn.microsoft.com/en-us/7b77bc06-3952-4799-b029-def3f8f7f88d)。</span><span class="sxs-lookup"><span data-stu-id="7e52e-149">For more information, see [How to: Add or Remove Resources](http://msdn.microsoft.com/en-us/7b77bc06-3952-4799-b029-def3f8f7f88d).</span></span>  
  
 [!code-vb[VbVbalrMyResources#1](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-resources-object_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="7e52e-150">示例</span><span class="sxs-lookup"><span data-stu-id="7e52e-150">Example</span></span>  
 <span data-ttu-id="7e52e-151">此示例将窗体的图标设置为名为图标`Form1Icon`存储在应用程序的资源文件。</span><span class="sxs-lookup"><span data-stu-id="7e52e-151">This example sets the icon of the form to the icon named `Form1Icon` that is stored in the application's resource file.</span></span> <span data-ttu-id="7e52e-152">对于该示例能工作，应用程序必须具有名为的图标`Form1Icon`其资源文件中。</span><span class="sxs-lookup"><span data-stu-id="7e52e-152">For the example to work, the application must have an icon named `Form1Icon` in its resource file.</span></span>  
  
 [!code-vb[VbVbalrMyResources#2](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-resources-object_2.vb)]  
  
## <a name="example"></a><span data-ttu-id="7e52e-153">示例</span><span class="sxs-lookup"><span data-stu-id="7e52e-153">Example</span></span>  
 <span data-ttu-id="7e52e-154">此示例中名为的图像资源设置窗体的背景图像`Form1Background`，这是在应用程序资源文件中。</span><span class="sxs-lookup"><span data-stu-id="7e52e-154">This example sets the background image of a form to the image resource named `Form1Background`, which is in the application resource file.</span></span> <span data-ttu-id="7e52e-155">对于此示例正常工作，应用程序必须具有名为图像资源`Form1Background`其资源文件中。</span><span class="sxs-lookup"><span data-stu-id="7e52e-155">For this example to work, the application must have an image resource named `Form1Background` in its resource file.</span></span>  
  
 [!code-vb[VbVbalrMyResources#3](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-resources-object_3.vb)]  
  
## <a name="example"></a><span data-ttu-id="7e52e-156">示例</span><span class="sxs-lookup"><span data-stu-id="7e52e-156">Example</span></span>  
 <span data-ttu-id="7e52e-157">此示例播放的声音，存储为音频资源名为`Form1Greeting`应用程序的资源文件中。</span><span class="sxs-lookup"><span data-stu-id="7e52e-157">This example plays the sound that is stored as an audio resource named `Form1Greeting` in the application's resource file.</span></span> <span data-ttu-id="7e52e-158">对于该示例能工作，应用程序必须具有名为音频资源`Form1Greeting`其资源文件中。</span><span class="sxs-lookup"><span data-stu-id="7e52e-158">For the example to work, the application must have an audio resource named `Form1Greeting` in its resource file.</span></span> <span data-ttu-id="7e52e-159">`My.Computer.Audio.Play`方法是仅适用于 Windows 窗体应用程序。</span><span class="sxs-lookup"><span data-stu-id="7e52e-159">The `My.Computer.Audio.Play` method is available only for Windows Forms applications.</span></span>  
  
 [!code-vb[VbVbalrMyResources#4](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-resources-object_4.vb)]  
  
## <a name="example"></a><span data-ttu-id="7e52e-160">示例</span><span class="sxs-lookup"><span data-stu-id="7e52e-160">Example</span></span>  
 <span data-ttu-id="7e52e-161">此示例检索字符串资源的应用程序的法语区域性版本。</span><span class="sxs-lookup"><span data-stu-id="7e52e-161">This example retrieves the French-culture version of a  string resource of the application.</span></span> <span data-ttu-id="7e52e-162">名为资源`Message`。</span><span class="sxs-lookup"><span data-stu-id="7e52e-162">The resource is named `Message`.</span></span> <span data-ttu-id="7e52e-163">若要更改区域性，`My.Resources`对象使用，该示例使用<xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.ChangeUICulture%2A>。</span><span class="sxs-lookup"><span data-stu-id="7e52e-163">To change the culture that the `My.Resources` object uses, the example uses <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.ChangeUICulture%2A>.</span></span>  
  
 <span data-ttu-id="7e52e-164">为此示例正常工作，应用程序必须具有名为字符串`Message`其资源中文件和应用程序应具有的资源文件，Resources.fr FR.resx 法语区域性版本。</span><span class="sxs-lookup"><span data-stu-id="7e52e-164">For this example to work, the application must have a string named `Message` in its resource file, and the application should have the French-culture version of that resource file, Resources.fr-FR.resx.</span></span> <span data-ttu-id="7e52e-165">有关详细信息，请参阅[如何： 添加或删除资源](http://msdn.microsoft.com/en-us/7b77bc06-3952-4799-b029-def3f8f7f88d)。</span><span class="sxs-lookup"><span data-stu-id="7e52e-165">For more information, see [How to: Add or Remove Resources](http://msdn.microsoft.com/en-us/7b77bc06-3952-4799-b029-def3f8f7f88d).</span></span> <span data-ttu-id="7e52e-166">如果应用程序不具有资源文件中，法语区域性版本`My.Resource`对象将从默认区域性资源文件中检索资源。</span><span class="sxs-lookup"><span data-stu-id="7e52e-166">If the application does not have the French-culture version of the resource file, the `My.Resource` object retrieves the resource from the default-culture resource file.</span></span>  
  
 [!code-vb[VbVbalrMyResources#10](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-resources-object_5.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="7e52e-167">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7e52e-167">See Also</span></span>  
 [<span data-ttu-id="7e52e-168">如何：添加或删除资源</span><span class="sxs-lookup"><span data-stu-id="7e52e-168">How to: Add or Remove Resources</span></span>](http://msdn.microsoft.com/en-us/7b77bc06-3952-4799-b029-def3f8f7f88d)  
 [<span data-ttu-id="7e52e-169">管理应用程序资源 (.NET)</span><span class="sxs-lookup"><span data-stu-id="7e52e-169">Managing Application Resources (.NET)</span></span>](/visualstudio/ide/managing-application-resources-dotnet)  
 [<span data-ttu-id="7e52e-170">桌面应用中的资源</span><span class="sxs-lookup"><span data-stu-id="7e52e-170">Resources in Desktop Apps</span></span>](../../../framework/resources/index.md)  
 [<span data-ttu-id="7e52e-171">演练： 本地化 Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="7e52e-171">Walkthrough: Localizing Windows Forms</span></span>](http://msdn.microsoft.com/en-us/9a96220d-a19b-4de0-9f48-01e5d82679e5)
