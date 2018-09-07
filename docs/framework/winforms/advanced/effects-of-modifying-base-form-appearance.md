---
title: 修改基窗体的外观的效果
ms.date: 03/30/2017
helpviewer_keywords:
- parent forms [Windows Forms]
- inherited forms [Windows Forms], modifications to base form
- Windows Forms, base form appearance
- base forms
- inheritance [Windows Forms], forms
ms.assetid: 1c3f2b29-a05c-4c6f-aa1a-4e66b94f343a
ms.openlocfilehash: adaf9224fd340c6ea4342e2591806a7c877e83ff
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "44084404"
---
# <a name="effects-of-modifying-a-base-form39s-appearance"></a><span data-ttu-id="232f8-102">修改基窗体的外观的效果</span><span class="sxs-lookup"><span data-stu-id="232f8-102">Effects of Modifying a Base Form&#39;s Appearance</span></span>
<span data-ttu-id="232f8-103">在应用程序开发过程中，可能经常需要更改基窗体的外观，该项目（或其他项目）中的其他窗体继承自此基窗体。</span><span class="sxs-lookup"><span data-stu-id="232f8-103">During application development, you may often need to change the appearance of the base form from which other forms in the project (or in other projects) are inheriting.</span></span>  
  
 <span data-ttu-id="232f8-104">在设计时，如果生成了包含基窗体的项目，则对基窗体外观所做更改（属性的设置或控件的增减）将反映在继承的窗体上。</span><span class="sxs-lookup"><span data-stu-id="232f8-104">At design time, changes to the base form's appearance (be it the setting of properties or the addition and subtraction of controls) are reflected on inherited forms when the project containing the base form is built.</span></span> <span data-ttu-id="232f8-105">仅将更改保存到基窗体是不够的。</span><span class="sxs-lookup"><span data-stu-id="232f8-105">It is not sufficient for you to simply save the changes to the base form.</span></span> <span data-ttu-id="232f8-106">若要生成项目，请从“生成”菜单选择“生成”。</span><span class="sxs-lookup"><span data-stu-id="232f8-106">To build a project, choose **Build** from the **Build** menu.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="232f8-107">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="232f8-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="232f8-108">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="232f8-108">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="232f8-109">有关详细信息，请参阅[个性化设置 Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide)。</span><span class="sxs-lookup"><span data-stu-id="232f8-109">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
 <span data-ttu-id="232f8-110">在运行时对基窗体所做修改不影响已实例化的继承窗体。</span><span class="sxs-lookup"><span data-stu-id="232f8-110">Modifications made to the base form at run time have no affect on inherited forms that are already instantiated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="232f8-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="232f8-111">See Also</span></span>  
 [<span data-ttu-id="232f8-112">base</span><span class="sxs-lookup"><span data-stu-id="232f8-112">base</span></span>](~/docs/csharp/language-reference/keywords/base.md)  
 [<span data-ttu-id="232f8-113">如何：继承 Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="232f8-113">How to: Inherit Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-inherit-windows-forms.md)  
 [<span data-ttu-id="232f8-114">Windows 窗体可视化继承</span><span class="sxs-lookup"><span data-stu-id="232f8-114">Windows Forms Visual Inheritance</span></span>](../../../../docs/framework/winforms/advanced/windows-forms-visual-inheritance.md)
