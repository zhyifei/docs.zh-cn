---
title: Windows 窗体控件中的属性
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], properties overview (using code)
- controls [Windows Forms], properties
- properties [Windows Forms]
ms.assetid: 2785279b-fb57-4937-8f6b-2050e475db6f
ms.openlocfilehash: 37db3f16a17acc7f3a6e594bd284ba368801e70a
ms.sourcegitcommit: 8c28ab17c26bf08abbd004cc37651985c68841b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/08/2018
ms.locfileid: "48850161"
---
# <a name="properties-in-windows-forms-controls"></a><span data-ttu-id="4e1a9-102">Windows 窗体控件中的属性</span><span class="sxs-lookup"><span data-stu-id="4e1a9-102">Properties in Windows Forms Controls</span></span>
<span data-ttu-id="4e1a9-103">Windows 窗体控件继承许多属性窗体的基类<xref:System.Windows.Forms.Control?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="4e1a9-103">A Windows Forms control inherits many properties form the base class <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span></span> <span data-ttu-id="4e1a9-104">这些包括属性如下所述<xref:System.Windows.Forms.Control.Font%2A>， <xref:System.Windows.Forms.Control.ForeColor%2A>， <xref:System.Windows.Forms.Control.BackColor%2A>， <xref:System.Windows.Forms.Control.Bounds%2A>， <xref:System.Windows.Forms.Control.ClientRectangle%2A>， <xref:System.Windows.Forms.Control.DisplayRectangle%2A>， <xref:System.Windows.Forms.Control.Enabled%2A>， <xref:System.Windows.Forms.Control.Focused%2A>， <xref:System.Windows.Forms.Control.Height%2A>， <xref:System.Windows.Forms.Control.Width%2A>， <xref:System.Windows.Forms.Control.Visible%2A>， <xref:System.Windows.Forms.Control.AutoSize%2A>，以及许多其他。</span><span class="sxs-lookup"><span data-stu-id="4e1a9-104">These include properties such as <xref:System.Windows.Forms.Control.Font%2A>, <xref:System.Windows.Forms.Control.ForeColor%2A>, <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.Bounds%2A>, <xref:System.Windows.Forms.Control.ClientRectangle%2A>, <xref:System.Windows.Forms.Control.DisplayRectangle%2A>, <xref:System.Windows.Forms.Control.Enabled%2A>, <xref:System.Windows.Forms.Control.Focused%2A>, <xref:System.Windows.Forms.Control.Height%2A>, <xref:System.Windows.Forms.Control.Width%2A>, <xref:System.Windows.Forms.Control.Visible%2A>, <xref:System.Windows.Forms.Control.AutoSize%2A>, and many others.</span></span> <span data-ttu-id="4e1a9-105">有关继承的属性的详细信息，请参阅<xref:System.Windows.Forms.Control?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="4e1a9-105">For details about inherited properties, see <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="4e1a9-106">可以在控件中重写继承的属性和定义新属性。</span><span class="sxs-lookup"><span data-stu-id="4e1a9-106">You can override inherited properties in your control as well as define new properties.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4e1a9-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="4e1a9-107">In This Section</span></span>  
 [<span data-ttu-id="4e1a9-108">定义属性</span><span class="sxs-lookup"><span data-stu-id="4e1a9-108">Defining a Property</span></span>](../../../../docs/framework/winforms/controls/defining-a-property-in-windows-forms-controls.md)  
 <span data-ttu-id="4e1a9-109">演示如何为自定义控件或组件实现属性，以及如何将该属性集成到设计环境中。</span><span class="sxs-lookup"><span data-stu-id="4e1a9-109">Shows how to implement a property for a custom control or component and shows how to integrate the property into the design environment.</span></span>  
  
 [<span data-ttu-id="4e1a9-110">使用 ShouldSerialize 和 Reset 方法定义默认值</span><span class="sxs-lookup"><span data-stu-id="4e1a9-110">Defining Default Values with the ShouldSerialize and Reset Methods</span></span>](../../../../docs/framework/winforms/controls/defining-default-values-with-the-shouldserialize-and-reset-methods.md)  
 <span data-ttu-id="4e1a9-111">演示如何为自定义控件或组件定义默认属性值。</span><span class="sxs-lookup"><span data-stu-id="4e1a9-111">Shows how to define default property values for a custom control or component.</span></span>  
  
 [<span data-ttu-id="4e1a9-112">属性更改事件</span><span class="sxs-lookup"><span data-stu-id="4e1a9-112">Property-Changed Events</span></span>](../../../../docs/framework/winforms/controls/property-changed-events.md)  
 <span data-ttu-id="4e1a9-113">介绍如何在属性值发生更改时启用属性更改通知。</span><span class="sxs-lookup"><span data-stu-id="4e1a9-113">Describes how to enable property-change notifications when a property value changes.</span></span>  
  
 [<span data-ttu-id="4e1a9-114">如何：公开构成控件的属性</span><span class="sxs-lookup"><span data-stu-id="4e1a9-114">How to: Expose Properties of Constituent Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-expose-properties-of-constituent-controls.md)  
 <span data-ttu-id="4e1a9-115">演示如何在自定义复合控件中公开构成控件的属性。</span><span class="sxs-lookup"><span data-stu-id="4e1a9-115">Shows how to expose properties of constituent controls in a custom composite control.</span></span>  
  
 [<span data-ttu-id="4e1a9-116">自定义控件中的方法实现</span><span class="sxs-lookup"><span data-stu-id="4e1a9-116">Method Implementation in Custom Controls</span></span>](../../../../docs/framework/winforms/controls/method-implementation-in-custom-controls.md)  
 <span data-ttu-id="4e1a9-117">介绍如何在自定义控件和组件中实现方法。</span><span class="sxs-lookup"><span data-stu-id="4e1a9-117">Describes how to implement methods in custom controls and components.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="4e1a9-118">参考</span><span class="sxs-lookup"><span data-stu-id="4e1a9-118">Reference</span></span>  
 <xref:System.Windows.Forms.UserControl>  
 <span data-ttu-id="4e1a9-119">介绍用于实现复合控件的基类。</span><span class="sxs-lookup"><span data-stu-id="4e1a9-119">Documents the base class for implementing composite controls.</span></span>  
  
 <xref:System.ComponentModel.TypeConverterAttribute>  
 <span data-ttu-id="4e1a9-120">介绍指定的特性<xref:System.ComponentModel.TypeConverter>要用于自定义属性类型。</span><span class="sxs-lookup"><span data-stu-id="4e1a9-120">Documents the attribute that specifies the <xref:System.ComponentModel.TypeConverter> to use for a custom property type.</span></span>  
  
 <xref:System.ComponentModel.EditorAttribute>  
 <span data-ttu-id="4e1a9-121">介绍指定的特性<xref:System.Drawing.Design.UITypeEditor>要用于自定义属性。</span><span class="sxs-lookup"><span data-stu-id="4e1a9-121">Documents the attribute that specifies the <xref:System.Drawing.Design.UITypeEditor> to use for a custom property.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="4e1a9-122">相关章节</span><span class="sxs-lookup"><span data-stu-id="4e1a9-122">Related Sections</span></span>  
 [<span data-ttu-id="4e1a9-123">Windows 窗体控件中的特性</span><span class="sxs-lookup"><span data-stu-id="4e1a9-123">Attributes in Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/attributes-in-windows-forms-controls.md)  
 <span data-ttu-id="4e1a9-124">描述你可以应用到自定义控件和组件的属性或其他成员的特性。</span><span class="sxs-lookup"><span data-stu-id="4e1a9-124">Describes the attributes you can apply to properties or other members of your custom controls and components.</span></span>  
  
 [<span data-ttu-id="4e1a9-125">组件的设计时特性</span><span class="sxs-lookup"><span data-stu-id="4e1a9-125">Design-Time Attributes for Components</span></span>](https://msdn.microsoft.com/library/12050fe3-9327-4509-9e21-4ee2494b95c3)  
 <span data-ttu-id="4e1a9-126">将列出的元数据特性应用到组件和控件，以便在设计时正确显示在可视化设计器中。</span><span class="sxs-lookup"><span data-stu-id="4e1a9-126">Lists metadata attributes to apply to components and controls so that they are displayed correctly at design time in visual designers.</span></span>  
  
 [<span data-ttu-id="4e1a9-127">扩展设计时支持</span><span class="sxs-lookup"><span data-stu-id="4e1a9-127">Extending Design-Time Support</span></span>](https://msdn.microsoft.com/library/d6ac8a6a-42fd-4bc8-bf33-b212811297e2)  
 <span data-ttu-id="4e1a9-128">描述如何实现提供设计时支持的类，例如编辑器和设计器。</span><span class="sxs-lookup"><span data-stu-id="4e1a9-128">Describes how to implement classes such as editors and designers that provide design-time support.</span></span>
