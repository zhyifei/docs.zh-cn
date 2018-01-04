---
title: "通过 ImeMode 属性显示亚洲字符"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5971fd9a75f936d2ec63eea6a086c681ec996652
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="display-of-asian-characters-with-the-imemode-property"></a><span data-ttu-id="ae05a-102">通过 ImeMode 属性显示亚洲字符</span><span class="sxs-lookup"><span data-stu-id="ae05a-102">Display of Asian Characters with the ImeMode Property</span></span>
<span data-ttu-id="ae05a-103"><xref:System.Windows.Forms.Control.ImeMode%2A>属性使用的窗体和控件，以强制进行输入的法编辑器 (IME) 的特定模式。</span><span class="sxs-lookup"><span data-stu-id="ae05a-103">The <xref:System.Windows.Forms.Control.ImeMode%2A> property is used by forms and controls to force a specific mode for an input method editor (IME).</span></span> <span data-ttu-id="ae05a-104">IME 是编写中文、日语和朝鲜语脚本的必备组件，因为这些编写系统具有的字符多于常规键盘可编码的字符。</span><span class="sxs-lookup"><span data-stu-id="ae05a-104">The IME is an essential component for writing Chinese, Japanese, and Korean scripts, since these writing systems have more characters than can be encoded for a regular keyboard.</span></span> <span data-ttu-id="ae05a-105">例如，可能想在特定文本框中仅允许使用 ASCII 字符。</span><span class="sxs-lookup"><span data-stu-id="ae05a-105">For example, you may want to allow only ASCII characters in a particular text box.</span></span> <span data-ttu-id="ae05a-106">在这种情况下可以设置<xref:System.Windows.Forms.Control.ImeMode%2A>属性<xref:System.Windows.Forms.ImeMode>并且用户将只能为该特定文本框中输入 ASCII 字符。</span><span class="sxs-lookup"><span data-stu-id="ae05a-106">In such a case you can set the <xref:System.Windows.Forms.Control.ImeMode%2A> property to <xref:System.Windows.Forms.ImeMode> and users will only be able to enter ASCII characters for that particular text box.</span></span> <span data-ttu-id="ae05a-107">默认值<xref:System.Windows.Forms.Control.ImeMode%2A>属性是<xref:System.Windows.Forms.ImeMode>，因此如果你设置窗体的属性，在窗体上的所有控件将都继承该设置。</span><span class="sxs-lookup"><span data-stu-id="ae05a-107">The default value of the <xref:System.Windows.Forms.Control.ImeMode%2A> property is <xref:System.Windows.Forms.ImeMode>, so if you set the property for a form, all controls on the form will inherit that setting.</span></span> <span data-ttu-id="ae05a-108">有关详细信息，请参阅<xref:System.Windows.Forms.Control.ImeMode%2A>) 和<xref:System.Windows.Forms.ImeMode>。</span><span class="sxs-lookup"><span data-stu-id="ae05a-108">For more information, see <xref:System.Windows.Forms.Control.ImeMode%2A> ) and <xref:System.Windows.Forms.ImeMode>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae05a-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="ae05a-109">See Also</span></span>  
 [<span data-ttu-id="ae05a-110">全球化 Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="ae05a-110">Globalizing Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/globalizing-windows-forms.md)
