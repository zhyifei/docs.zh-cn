---
title: "Windows 窗体 DataGridView 控件中的数据格式设置"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DataGridView control [Windows Forms], formatting data
- data [Windows Forms], formatting in grids
- data grids [Windows Forms], formatting data
ms.assetid: 07bf558d-3748-42ba-8ba0-37fdef924081
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e716dc74946ac6f18ab82c6834518f0bd6bbea76
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="data-formatting-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="1f53e-102">Windows 窗体 DataGridView 控件中的数据格式设置</span><span class="sxs-lookup"><span data-stu-id="1f53e-102">Data Formatting in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="1f53e-103"><xref:System.Windows.Forms.DataGridView>控件提供单元格的值的父列显示的数据类型之间的自动转换。</span><span class="sxs-lookup"><span data-stu-id="1f53e-103">The <xref:System.Windows.Forms.DataGridView> control provides automatic conversion between cell values and the data types that the parent columns display.</span></span> <span data-ttu-id="1f53e-104">文本框列，例如，显示的日期、 时间、 号和枚举值的字符串表示形式，并将用户输入的字符串值转换为数据存储所需的类型。</span><span class="sxs-lookup"><span data-stu-id="1f53e-104">Text box columns, for example, display string representations of date, time, number, and enumeration values, and convert user-entered string values to the types required by the data store.</span></span>  
  
