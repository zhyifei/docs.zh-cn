---
title: 如何：按功能分组 Windows 窗体 RadioButton 控件
ms.date: 03/30/2017
helpviewer_keywords:
- radio buttons [Windows Forms], grouping
- controls [Windows Forms], grouping
- Windows Forms controls, grouping
- RadioButton control [Windows Forms], grouping
ms.assetid: 58f8fe34-50b7-49d8-a2be-c271be3c6b32
ms.openlocfilehash: c785b124d0b9efdbd9a1fa85819031cad3c8857c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59117892"
---
# <a name="how-to-group-windows-forms-radiobutton-controls-to-function-as-a-set"></a><span data-ttu-id="d9a37-102">如何：按功能分组 Windows 窗体 RadioButton 控件</span><span class="sxs-lookup"><span data-stu-id="d9a37-102">How to: Group Windows Forms RadioButton Controls to Function as a Set</span></span>
<span data-ttu-id="d9a37-103">Windows 窗体<xref:System.Windows.Forms.RadioButton>控件旨在让用户在两个或多个设置，其中只有一个可以分配给过程或对象之间进行选择。</span><span class="sxs-lookup"><span data-stu-id="d9a37-103">Windows Forms <xref:System.Windows.Forms.RadioButton> controls are designed to give users a choice among two or more settings, of which only one can be assigned to a procedure or object.</span></span> <span data-ttu-id="d9a37-104">例如，一组<xref:System.Windows.Forms.RadioButton>控件可能会显示选择的包承运商以便订单，但将只能使用一个承运商。</span><span class="sxs-lookup"><span data-stu-id="d9a37-104">For example, a group of <xref:System.Windows.Forms.RadioButton> controls may display a choice of package carriers for an order, but only one of the carriers will be used.</span></span> <span data-ttu-id="d9a37-105">因此只有一个<xref:System.Windows.Forms.RadioButton>一次可以选择，即使它是功能组的一部分。</span><span class="sxs-lookup"><span data-stu-id="d9a37-105">Therefore only one <xref:System.Windows.Forms.RadioButton> at a time can be selected, even if it is a part of a functional group.</span></span>  
  
 <span data-ttu-id="d9a37-106">单选按钮分组通过如容器内绘制它们<xref:System.Windows.Forms.Panel>控件，<xref:System.Windows.Forms.GroupBox>控件或窗体。</span><span class="sxs-lookup"><span data-stu-id="d9a37-106">You group radio buttons by drawing them inside a container such as a <xref:System.Windows.Forms.Panel> control, a <xref:System.Windows.Forms.GroupBox> control, or a form.</span></span> <span data-ttu-id="d9a37-107">直接添加到窗体成为一个组的所有单选按钮。</span><span class="sxs-lookup"><span data-stu-id="d9a37-107">All radio buttons that are added directly to a form become one group.</span></span> <span data-ttu-id="d9a37-108">若要添加单独的组，必须将它们放在面板或分组框中。</span><span class="sxs-lookup"><span data-stu-id="d9a37-108">To add separate groups, you must place them inside panels or group boxes.</span></span> <span data-ttu-id="d9a37-109">有关面板或分组框的详细信息，请参阅[Panel 控件概述](panel-control-overview-windows-forms.md)或[GroupBox 控件概述](groupbox-control-overview-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="d9a37-109">For more information about panels or group boxes, see [Panel Control Overview](panel-control-overview-windows-forms.md) or [GroupBox Control Overview](groupbox-control-overview-windows-forms.md).</span></span>  
  
### <a name="to-group-radiobutton-controls-as-a-set-to-function-independently-of-other-sets"></a><span data-ttu-id="d9a37-110">与为独立于其他集函数对一组单选按钮控件</span><span class="sxs-lookup"><span data-stu-id="d9a37-110">To group RadioButton controls as a set to function independently of other sets</span></span>  
  
1.  <span data-ttu-id="d9a37-111">拖动<xref:System.Windows.Forms.GroupBox>或<xref:System.Windows.Forms.Panel>控件从**Windows 窗体**选项卡上**工具箱**拖到窗体。</span><span class="sxs-lookup"><span data-stu-id="d9a37-111">Drag a <xref:System.Windows.Forms.GroupBox> or <xref:System.Windows.Forms.Panel> control from the **Windows Forms** tab on the **Toolbox** onto the form.</span></span>  
  
2.  <span data-ttu-id="d9a37-112">绘制<xref:System.Windows.Forms.RadioButton>上的控件<xref:System.Windows.Forms.GroupBox>或<xref:System.Windows.Forms.Panel>控件。</span><span class="sxs-lookup"><span data-stu-id="d9a37-112">Draw <xref:System.Windows.Forms.RadioButton> controls on the <xref:System.Windows.Forms.GroupBox> or <xref:System.Windows.Forms.Panel> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9a37-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="d9a37-113">See also</span></span>

- <xref:System.Windows.Forms.RadioButton>
- [<span data-ttu-id="d9a37-114">RadioButton 控件概述</span><span class="sxs-lookup"><span data-stu-id="d9a37-114">RadioButton Control Overview</span></span>](radiobutton-control-overview-windows-forms.md)
- [<span data-ttu-id="d9a37-115">Panel 控件概述</span><span class="sxs-lookup"><span data-stu-id="d9a37-115">Panel Control Overview</span></span>](panel-control-overview-windows-forms.md)
- [<span data-ttu-id="d9a37-116">GroupBox 控件概述</span><span class="sxs-lookup"><span data-stu-id="d9a37-116">GroupBox Control Overview</span></span>](groupbox-control-overview-windows-forms.md)
- [<span data-ttu-id="d9a37-117">CheckBox 控件概述</span><span class="sxs-lookup"><span data-stu-id="d9a37-117">CheckBox Control Overview</span></span>](checkbox-control-overview-windows-forms.md)
- [<span data-ttu-id="d9a37-118">RadioButton 控件</span><span class="sxs-lookup"><span data-stu-id="d9a37-118">RadioButton Control</span></span>](radiobutton-control-windows-forms.md)
