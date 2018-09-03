---
title: 打包和部署自定义 My 扩展 (Visual Basic)
ms.date: 08/14/2018
helpviewer_keywords:
- My namespace [Visual Basic], customizing
- My namespace
- My namespace [Visual Basic], extending
ms.assetid: fd89c54b-0290-4c50-95a3-ff17d4487a21
ms.openlocfilehash: 4212f58c39f63be6ba20c3b79e5d9c98d0615c5e
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/03/2018
ms.locfileid: "43487151"
---
# <a name="package-and-deploy-custom-my-extensions-visual-basic"></a><span data-ttu-id="b5096-102">打包和部署自定义 My 扩展 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b5096-102">Package and deploy custom My extensions (Visual Basic)</span></span>

<span data-ttu-id="b5096-103">Visual Basic 提供了用于轻松对你可以部署您的自定义`My`通过使用 Visual Studio 模板的命名空间扩展。</span><span class="sxs-lookup"><span data-stu-id="b5096-103">Visual Basic provides an easy way for you to deploy your custom `My` namespace extensions by using Visual Studio templates.</span></span> <span data-ttu-id="b5096-104">如果要为其创建的项目模板在`My`扩展新的项目类型的重要组成部分，您只需包含您的自定义`My`项目导出模板时使用的扩展插件代码。</span><span class="sxs-lookup"><span data-stu-id="b5096-104">If you are creating a project template for which your `My` extensions are an integral part of the new project type, you can just include your custom `My` extension code with the project when you export the template.</span></span> <span data-ttu-id="b5096-105">有关导出项目模板的详细信息，请参阅[如何： 创建项目模板](/visualstudio/ide/how-to-create-project-templates)。</span><span class="sxs-lookup"><span data-stu-id="b5096-105">For more information about exporting project templates, see [How to: Create Project Templates](/visualstudio/ide/how-to-create-project-templates).</span></span>

<span data-ttu-id="b5096-106">如果您的自定义`My`扩展在单个代码文件中，你可以将文件导出为用户可添加到任何类型的 Visual Basic 项目项模板。</span><span class="sxs-lookup"><span data-stu-id="b5096-106">If your custom `My` extension is in a single code file, you can export the file as an item template that users can add to any type of Visual Basic project.</span></span> <span data-ttu-id="b5096-107">然后可以自定义项模板以启用其他功能和您的自定义行为`My`Visual Basic 项目中的扩展。</span><span class="sxs-lookup"><span data-stu-id="b5096-107">You can then customize the item template to enable additional capabilities and behavior for your custom `My` extension in a Visual Basic project.</span></span> <span data-ttu-id="b5096-108">这些功能包括：</span><span class="sxs-lookup"><span data-stu-id="b5096-108">Those capabilities include the following:</span></span>

- <span data-ttu-id="b5096-109">允许用户管理您的自定义`My`从扩展**My 扩展**Visual Basic 项目设计器页。</span><span class="sxs-lookup"><span data-stu-id="b5096-109">Allowing users to manage your custom `My` extension from the **My Extensions** page of the Visual Basic Project Designer.</span></span>

- <span data-ttu-id="b5096-110">自动添加您的自定义`My`扩展时指定的程序集的引用添加到项目。</span><span class="sxs-lookup"><span data-stu-id="b5096-110">Automatically adding your custom `My` extension when a reference to a specified assembly is added to a project.</span></span>

- <span data-ttu-id="b5096-111">隐藏`My`扩展中的项模板**添加项**对话框中，以便它不包含在项目项的列表。</span><span class="sxs-lookup"><span data-stu-id="b5096-111">Hiding the `My` extension item template in the **Add Item** dialog box so that it is not included in the list of project items.</span></span>

<span data-ttu-id="b5096-112">本主题讨论如何打包自定义`My`为隐藏的项模板，以便可以从管理扩展**My 扩展**Visual Basic 项目设计器页。</span><span class="sxs-lookup"><span data-stu-id="b5096-112">This topic discusses how to package a custom `My` extension as a hidden item template that can be managed from the **My Extensions** page of the Visual Basic Project Designer.</span></span> <span data-ttu-id="b5096-113">自定义`My`对指定的程序集的引用添加到项目时，扩展可以还会自动添加。</span><span class="sxs-lookup"><span data-stu-id="b5096-113">The custom `My` extension can also be added automatically when a reference to a specified assembly is added to a project.</span></span>

