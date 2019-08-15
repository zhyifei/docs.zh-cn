---
title: 如何：使用设计器为 Windows 窗体控件创建访问键
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], access keys
- Button control [Windows Forms], access keys
- dialog box controls [Windows Forms], mnemonics
- access keys [Windows Forms], creating for controls
- mnemonics [Windows Forms], adding to dialog box controls
- ampersand character in shortcut key
- Windows Forms controls, access keys
- examples [Windows Forms], controls
- Text property [Windows Forms], specifying access keys for controls
- keyboard shortcuts [Windows Forms], creating for controls
- access keys [Windows Forms], Windows Forms
- ALT key
ms.assetid: 4c374c4c-4ca9-4a68-ac96-9dc3ab0f518a
ms.openlocfilehash: 01bed04483702ba2e62162b675aa1138bc1b0e01
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039525"
---
# <a name="how-to-create-access-keys-for-windows-forms-controls-using-the-designer"></a>如何：使用设计器为 Windows 窗体控件创建访问键
*访问键*是菜单、菜单项或控件 (如按钮) 的标签文本中带下划线的字符。 它使用户可以通过将 ALT 键与预定义的访问密钥结合使用来 "单击" 按钮。 例如, 如果按钮运行过程来打印窗体, 因此其`Text`属性设置为 "打印", 则在字母 "p" 之前添加 "and" 符 (&) 会导致在运行时将字母 "p" 添加到按钮文本中的下划线。 用户可以通过按 ALT + P 运行与该按钮关联的命令。 不能为无法接收焦点的控件提供访问键。

## <a name="to-create-an-access-key-for-a-control"></a>为控件创建访问键

1. 在 "**属性**" 窗口中, `Text`将属性设置为一个字符串, 该字符串包含 "&" 符 (&) (在将作为访问密钥的字母之前)。 例如, 若要将字母 "P" 设置为访问键, 请键入 **& 打印**到网格中。

## <a name="see-also"></a>请参阅

- <xref:System.Windows.Forms.Button>
- [如何：响应 Windows 窗体按钮单击](how-to-respond-to-windows-forms-button-clicks.md)
- [如何：设置 Windows 窗体控件显示的文本](how-to-set-the-text-displayed-by-a-windows-forms-control.md)
- [标记各个 Windows 窗体控件并创建它们的快捷键](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
