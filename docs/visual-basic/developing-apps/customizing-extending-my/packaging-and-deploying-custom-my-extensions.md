---
title: 打包和部署自定义 My 扩展 (Visual Basic)
ms.date: 08/14/2018
helpviewer_keywords:
- My namespace [Visual Basic], customizing
- My namespace
- My namespace [Visual Basic], extending
ms.assetid: fd89c54b-0290-4c50-95a3-ff17d4487a21
ms.openlocfilehash: 4212f58c39f63be6ba20c3b79e5d9c98d0615c5e
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2018
ms.locfileid: "44211770"
---
# <a name="package-and-deploy-custom-my-extensions-visual-basic"></a>打包和部署自定义 My 扩展 (Visual Basic)

Visual Basic 提供了用于轻松对你可以部署您的自定义`My`通过使用 Visual Studio 模板的命名空间扩展。 如果要为其创建的项目模板在`My`扩展新的项目类型的重要组成部分，您只需包含您的自定义`My`项目导出模板时使用的扩展插件代码。 有关导出项目模板的详细信息，请参阅[如何： 创建项目模板](/visualstudio/ide/how-to-create-project-templates)。

如果您的自定义`My`扩展在单个代码文件中，你可以将文件导出为用户可添加到任何类型的 Visual Basic 项目项模板。 然后可以自定义项模板以启用其他功能和您的自定义行为`My`Visual Basic 项目中的扩展。 这些功能包括：

- 允许用户管理您的自定义`My`从扩展**My 扩展**Visual Basic 项目设计器页。

- 自动添加您的自定义`My`扩展时指定的程序集的引用添加到项目。

- 隐藏`My`扩展中的项模板**添加项**对话框中，以便它不包含在项目项的列表。

本主题讨论如何打包自定义`My`为隐藏的项模板，以便可以从管理扩展**My 扩展**Visual Basic 项目设计器页。 自定义`My`对指定的程序集的引用添加到项目时，扩展可以还会自动添加。

## <a name="create-a-my-namespace-extension"></a>创建 My namespace 扩展

创建自定义的部署包的第一步`My`扩展是创建为单个代码文件扩展名。 有关详细信息和有关如何创建自定义指南`My`扩展，请参阅[扩展在 Visual Basic 中的 My Namespace](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md)。

## <a name="export-a-my-namespace-extension-as-an-item-template"></a>导出为项模板的 My namespace 扩展

有一个文件，其中包括后你`My`命名空间扩展可以将代码文件导出为 Visual Studio 项模板。 有关如何将文件导出为 Visual Studio 项模板的说明，请参阅[如何： 创建项模板](/visualstudio/ide/how-to-create-item-templates)。

> [!NOTE]
> 如果你`My`命名空间扩展具有特定的程序集的依赖项，则可以自定义项模板以自动安装在`My`命名空间扩展添加到该程序集的引用时。 因此，想要排除该程序集引用时将代码文件导出为 Visual Studio 项模板。

## <a name="customize-the-item-template"></a>自定义项模板

可以让您从管理的项模板**My 扩展**Visual Basic 项目设计器页。 此外可以启用要指定程序集的引用添加到项目时自动添加的项模板。 若要启用这些自定义，将添加一个新文件，称为 CustomData 文件，为你的模板，然后将新元素添加到 XML，在.vstemplate 文件中。

### <a name="add-the-customdata-file"></a>添加 CustomData 文件

CustomData 文件是具有文件扩展名的文本文件。CustomData （文件名称可以设置为任何值到你的模板有意义） 和包含的 XML。 CustomData 文件中的 XML 指示 Visual Basic 包括你`My`扩展用户使用时**My 扩展**Visual Basic 项目设计器页。 你可以选择添加 <`AssemblyFullName>`到 CustomData 文件 XML 属性。 这会指示 Visual Basic 会自动安装您的自定义`My`扩展时对特定的程序集的引用添加到项目。 可以使用任何文本编辑器或 XML 编辑器来创建 CustomData 文件，然后将其添加到项模板的压缩的文件夹 （.zip 文件）。

例如，以下 XML 显示了 CustomData 文件，会将模板项添加到 Visual Basic 项目时 Microsoft.VisualBasic.PowerPacks.Vs.dll 程序集的引用的 My 扩展文件夹的内容添加到项目。

```xml
<VBMyExtensionTemplate
    ID="Microsoft.VisualBasic.Samples.MyExtensions.MyPrinterInfo"
    Version="1.0.0.0"
    AssemblyFullName="Microsoft.VisualBasic.PowerPacks.vs"
/>
```

CustomData 文件包含 <`VBMyExtensionTemplate>`具有属性，如以下表中列出的元素。

|特性|描述|
|---|---|
|`ID`|必须的。 扩展的唯一标识符。 如果具有此 ID 的扩展已添加到项目中，不会提示用户重新添加它。|
|`Version`|必须的。 在项模板的版本号。|
|`AssemblyFullName`|可选。 程序集名称。 当此程序集的引用添加到项目中时，将提示用户添加`My`从此项模板的扩展。|

### <a name="add-the-customdatasignature-element-to-the-vstemplate-file"></a>添加\<CustomDataSignature > 元素的.vstemplate 文件

若要确定 Visual Studio 项模板`My`命名空间扩展必须还修改您的项模板的.vstemplate 文件。 必须添加`<CustomDataSignature>`元素`<TemplateData>`元素。 `<CustomDataSignature>`元素必须包含文本`Microsoft.VisualBasic.MyExtension`，如以下示例所示。

```xml
<CustomDataSignature>Microsoft.VisualBasic.MyExtension</CustomDataSignature>
```

不能直接修改压缩的文件夹 （.zip 文件） 中的文件。 必须将.vstemplate 文件从压缩文件夹复制、 对其进行修改和已更新副本替换将压缩的文件夹中的.vstemplate 文件。

下面的示例显示了具有的.vstemplate 文件的内容`<CustomDataSignature>`添加元素。

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

## <a name="install-the-template"></a>安装模板

若要安装此模板，您可以复制将压缩的文件夹 (*.zip*文件) 的 Visual Basic 项模板文件夹。 默认情况下，用户项模板都位于 *%USERPROFILE%\Documents\Visual Studio\<版本\>\Templates\ItemTemplates\Visual Basic*。 另外，您可以发布模板为 Visual Studio 安装程序 (*.vsi*) 文件。

## <a name="see-also"></a>请参阅

- [扩展 Visual Basic 中的 My 命名空间](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md)
- [扩展 Visual Basic 应用程序模型](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-visual-basic-application-model.md)
- [自定义 My 中可用的对象](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)
- [“项目设计器”->“My 扩展”页](/visualstudio/ide/reference/my-extensions-page-project-designer-visual-basic)