## <a name="create-a-my-namespace-extension"></a><span data-ttu-id="b5096-114">创建 My namespace 扩展</span><span class="sxs-lookup"><span data-stu-id="b5096-114">Create a My namespace extension</span></span>

<span data-ttu-id="b5096-115">创建自定义的部署包的第一步`My`扩展是创建为单个代码文件扩展名。</span><span class="sxs-lookup"><span data-stu-id="b5096-115">The first step in creating a deployment package for a custom `My` extension is to create the extension as a single code file.</span></span> <span data-ttu-id="b5096-116">有关详细信息和有关如何创建自定义指南`My`扩展，请参阅[扩展在 Visual Basic 中的 My Namespace](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md)。</span><span class="sxs-lookup"><span data-stu-id="b5096-116">For details and guidance about how to create a custom `My` extension, see [Extending the My Namespace in Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md).</span></span>

## <a name="export-a-my-namespace-extension-as-an-item-template"></a><span data-ttu-id="b5096-117">导出为项模板的 My namespace 扩展</span><span class="sxs-lookup"><span data-stu-id="b5096-117">Export a My namespace extension as an item template</span></span>

<span data-ttu-id="b5096-118">有一个文件，其中包括后你`My`命名空间扩展可以将代码文件导出为 Visual Studio 项模板。</span><span class="sxs-lookup"><span data-stu-id="b5096-118">After you have a code file that includes your `My` namespace extension, you can export the code file as a Visual Studio item template.</span></span> <span data-ttu-id="b5096-119">有关如何将文件导出为 Visual Studio 项模板的说明，请参阅[如何： 创建项模板](/visualstudio/ide/how-to-create-item-templates)。</span><span class="sxs-lookup"><span data-stu-id="b5096-119">For instructions on how to export a file as a Visual Studio item template, see [How to: Create Item Templates](/visualstudio/ide/how-to-create-item-templates).</span></span>

> [!NOTE]
> <span data-ttu-id="b5096-120">如果你`My`命名空间扩展具有特定的程序集的依赖项，则可以自定义项模板以自动安装在`My`命名空间扩展添加到该程序集的引用时。</span><span class="sxs-lookup"><span data-stu-id="b5096-120">If your `My` namespace extension has a dependency on a particular assembly, you can customize your item template to automatically install your `My` namespace extension when a reference to that assembly is added.</span></span> <span data-ttu-id="b5096-121">因此，想要排除该程序集引用时将代码文件导出为 Visual Studio 项模板。</span><span class="sxs-lookup"><span data-stu-id="b5096-121">As a result, you will want to exclude that assembly reference when you export the code file as a Visual Studio item template.</span></span>

## <a name="customize-the-item-template"></a><span data-ttu-id="b5096-122">自定义项模板</span><span class="sxs-lookup"><span data-stu-id="b5096-122">Customize the item template</span></span>

<span data-ttu-id="b5096-123">可以让您从管理的项模板**My 扩展**Visual Basic 项目设计器页。</span><span class="sxs-lookup"><span data-stu-id="b5096-123">You can enable your item template to be managed from the **My Extensions** page of the Visual Basic Project Designer.</span></span> <span data-ttu-id="b5096-124">此外可以启用要指定程序集的引用添加到项目时自动添加的项模板。</span><span class="sxs-lookup"><span data-stu-id="b5096-124">You can also enable the item template to be added automatically when a reference to a specified assembly is added to a project.</span></span> <span data-ttu-id="b5096-125">若要启用这些自定义，将添加一个新文件，称为 CustomData 文件，为你的模板，然后将新元素添加到 XML，在.vstemplate 文件中。</span><span class="sxs-lookup"><span data-stu-id="b5096-125">To enable these customizations, you will add a new file, called the CustomData file, to your template, and then add a new element to the XML in your .vstemplate file.</span></span>

### <a name="add-the-customdata-file"></a><span data-ttu-id="b5096-126">添加 CustomData 文件</span><span class="sxs-lookup"><span data-stu-id="b5096-126">Add the CustomData file</span></span>

