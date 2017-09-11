---
title: "打包和部署自定义 My 扩展 (Visual Basic 中) |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- My namespace, customizing
- My namespace
- My namespace, extending
ms.assetid: fd89c54b-0290-4c50-95a3-ff17d4487a21
caps.latest.revision: 10
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
ms.openlocfilehash: 81483722227873d1b145219ae5c4326d841ff876
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="packaging-and-deploying-custom-my-extensions-visual-basic"></a><span data-ttu-id="ac5dc-102">打包和部署自定义 My 扩展 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ac5dc-102">Packaging and deploying custom My extensions (Visual Basic)</span></span>
<span data-ttu-id="ac5dc-103">Visual Basic 提供了用于轻松对您要部署您的自定义`My`通过使用 Visual Studio 模板的命名空间扩展。</span><span class="sxs-lookup"><span data-stu-id="ac5dc-103">Visual Basic provides an easy way for you to deploy your custom `My` namespace extensions by using Visual Studio templates.</span></span> <span data-ttu-id="ac5dc-104">如果要为其创建项目模板您`My`扩展新的项目类型的组成部分，您只需包含您的自定义`My`扩展代码包括在导出模板时的项目。</span><span class="sxs-lookup"><span data-stu-id="ac5dc-104">If you are creating a project template for which your `My` extensions are an integral part of the new project type, you can just include your custom `My` extension code with the project when you export the template.</span></span> <span data-ttu-id="ac5dc-105">有关导出项目模板的详细信息，请参阅[如何︰ 创建项目模板](http://msdn.microsoft.com/library/a1a6999d-a34c-48a8-b1cf-027eb5c76398)。</span><span class="sxs-lookup"><span data-stu-id="ac5dc-105">For more information about exporting project templates, see [How to: Create Project Templates](http://msdn.microsoft.com/library/a1a6999d-a34c-48a8-b1cf-027eb5c76398).</span></span>  
  
 <span data-ttu-id="ac5dc-106">如果您的自定义`My`扩展在单个代码文件中，可以将文件导出为项模板，用户可添加到任何类型的 Visual Basic 项目。</span><span class="sxs-lookup"><span data-stu-id="ac5dc-106">If your custom `My` extension is in a single code file, you can export the file as an item template that users can add to any type of Visual Basic project.</span></span> <span data-ttu-id="ac5dc-107">然后可以自定义项模板以启用其他功能和您的自定义行为`My`Visual Basic 项目中的扩展。</span><span class="sxs-lookup"><span data-stu-id="ac5dc-107">You can then customize the item template to enable additional capabilities and behavior for your custom `My` extension in a Visual Basic project.</span></span> <span data-ttu-id="ac5dc-108">这些功能包括︰</span><span class="sxs-lookup"><span data-stu-id="ac5dc-108">Those capabilities include the following:</span></span>  
  
-   <span data-ttu-id="ac5dc-109">允许用户管理您的自定义`My`扩展名从**My 扩展**Visual Basic 项目设计器的页面。</span><span class="sxs-lookup"><span data-stu-id="ac5dc-109">Allowing users to manage your custom `My` extension from the **My Extensions** page of the Visual Basic Project Designer.</span></span>  
  
-   <span data-ttu-id="ac5dc-110">自动将其添加您的自定义`My`扩展时指定的程序集的引用添加到项目。</span><span class="sxs-lookup"><span data-stu-id="ac5dc-110">Automatically adding your custom `My` extension when a reference to a specified assembly is added to a project.</span></span>  
  
-   <span data-ttu-id="ac5dc-111">隐藏`My`扩展中的项模板**添加项**对话框中，以便不将其包含在项目项的列表。</span><span class="sxs-lookup"><span data-stu-id="ac5dc-111">Hiding the `My` extension item template in the **Add Item** dialog box so that it is not included in the list of project items.</span></span>  
  
 <span data-ttu-id="ac5dc-112">本主题讨论如何打包自定义`My`扩展为隐藏的项模板，以便可以从管理**My 扩展**Visual Basic 项目设计器的页面。</span><span class="sxs-lookup"><span data-stu-id="ac5dc-112">This topic discusses how to package a custom `My` extension as a hidden item template that can be managed from the **My Extensions** page of the Visual Basic Project Designer.</span></span> <span data-ttu-id="ac5dc-113">自定义`My`扩展也可以添加自动对指定的程序集的引用添加到项目时。</span><span class="sxs-lookup"><span data-stu-id="ac5dc-113">The custom `My` extension can also be added automatically when a reference to a specified assembly is added to a project.</span></span>  
  
## <a name="create-a-my-namespace-extension"></a><span data-ttu-id="ac5dc-114">创建 My 命名空间扩展</span><span class="sxs-lookup"><span data-stu-id="ac5dc-114">Create a My namespace extension</span></span>  
 <span data-ttu-id="ac5dc-115">创建一个自定义的部署包的第一步`My`扩展是扩展为单个代码文件创建。</span><span class="sxs-lookup"><span data-stu-id="ac5dc-115">The first step in creating a deployment package for a custom `My` extension is to create the extension as a single code file.</span></span> <span data-ttu-id="ac5dc-116">有关详细信息和有关如何创建自定义指导`My`扩展，请参阅[扩展在 Visual Basic My Namespace](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md)。</span><span class="sxs-lookup"><span data-stu-id="ac5dc-116">For details and guidance about how to create a custom `My` extension, see [Extending the My Namespace in Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md).</span></span>  
  
## <a name="export-a-my-namespace-extension-as-an-item-template"></a><span data-ttu-id="ac5dc-117">导出为项模板的 My 命名空间扩展</span><span class="sxs-lookup"><span data-stu-id="ac5dc-117">Export a My namespace extension as an item template</span></span>  
 <span data-ttu-id="ac5dc-118">包括一个代码文件之后您`My`命名空间扩展，可以将代码文件导出为 Visual Studio 项模板。</span><span class="sxs-lookup"><span data-stu-id="ac5dc-118">After you have a code file that includes your `My` namespace extension, you can export the code file as a Visual Studio item template.</span></span> <span data-ttu-id="ac5dc-119">有关如何将文件导出为 Visual Studio 项模板的说明，请参阅[如何︰ 创建项模板](http://msdn.microsoft.com/library/77bc53d4-d607-4820-a032-7e3b365891b5)。</span><span class="sxs-lookup"><span data-stu-id="ac5dc-119">For instructions on how to export a file as a Visual Studio item template, see [How to: Create Item Templates](http://msdn.microsoft.com/library/77bc53d4-d607-4820-a032-7e3b365891b5).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ac5dc-120">如果您`My`命名空间扩展程序依赖于特定程序集，您可以自定义项模板，从而自动安装您`My`命名空间扩展添加到该程序集的引用时。</span><span class="sxs-lookup"><span data-stu-id="ac5dc-120">If your `My` namespace extension has a dependency on a particular assembly, you can customize your item template to automatically install your `My` namespace extension when a reference to that assembly is added.</span></span> <span data-ttu-id="ac5dc-121">因此，想要排除该程序集引用的代码文件导出为 Visual Studio 项模板时。</span><span class="sxs-lookup"><span data-stu-id="ac5dc-121">As a result, you will want to exclude that assembly reference when you export the code file as a Visual Studio item template.</span></span>  
  
## <a name="customize-the-item-template"></a><span data-ttu-id="ac5dc-122">自定义项模板</span><span class="sxs-lookup"><span data-stu-id="ac5dc-122">Customize the item template</span></span>  
 <span data-ttu-id="ac5dc-123">您可以启用项模板，从而从管理**My 扩展**Visual Basic 项目设计器的页面。</span><span class="sxs-lookup"><span data-stu-id="ac5dc-123">You can enable your item template to be managed from the **My Extensions** page of the Visual Basic Project Designer.</span></span> <span data-ttu-id="ac5dc-124">此外可以启用对指定的程序集的引用添加到项目时自动添加的项目模板。</span><span class="sxs-lookup"><span data-stu-id="ac5dc-124">You can also enable the item template to be added automatically when a reference to a specified assembly is added to a project.</span></span> <span data-ttu-id="ac5dc-125">若要启用这些自定义设置，将添加一个新文件，称为 CustomData 文件，为您的模板，然后将新元素添加到 XML，.vstemplate 文件中。</span><span class="sxs-lookup"><span data-stu-id="ac5dc-125">To enable these customizations, you will add a new file, called the CustomData file, to your template, and then add a new element to the XML in your .vstemplate file.</span></span>  
  
### <a name="add-the-customdata-file"></a><span data-ttu-id="ac5dc-126">添加 CustomData 文件</span><span class="sxs-lookup"><span data-stu-id="ac5dc-126">Add the CustomData file</span></span>  
 <span data-ttu-id="ac5dc-127">CustomData 文件是扩展名为文件的文本文件。CustomData （文件名可以设置为任何值对您的模板有意义） 和包含的 XML。</span><span class="sxs-lookup"><span data-stu-id="ac5dc-127">The CustomData file is a text file that has a file name extension of .CustomData (the file name can be set to any value meaningful to your template) and that contains XML.</span></span> <span data-ttu-id="ac5dc-128">CustomData 文件中的 XML 指示 Visual Basic 中包括您`My`扩展插件在用户使用时**My 扩展**Visual Basic 项目设计器的页面。</span><span class="sxs-lookup"><span data-stu-id="ac5dc-128">The XML in the CustomData file instructs Visual Basic to include your `My` extension when users use the **My Extensions** page of the Visual Basic Project Designer.</span></span> <span data-ttu-id="ac5dc-129">您可以选择添加`AssemblyFullName>`到 CustomData 文件 XML 属性。</span><span class="sxs-lookup"><span data-stu-id="ac5dc-129">You can optionally add the <`AssemblyFullName>` attribute to your CustomData file XML.</span></span> <span data-ttu-id="ac5dc-130">这将指示 Visual Basic 中自动安装您的自定义`My`扩展时对特定的程序集的引用添加到项目。</span><span class="sxs-lookup"><span data-stu-id="ac5dc-130">This instructs Visual Basic to automatically install your custom `My` extension when a reference to a particular assembly is added to the project.</span></span> <span data-ttu-id="ac5dc-131">可以使用任何文本编辑器或 XML 编辑器创建 CustomData 文件，并将其添加到您的项模板的压缩文件夹 （.zip 文件）。</span><span class="sxs-lookup"><span data-stu-id="ac5dc-131">You can use any text editor or XML editor to create the CustomData file, and then add it to your item template's compressed folder (.zip file).</span></span>  
  
 <span data-ttu-id="ac5dc-132">例如，以下 XML 显示 CustomData 文件将添加到 Visual Basic 项目对 Microsoft.VisualBasic.PowerPacks.Vs.dll 程序集的引用时的 My 扩展文件夹的模板项的内容添加到项目。</span><span class="sxs-lookup"><span data-stu-id="ac5dc-132">For example, the following XML shows the contents of a CustomData file that will add the template item to the My Extensions folder of a Visual Basic project when a reference to the Microsoft.VisualBasic.PowerPacks.Vs.dll assembly is added to the project.</span></span>  
  
```  
<VBMyExtensionTemplate   
    ID="Microsoft.VisualBasic.Samples.MyExtensions.MyPrinterInfo"   
    Version="1.0.0.0"  
    AssemblyFullName="Microsoft.VisualBasic.PowerPacks.vs"  
/>  
```  
  
 <span data-ttu-id="ac5dc-133">CustomData 文件包含`VBMyExtensionTemplate>`具有属性，如下面的表中列出的元素。</span><span class="sxs-lookup"><span data-stu-id="ac5dc-133">The CustomData file contains a <`VBMyExtensionTemplate>` element that has attributes as listed in the following table.</span></span>  
  
|<span data-ttu-id="ac5dc-134">特性</span><span class="sxs-lookup"><span data-stu-id="ac5dc-134">Attribute</span></span>|<span data-ttu-id="ac5dc-135">说明</span><span class="sxs-lookup"><span data-stu-id="ac5dc-135">Description</span></span>|  
|---|---|  
|`ID`|<span data-ttu-id="ac5dc-136">必需。</span><span class="sxs-lookup"><span data-stu-id="ac5dc-136">Required.</span></span> <span data-ttu-id="ac5dc-137">扩展的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="ac5dc-137">A unique identifier for the extension.</span></span> <span data-ttu-id="ac5dc-138">如果已将具有此 ID 的扩展添加到项目中，不会提示用户重新添加它。</span><span class="sxs-lookup"><span data-stu-id="ac5dc-138">If the extension that has this ID has already been added to the project, the user will not be prompted to add it again.</span></span>|  
|`Version`|<span data-ttu-id="ac5dc-139">必需。</span><span class="sxs-lookup"><span data-stu-id="ac5dc-139">Required.</span></span> <span data-ttu-id="ac5dc-140">在项模板的版本号。</span><span class="sxs-lookup"><span data-stu-id="ac5dc-140">A version number for the item template.</span></span>|  
|`AssemblyFullName`|<span data-ttu-id="ac5dc-141">可选。</span><span class="sxs-lookup"><span data-stu-id="ac5dc-141">Optional.</span></span> <span data-ttu-id="ac5dc-142">程序集名称。</span><span class="sxs-lookup"><span data-stu-id="ac5dc-142">An assembly name.</span></span> <span data-ttu-id="ac5dc-143">当此程序集的引用添加到项目中时，将提示用户添加`My`扩展名从这个项模板。</span><span class="sxs-lookup"><span data-stu-id="ac5dc-143">When a reference to this assembly is added to the project, the user will be prompted to add the `My` extension from this item template.</span></span>|  
  
### <a name="add-the-customdatasignature-element-to-the-vstemplate-file"></a><span data-ttu-id="ac5dc-144">添加\<CustomDataSignature&1;> 的.vstemplate 文件的元素</span><span class="sxs-lookup"><span data-stu-id="ac5dc-144">Add the \<CustomDataSignature> element to the .vstemplate file</span></span>  
 <span data-ttu-id="ac5dc-145">若要确定您的 Visual Studio 项模板作为`My`命名空间扩展必须还修改您的项模板的.vstemplate 文件。</span><span class="sxs-lookup"><span data-stu-id="ac5dc-145">To identify your Visual Studio item template as a `My` namespace extension, you must also modify the .vstemplate file for your item template.</span></span> <span data-ttu-id="ac5dc-146">您必须添加`<CustomDataSignature>`元素`<TemplateData>`元素。</span><span class="sxs-lookup"><span data-stu-id="ac5dc-146">You must add a `<CustomDataSignature>` element to the `<TemplateData>` element.</span></span> <span data-ttu-id="ac5dc-147">`<CustomDataSignature>`元素必须包含文本`Microsoft.VisualBasic.MyExtension`，如在下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="ac5dc-147">The `<CustomDataSignature>` element must contain the text `Microsoft.VisualBasic.MyExtension`, as shown in the following example.</span></span>  
  
```  
<CustomDataSignature>Microsoft.VisualBasic.MyExtension</CustomDataSignature>  
```  
  
 <span data-ttu-id="ac5dc-148">您不能直接修改压缩文件夹 （.zip 文件） 中的文件。</span><span class="sxs-lookup"><span data-stu-id="ac5dc-148">You cannot modify files in a compressed folder (.zip file) directly.</span></span> <span data-ttu-id="ac5dc-149">必须从压缩文件夹中复制的.vstemplate 文件、 对其进行修改并更新副本替换该压缩文件夹中的.vstemplate 文件。</span><span class="sxs-lookup"><span data-stu-id="ac5dc-149">You must copy the .vstemplate file from the compressed folder, modify it, and then replace the .vstemplate file in the compressed folder with your updated copy.</span></span>  
  
 <span data-ttu-id="ac5dc-150">下面的示例演示一个具有的.vstemplate 文件的内容`<CustomDataSignature>`添加元素。</span><span class="sxs-lookup"><span data-stu-id="ac5dc-150">The following example shows the contents of a .vstemplate file that has the `<CustomDataSignature>` element added.</span></span>  
  
```  
<VSTemplate Version="2.0.0" xmlns="http://schemas.microsoft.com/developer/vstemplate/2005" Type="Item">  
  <TemplateData>  
    <DefaultName>MyCustomExtensionModule.vb</DefaultName>  
    <Name>MyPrinterInfo</Name>  
    <Description>Custom My Extensions Item Template</Description>  
    <ProjectType>VisualBasic</ProjectType>  
    <SortOrder>10</SortOrder>  
    <Icon>__TemplateIcon.ico</Icon>  
    <CustomDataSignature      >Microsoft.VisualBasic.MyExtension</CustomDataSignature>  
  </TemplateData>  
  <TemplateContent>  
    <References />  
    <ProjectItem SubType="Code"   
                 TargetFileName="$fileinputname$.vb"  
                 ReplaceParameters="true"  
     >MyCustomExtensionModule.vb</ProjectItem>  
  </TemplateContent>  
</VSTemplate>  
```  
  
## <a name="install-the-template"></a><span data-ttu-id="ac5dc-151">安装此模板</span><span class="sxs-lookup"><span data-stu-id="ac5dc-151">Install the template</span></span>  
 <span data-ttu-id="ac5dc-152">若要安装此模板，可以将压缩的文件夹 （.zip 文件） 复制到 Visual Basic 项目模板文件夹 （例如，My Documents\Visual Studio 2008\Templates\Item Templates\Visual 基本）。</span><span class="sxs-lookup"><span data-stu-id="ac5dc-152">To install the template, you can copy the compressed folder (.zip file) to the Visual Basic item templates folder (for example, My Documents\Visual Studio 2008\Templates\Item Templates\Visual Basic).</span></span> <span data-ttu-id="ac5dc-153">或者，您可以为 Visual Studio 安装程序 (.vsi) 文件发布模板。</span><span class="sxs-lookup"><span data-stu-id="ac5dc-153">Alternatively, you can publish the template as a Visual Studio Installer (.vsi) file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac5dc-154">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ac5dc-154">See also</span></span>  
 <span data-ttu-id="ac5dc-155">[扩展 Visual Basic 中的 My 命名空间](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md) </span><span class="sxs-lookup"><span data-stu-id="ac5dc-155">[Extending the My Namespace in Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md) </span></span>  
<span data-ttu-id="ac5dc-156"> [扩展 Visual Basic 应用程序模型](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-visual-basic-application-model.md) </span><span class="sxs-lookup"><span data-stu-id="ac5dc-156"> [Extending the Visual Basic Application Model](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-visual-basic-application-model.md) </span></span>  
<span data-ttu-id="ac5dc-157"> [自定义的对象都将在我](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md) </span><span class="sxs-lookup"><span data-stu-id="ac5dc-157"> [Customizing Which Objects are Available in My](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md) </span></span>  
<span data-ttu-id="ac5dc-158"> [My 扩展页项目设计器](https://docs.microsoft.com/visualstudio/ide/reference/my-extensions-page-project-designer-visual-basic)</span><span class="sxs-lookup"><span data-stu-id="ac5dc-158"> [My Extensions Page, Project Designer](https://docs.microsoft.com/visualstudio/ide/reference/my-extensions-page-project-designer-visual-basic)</span></span>