## <a name="formatting-with-the-datagridviewcellstyle-class"></a><span data-ttu-id="1f53e-105">使用 DataGridViewCellStyle 类进行格式设置</span><span class="sxs-lookup"><span data-stu-id="1f53e-105">Formatting with the DataGridViewCellStyle class</span></span>  
 <span data-ttu-id="1f53e-106"><xref:System.Windows.Forms.DataGridView>控件提供的单元格的值，通过基本数据格式设置<xref:System.Windows.Forms.DataGridViewCellStyle>类。</span><span class="sxs-lookup"><span data-stu-id="1f53e-106">The <xref:System.Windows.Forms.DataGridView> control provides basic data formatting of cell values through the <xref:System.Windows.Forms.DataGridViewCellStyle> class.</span></span> <span data-ttu-id="1f53e-107">你可以使用<xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A>为当前使用中所述的格式说明符的默认区域性的格式日期、 时间、 编号和枚举值的属性[格式化类型](../../../../docs/standard/base-types/formatting-types.md)。</span><span class="sxs-lookup"><span data-stu-id="1f53e-107">You can use the <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> property to format date, time, number, and enumeration values for the current default culture using the format specifiers described in [Formatting Types](../../../../docs/standard/base-types/formatting-types.md).</span></span> <span data-ttu-id="1f53e-108">你还可以设置特定区域性使用这些值进行格式<xref:System.Windows.Forms.DataGridViewCellStyle.FormatProvider%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="1f53e-108">You can also format these values for specific cultures using the <xref:System.Windows.Forms.DataGridViewCellStyle.FormatProvider%2A> property.</span></span> <span data-ttu-id="1f53e-109">使用指定的格式显示数据和分析用户在指定的格式中输入的数据。</span><span class="sxs-lookup"><span data-stu-id="1f53e-109">The specified format is used both to display data and to parse data that the user enters in the specified format.</span></span>  
  
 <span data-ttu-id="1f53e-110"><xref:System.Windows.Forms.DataGridViewCellStyle>类提供了附加的格式设置属性，自动换行、 文本对齐方式，以及数据库空值的自定义显示。</span><span class="sxs-lookup"><span data-stu-id="1f53e-110">The <xref:System.Windows.Forms.DataGridViewCellStyle> class provides additional formatting properties for wordwrap, text alignment, and the custom display of null database values.</span></span> <span data-ttu-id="1f53e-111">有关详细信息，请参阅[如何：设置 Windows 窗体 DataGridView 控件中的数据格式](../../../../docs/framework/winforms/controls/how-to-format-data-in-the-windows-forms-datagridview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="1f53e-111">For more information, see [How to: Format Data in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/how-to-format-data-in-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="formatting-with-the-cellformatting-event"></a><span data-ttu-id="1f53e-112">与 CellFormatting 事件格式设置</span><span class="sxs-lookup"><span data-stu-id="1f53e-112">Formatting with the CellFormatting Event</span></span>  
 <span data-ttu-id="1f53e-113">如果基本格式设置不符合你的需求，你可以提供自定义数据的处理程序中的格式设置<xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType>事件。</span><span class="sxs-lookup"><span data-stu-id="1f53e-113">If the basic formatting does not meet your needs, you can provide custom data formatting in a handler for the <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> event.</span></span> <span data-ttu-id="1f53e-114"><xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs>传递给处理程序具有<xref:System.Windows.Forms.ConvertEventArgs.Value%2A>最初包含单元格的值的属性。</span><span class="sxs-lookup"><span data-stu-id="1f53e-114">The <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs> passed to the handler has a <xref:System.Windows.Forms.ConvertEventArgs.Value%2A> property that initially contains the cell value.</span></span> <span data-ttu-id="1f53e-115">通常情况下，此值会自动转换为显示类型。</span><span class="sxs-lookup"><span data-stu-id="1f53e-115">Normally, this value is automatically converted to the display type.</span></span> <span data-ttu-id="1f53e-116">若要自行转换该值，将设置<xref:System.Windows.Forms.ConvertEventArgs.Value%2A>属性显示类型的值。</span><span class="sxs-lookup"><span data-stu-id="1f53e-116">To convert the value yourself, set the <xref:System.Windows.Forms.ConvertEventArgs.Value%2A> property to a value of the display type.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1f53e-117">如果单元格实际上是一个格式字符串，它将覆盖您对修改<xref:System.Windows.Forms.ConvertEventArgs.Value%2A>属性值，除非你设置<xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs.FormattingApplied%2A>属性`true`。</span><span class="sxs-lookup"><span data-stu-id="1f53e-117">If a format string is in effect for the cell, it overrides your change of the <xref:System.Windows.Forms.ConvertEventArgs.Value%2A> property value unless you set the <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs.FormattingApplied%2A> property to `true`.</span></span>  
  
 <span data-ttu-id="1f53e-118"><xref:System.Windows.Forms.DataGridView.CellFormatting>事件非常有用，当你想要设置<xref:System.Windows.Forms.DataGridViewCellStyle>各个单元格的属性基于其值。</span><span class="sxs-lookup"><span data-stu-id="1f53e-118">The <xref:System.Windows.Forms.DataGridView.CellFormatting> event is also useful when you want to set <xref:System.Windows.Forms.DataGridViewCellStyle> properties for individual cells based on their values.</span></span> <span data-ttu-id="1f53e-119">有关详细信息，请参阅[如何： 在 Windows 窗体 DataGridView 控件中自定义数据格式](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="1f53e-119">For more information, see [How to: Customize Data Formatting in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).</span></span>  
  
 <span data-ttu-id="1f53e-120">如果用户指定值的默认分析不满足你的需求，你可以处理<xref:System.Windows.Forms.DataGridView.CellParsing>事件<xref:System.Windows.Forms.DataGridView>控件提供自定义分析。</span><span class="sxs-lookup"><span data-stu-id="1f53e-120">If the default parsing of user-specified values does not meet your needs, you can handle the <xref:System.Windows.Forms.DataGridView.CellParsing> event of the <xref:System.Windows.Forms.DataGridView> control to provide custom parsing.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f53e-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1f53e-121">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewCellStyle>  
 [<span data-ttu-id="1f53e-122">在 Windows 窗体 DataGridView 控件中显示数据</span><span class="sxs-lookup"><span data-stu-id="1f53e-122">Displaying Data in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="1f53e-123">Windows 窗体 DataGridView 控件中的单元格样式</span><span class="sxs-lookup"><span data-stu-id="1f53e-123">Cell Styles in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="1f53e-124">如何：在 Windows 窗体 DataGridView 控件中设置数据格式</span><span class="sxs-lookup"><span data-stu-id="1f53e-124">How to: Format Data in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-format-data-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="1f53e-125">如何：在 Windows 窗体 DataGridView 控件中自定义数据格式设置</span><span class="sxs-lookup"><span data-stu-id="1f53e-125">How to: Customize Data Formatting in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)