<span data-ttu-id="b5096-127">CustomData 文件是具有文件扩展名的文本文件。CustomData （文件名称可以设置为任何值到你的模板有意义） 和包含的 XML。</span><span class="sxs-lookup"><span data-stu-id="b5096-127">The CustomData file is a text file that has a file name extension of .CustomData (the file name can be set to any value meaningful to your template) and that contains XML.</span></span> <span data-ttu-id="b5096-128">CustomData 文件中的 XML 指示 Visual Basic 包括你`My`扩展用户使用时**My 扩展**Visual Basic 项目设计器页。</span><span class="sxs-lookup"><span data-stu-id="b5096-128">The XML in the CustomData file instructs Visual Basic to include your `My` extension when users use the **My Extensions** page of the Visual Basic Project Designer.</span></span> <span data-ttu-id="b5096-129">你可以选择添加 <`AssemblyFullName>`到 CustomData 文件 XML 属性。</span><span class="sxs-lookup"><span data-stu-id="b5096-129">You can optionally add the <`AssemblyFullName>` attribute to your CustomData file XML.</span></span> <span data-ttu-id="b5096-130">这会指示 Visual Basic 会自动安装您的自定义`My`扩展时对特定的程序集的引用添加到项目。</span><span class="sxs-lookup"><span data-stu-id="b5096-130">This instructs Visual Basic to automatically install your custom `My` extension when a reference to a particular assembly is added to the project.</span></span> <span data-ttu-id="b5096-131">可以使用任何文本编辑器或 XML 编辑器来创建 CustomData 文件，然后将其添加到项模板的压缩的文件夹 （.zip 文件）。</span><span class="sxs-lookup"><span data-stu-id="b5096-131">You can use any text editor or XML editor to create the CustomData file, and then add it to your item template's compressed folder (.zip file).</span></span>

<span data-ttu-id="b5096-132">例如，以下 XML 显示了 CustomData 文件，会将模板项添加到 Visual Basic 项目时 Microsoft.VisualBasic.PowerPacks.Vs.dll 程序集的引用的 My 扩展文件夹的内容添加到项目。</span><span class="sxs-lookup"><span data-stu-id="b5096-132">For example, the following XML shows the contents of a CustomData file that will add the template item to the My Extensions folder of a Visual Basic project when a reference to the Microsoft.VisualBasic.PowerPacks.Vs.dll assembly is added to the project.</span></span>

```xml
<VBMyExtensionTemplate
    ID="Microsoft.VisualBasic.Samples.MyExtensions.MyPrinterInfo"
    Version="1.0.0.0"
    AssemblyFullName="Microsoft.VisualBasic.PowerPacks.vs"
/>
```

<span data-ttu-id="b5096-133">CustomData 文件包含 <`VBMyExtensionTemplate>`具有属性，如以下表中列出的元素。</span><span class="sxs-lookup"><span data-stu-id="b5096-133">The CustomData file contains a <`VBMyExtensionTemplate>` element that has attributes as listed in the following table.</span></span>

|<span data-ttu-id="b5096-134">特性</span><span class="sxs-lookup"><span data-stu-id="b5096-134">Attribute</span></span>|<span data-ttu-id="b5096-135">描述</span><span class="sxs-lookup"><span data-stu-id="b5096-135">Description</span></span>|
|---|---|
|`ID`|<span data-ttu-id="b5096-136">必须的。</span><span class="sxs-lookup"><span data-stu-id="b5096-136">Required.</span></span> <span data-ttu-id="b5096-137">扩展的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="b5096-137">A unique identifier for the extension.</span></span> <span data-ttu-id="b5096-138">如果具有此 ID 的扩展已添加到项目中，不会提示用户重新添加它。</span><span class="sxs-lookup"><span data-stu-id="b5096-138">If the extension that has this ID has already been added to the project, the user will not be prompted to add it again.</span></span>|
|`Version`|<span data-ttu-id="b5096-139">必须的。</span><span class="sxs-lookup"><span data-stu-id="b5096-139">Required.</span></span> <span data-ttu-id="b5096-140">在项模板的版本号。</span><span class="sxs-lookup"><span data-stu-id="b5096-140">A version number for the item template.</span></span>|
|`AssemblyFullName`|<span data-ttu-id="b5096-141">可选。</span><span class="sxs-lookup"><span data-stu-id="b5096-141">Optional.</span></span> <span data-ttu-id="b5096-142">程序集名称。</span><span class="sxs-lookup"><span data-stu-id="b5096-142">An assembly name.</span></span> <span data-ttu-id="b5096-143">当此程序集的引用添加到项目中时，将提示用户添加`My`从此项模板的扩展。</span><span class="sxs-lookup"><span data-stu-id="b5096-143">When a reference to this assembly is added to the project, the user will be prompted to add the `My` extension from this item template.</span></span>|

### <a name="add-the-customdatasignature-element-to-the-vstemplate-file"></a><span data-ttu-id="b5096-144">添加\<CustomDataSignature > 元素的.vstemplate 文件</span><span class="sxs-lookup"><span data-stu-id="b5096-144">Add the \<CustomDataSignature> element to the .vstemplate file</span></span>

