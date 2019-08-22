---
title: 如何：使用设计器添加或移除 ImageList 图像
ms.date: 03/30/2017
helpviewer_keywords:
- ImageList component [Windows Forms], adding images
- ImageList component [Windows Forms], removing images
- images [Windows Forms], adding to ImageList component
ms.assetid: 5699b244-e37c-4d20-bc35-7441e55c1e3a
ms.openlocfilehash: be17d5e6a12824c1c9edc867c99e77a6a1437a36
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2019
ms.locfileid: "69658587"
---
# <a name="how-to-add-or-remove-imagelist-images-with-the-designer"></a>如何：使用设计器添加或移除 ImageList 图像

可以通过多种不同方式向<xref:System.Windows.Forms.ImageList>组件添加图像。 你可以通过使用与<xref:System.Windows.Forms.ImageList>关联的智能标记来非常快速地添加图像, 或者<xref:System.Windows.Forms.ImageList>, 如果你在上设置多个其他属性, 则可以更方便地使用属性窗口添加图像。 你还可以通过使用代码来添加映像。 有关如何添加包含代码的图像的详细信息, 请[参阅如何:添加或删除包含 Windows 窗体 ImageList 组件](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)的映像。 通常, 在<xref:System.Windows.Forms.ImageList>组件与控件关联之前, 使用图像填充组件, 但这不是必需的。

### <a name="to-add-or-remove-images-by-using-the-properties-window"></a>使用属性窗口添加或删除映像

1. <xref:System.Windows.Forms.ImageList>选择组件, 或将其添加到窗体。

2. 在属性窗口中, 单击![ <xref:System.Windows.Forms.ImageList.Images%2A>属性旁边的省略号按钮 (Visual](./media/visual-studio-ellipsis-button.png)Studio 的属性窗口中的省略号按钮 (...)。

3. 在**图像集合编辑器**中, 单击 "**添加**" 或 "**删除**" 以添加或删除列表中的映像。

### <a name="to-add-or-remove-images-using-the-smart-tag"></a>使用智能标记添加或删除图像

1. <xref:System.Windows.Forms.ImageList>选择组件, 或将其添加到窗体。

2. 单击智能标记字形 (![智能标记字形](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph"))

3. 在 " **ImageList 任务**" 对话框中, 选择 "**选择图像**"。

4. 在**图像集合编辑器**中, 单击 "**添加**" 或 "**删除**" 以添加或删除列表中的映像。

## <a name="see-also"></a>请参阅

- [图像、位图和图元文件](../advanced/images-bitmaps-and-metafiles.md)
- [演练：使用 Windows 窗体控件上的智能标记执行常见任务](performing-common-tasks-using-smart-tags-on-wf-controls.md)
- [ImageList 组件](imagelist-component-windows-forms.md)
