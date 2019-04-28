---
title: 通过 ImeMode 属性显示亚洲字符
ms.date: 03/30/2017
helpviewer_keywords:
- Asian languages [Windows Forms], displaying with ImeMode
- Chinese characters [Windows Forms], displaying with ImeMode
- IME mode
- Japanese characters [Windows Forms], displaying with ImeMode
- international applications [Windows Forms], character display
- international characters
- Korean characters
- Asian languages
- Input Method Editor (IME), mode
- localization [Windows Forms], character sets
- globalization [Windows Forms], character sets
ms.assetid: c60ae399-0dab-4f07-9dea-6dbfb15ec0ae
ms.openlocfilehash: 25602e1a878443bd54411dfd6481581abebda5c7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61755475"
---
# <a name="display-of-asian-characters-with-the-imemode-property"></a><span data-ttu-id="3725f-102">通过 ImeMode 属性显示亚洲字符</span><span class="sxs-lookup"><span data-stu-id="3725f-102">Display of Asian Characters with the ImeMode Property</span></span>
<span data-ttu-id="3725f-103"><xref:System.Windows.Forms.Control.ImeMode%2A>属性用于窗体和控件的输入的法编辑器 (IME) 强制使用特定模式。</span><span class="sxs-lookup"><span data-stu-id="3725f-103">The <xref:System.Windows.Forms.Control.ImeMode%2A> property is used by forms and controls to force a specific mode for an input method editor (IME).</span></span> <span data-ttu-id="3725f-104">IME 是编写中文、日语和朝鲜语脚本的必备组件，因为这些编写系统具有的字符多于常规键盘可编码的字符。</span><span class="sxs-lookup"><span data-stu-id="3725f-104">The IME is an essential component for writing Chinese, Japanese, and Korean scripts, since these writing systems have more characters than can be encoded for a regular keyboard.</span></span> <span data-ttu-id="3725f-105">例如，可能想在特定文本框中仅允许使用 ASCII 字符。</span><span class="sxs-lookup"><span data-stu-id="3725f-105">For example, you may want to allow only ASCII characters in a particular text box.</span></span> <span data-ttu-id="3725f-106">在这种情况下可以设置<xref:System.Windows.Forms.Control.ImeMode%2A>属性设置为<xref:System.Windows.Forms.ImeMode>和用户将只能为该特定文本框中输入 ASCII 字符。</span><span class="sxs-lookup"><span data-stu-id="3725f-106">In such a case you can set the <xref:System.Windows.Forms.Control.ImeMode%2A> property to <xref:System.Windows.Forms.ImeMode> and users will only be able to enter ASCII characters for that particular text box.</span></span> <span data-ttu-id="3725f-107">默认值<xref:System.Windows.Forms.Control.ImeMode%2A>属性是<xref:System.Windows.Forms.ImeMode>，因此，如果设置窗体的属性，在窗体上的所有控件将都继承该设置。</span><span class="sxs-lookup"><span data-stu-id="3725f-107">The default value of the <xref:System.Windows.Forms.Control.ImeMode%2A> property is <xref:System.Windows.Forms.ImeMode>, so if you set the property for a form, all controls on the form will inherit that setting.</span></span> <span data-ttu-id="3725f-108">有关详细信息，请参阅<xref:System.Windows.Forms.Control.ImeMode%2A>) 和<xref:System.Windows.Forms.ImeMode>。</span><span class="sxs-lookup"><span data-stu-id="3725f-108">For more information, see <xref:System.Windows.Forms.Control.ImeMode%2A> ) and <xref:System.Windows.Forms.ImeMode>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3725f-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="3725f-109">See also</span></span>

- [<span data-ttu-id="3725f-110">全球化 Windows 窗体应用程序</span><span class="sxs-lookup"><span data-stu-id="3725f-110">Globalizing Windows Forms applications</span></span>](globalizing-windows-forms.md)