<span data-ttu-id="b5096-145">若要确定 Visual Studio 项模板`My`命名空间扩展必须还修改您的项模板的.vstemplate 文件。</span><span class="sxs-lookup"><span data-stu-id="b5096-145">To identify your Visual Studio item template as a `My` namespace extension, you must also modify the .vstemplate file for your item template.</span></span> <span data-ttu-id="b5096-146">必须添加`<CustomDataSignature>`元素`<TemplateData>`元素。</span><span class="sxs-lookup"><span data-stu-id="b5096-146">You must add a `<CustomDataSignature>` element to the `<TemplateData>` element.</span></span> <span data-ttu-id="b5096-147">`<CustomDataSignature>`元素必须包含文本`Microsoft.VisualBasic.MyExtension`，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="b5096-147">The `<CustomDataSignature>` element must contain the text `Microsoft.VisualBasic.MyExtension`, as shown in the following example.</span></span>

```xml
<CustomDataSignature>Microsoft.VisualBasic.MyExtension</CustomDataSignature>
```

<span data-ttu-id="b5096-148">不能直接修改压缩的文件夹 （.zip 文件） 中的文件。</span><span class="sxs-lookup"><span data-stu-id="b5096-148">You cannot modify files in a compressed folder (.zip file) directly.</span></span> <span data-ttu-id="b5096-149">必须将.vstemplate 文件从压缩文件夹复制、 对其进行修改和已更新副本替换将压缩的文件夹中的.vstemplate 文件。</span><span class="sxs-lookup"><span data-stu-id="b5096-149">You must copy the .vstemplate file from the compressed folder, modify it, and then replace the .vstemplate file in the compressed folder with your updated copy.</span></span>

<span data-ttu-id="b5096-150">下面的示例显示了具有的.vstemplate 文件的内容`<CustomDataSignature>`添加元素。</span><span class="sxs-lookup"><span data-stu-id="b5096-150">The following example shows the contents of a .vstemplate file that has the `<CustomDataSignature>` element added.</span></span>

```xml
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

## <a name="install-the-template"></a><span data-ttu-id="b5096-151">安装模板</span><span class="sxs-lookup"><span data-stu-id="b5096-151">Install the template</span></span>

<span data-ttu-id="b5096-152">若要安装此模板，您可以复制将压缩的文件夹 (*.zip*文件) 的 Visual Basic 项模板文件夹。</span><span class="sxs-lookup"><span data-stu-id="b5096-152">To install the template, you can copy the compressed folder (*.zip* file) to the Visual Basic item templates folder.</span></span> <span data-ttu-id="b5096-153">默认情况下，用户项模板都位于 *%USERPROFILE%\Documents\Visual Studio\<版本\>\Templates\ItemTemplates\Visual Basic*。</span><span class="sxs-lookup"><span data-stu-id="b5096-153">By default, user item templates are located in *%USERPROFILE%\Documents\Visual Studio \<Version\>\Templates\ItemTemplates\Visual Basic*.</span></span> <span data-ttu-id="b5096-154">另外，您可以发布模板为 Visual Studio 安装程序 (*.vsi*) 文件。</span><span class="sxs-lookup"><span data-stu-id="b5096-154">Alternatively, you can publish the template as a Visual Studio Installer (*.vsi*) file.</span></span>

## <a name="see-also"></a><span data-ttu-id="b5096-155">请参阅</span><span class="sxs-lookup"><span data-stu-id="b5096-155">See also</span></span>

- [<span data-ttu-id="b5096-156">扩展 Visual Basic 中的 My 命名空间</span><span class="sxs-lookup"><span data-stu-id="b5096-156">Extending the My Namespace in Visual Basic</span></span>](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md)
- [<span data-ttu-id="b5096-157">扩展 Visual Basic 应用程序模型</span><span class="sxs-lookup"><span data-stu-id="b5096-157">Extending the Visual Basic Application Model</span></span>](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-visual-basic-application-model.md)
- [<span data-ttu-id="b5096-158">自定义 My 中可用的对象</span><span class="sxs-lookup"><span data-stu-id="b5096-158">Customizing Which Objects are Available in My</span></span>](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)
- [<span data-ttu-id="b5096-159">“项目设计器”->“My 扩展”页</span><span class="sxs-lookup"><span data-stu-id="b5096-159">My Extensions Page, Project Designer</span></span>](/visualstudio/ide/reference/my-extensions-page-project-designer-visual-basic)
