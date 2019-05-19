---
title: 如何：使用设计器添加或移除 ImageList 图像
ms.date: 03/30/2017
helpviewer_keywords:
- ImageList component [Windows Forms], adding images
- ImageList component [Windows Forms], removing images
- images [Windows Forms], adding to ImageList component
ms.assetid: 5699b244-e37c-4d20-bc35-7441e55c1e3a
ms.openlocfilehash: 346d7107c9c17c5df06fa0e47f7a35355344f590
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2019
ms.locfileid: "65880725"
---
# <a name="how-to-add-or-remove-imagelist-images-with-the-designer"></a>如何：使用设计器添加或移除 ImageList 图像
您可以将映像添加到<xref:System.Windows.Forms.ImageList>组件多种不同的方式。 您可以通过使用与关联的智能标记非常快速地添加图像<xref:System.Windows.Forms.ImageList>，或如果您在上设置多个其他属性<xref:System.Windows.Forms.ImageList>，可能会发现更方便地添加具有属性窗口的图像。 此外可以通过使用代码来添加映像。 有关如何通过代码添加图像的详细信息，请参阅[如何：添加或删除图像与 Windows 窗体 ImageList 组件](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)。 通常填充<xref:System.Windows.Forms.ImageList>映像之前它是与控件相关联，但这不是必需组件。  
  
> [!NOTE]
>  显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。 若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。 有关详细信息，请参阅[个性化设置 Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide)。  
  
### <a name="to-add-or-remove-images-by-using-the-properties-window"></a>若要添加或删除映像，通过使用属性窗口  
  
1. 选择<xref:System.Windows.Forms.ImageList>组件，或添加到窗体。  
  
2.  在属性窗口中，单击省略号按钮 (![的 Visual Studio 属性窗口中的省略号按钮 （...）](./media/visual-studio-ellipsis-button.png)) 旁边<xref:System.Windows.Forms.ImageList.Images%2A>属性。  
  
3. 在中**图像集合编辑器**，单击**添加**或**删除**来添加或从列表中删除映像。  
  
### <a name="to-add-or-remove-images-using-the-smart-tag"></a>若要添加或删除使用智能标记的图像  
  
1. 选择<xref:System.Windows.Forms.ImageList>组件，或添加到窗体。  
  
2. 单击智能标记标志符号 (![智能标记标志符号](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph"))  
  
3. 在中**ImageList 任务**对话框中，选择**选择映像**。  
  
4. 在中**图像集合编辑器**单击**添加**或**删除**来添加或从列表中删除映像。  
  
## <a name="see-also"></a>请参阅

- [图像、位图和图元文件](../advanced/images-bitmaps-and-metafiles.md)
- [演练：执行常见任务使用智能标记在 Windows 窗体控件](performing-common-tasks-using-smart-tags-on-wf-controls.md)
- [ImageList 组件](imagelist-component-windows-forms.md)
