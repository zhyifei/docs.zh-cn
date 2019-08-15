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
ms.openlocfilehash: 5239017eb63ca6360ae8811a76497256fafbd1b1
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040135"
---
# <a name="effects-of-modifying-a-base-forms-appearance"></a><span data-ttu-id="079df-102">修改基窗体外观的效果</span><span class="sxs-lookup"><span data-stu-id="079df-102">Effects of modifying a base form's appearance</span></span>

<span data-ttu-id="079df-103">在应用程序开发过程中，可能经常需要更改基窗体的外观，该项目（或其他项目）中的其他窗体继承自此基窗体。</span><span class="sxs-lookup"><span data-stu-id="079df-103">During application development, you may often need to change the appearance of the base form from which other forms in the project (or in other projects) are inheriting.</span></span>

<span data-ttu-id="079df-104">在设计时，如果生成了包含基窗体的项目，则对基窗体外观所做更改（属性的设置或控件的增减）将反映在继承的窗体上。</span><span class="sxs-lookup"><span data-stu-id="079df-104">At design time, changes to the base form's appearance (be it the setting of properties or the addition and subtraction of controls) are reflected on inherited forms when the project containing the base form is built.</span></span> <span data-ttu-id="079df-105">仅将更改保存到基窗体是不够的。</span><span class="sxs-lookup"><span data-stu-id="079df-105">It is not sufficient for you to simply save the changes to the base form.</span></span> <span data-ttu-id="079df-106">若要生成项目，请从“生成”菜单选择“生成”。</span><span class="sxs-lookup"><span data-stu-id="079df-106">To build a project, choose **Build** from the **Build** menu.</span></span>

<span data-ttu-id="079df-107">在运行时对基窗体所做修改不影响已实例化的继承窗体。</span><span class="sxs-lookup"><span data-stu-id="079df-107">Modifications made to the base form at run time have no affect on inherited forms that are already instantiated.</span></span>

## <a name="see-also"></a><span data-ttu-id="079df-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="079df-108">See also</span></span>

- [<span data-ttu-id="079df-109">base</span><span class="sxs-lookup"><span data-stu-id="079df-109">base</span></span>](~/docs/csharp/language-reference/keywords/base.md)
- [<span data-ttu-id="079df-110">如何：继承 Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="079df-110">How to: Inherit Windows Forms</span></span>](how-to-inherit-windows-forms.md)
- [<span data-ttu-id="079df-111">Windows 窗体可视化继承</span><span class="sxs-lookup"><span data-stu-id="079df-111">Windows Forms Visual Inheritance</span></span>](windows-forms-visual-inheritance.md)
