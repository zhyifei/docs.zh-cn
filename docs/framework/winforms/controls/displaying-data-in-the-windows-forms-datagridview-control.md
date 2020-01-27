---
title: 在 DataGridView 控件中显示数据
ms.date: 03/30/2017
helpviewer_keywords:
- data [Windows Forms], displaying in tabular format
- data grids [Windows Forms], displaying data
- displaying data [Windows Forms], data grids
- DataGridView control [Windows Forms], displaying data
ms.assetid: b170b52a-2ebd-4948-ac2f-e52d494cebb2
ms.openlocfilehash: d02362895d75df3735d19554bd44bb8ac443c6c2
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745865"
---
# <a name="displaying-data-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="3c786-102">Windows Forms DataGridView 컨트롤에서 데이터 표시</span><span class="sxs-lookup"><span data-stu-id="3c786-102">Displaying Data in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="3c786-103">`DataGridView` 控件用于显示来自各种外部数据源的数据。</span><span class="sxs-lookup"><span data-stu-id="3c786-103">The `DataGridView` control is used to display data from a variety of external data sources.</span></span> <span data-ttu-id="3c786-104">此外，也可以向控件添加行和列，并手动填充数据。</span><span class="sxs-lookup"><span data-stu-id="3c786-104">Alternatively, you can add rows and columns to the control and manually populate it with data.</span></span>  
  
 <span data-ttu-id="3c786-105">将控件绑定到数据源时，可以基于数据源的架构自动生成列。</span><span class="sxs-lookup"><span data-stu-id="3c786-105">When you bind the control to a data source, you can generate columns automatically based on the schema of the data source.</span></span> <span data-ttu-id="3c786-106">如果这些列没有按您所需的方式显示，您可以隐藏、删除或重新排列这些列。</span><span class="sxs-lookup"><span data-stu-id="3c786-106">If these columns do not appear just as you want them to, you can hide, remove, or rearrange them.</span></span> <span data-ttu-id="3c786-107">您还可以添加未绑定的列，以显示来自数据源的补充数据。</span><span class="sxs-lookup"><span data-stu-id="3c786-107">You can also add unbound columns to display supplemental data that does not come from the data source.</span></span>  
  
 <span data-ttu-id="3c786-108">此外，您还可以使用标准格式（如货币格式）来显示数据，也可以自定义显示格式以显示您的数据，但您需要这样做（例如更改负数背景色或替换字符串值）。带有相应图像的）。</span><span class="sxs-lookup"><span data-stu-id="3c786-108">Additionally, you can display your data using standard formats (such as currency format), or you can customize the display formatting to present your data however you need to (such as changing the background color for negative numbers, or replacing string values with corresponding images).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3c786-109">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="3c786-109">In This Section</span></span>  
 [<span data-ttu-id="3c786-110">Windows Forms DataGridView 컨트롤의 데이터 디스플레이 모드</span><span class="sxs-lookup"><span data-stu-id="3c786-110">Data Display Modes in the Windows Forms DataGridView Control</span></span>](data-display-modes-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="3c786-111">介绍用于用数据填充控件的选项。</span><span class="sxs-lookup"><span data-stu-id="3c786-111">Describes the options for populating the control with data.</span></span>  
  
 [<span data-ttu-id="3c786-112">Windows Forms DataGridView 컨트롤의 데이터 형식 지정</span><span class="sxs-lookup"><span data-stu-id="3c786-112">Data Formatting in the Windows Forms DataGridView Control</span></span>](data-formatting-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="3c786-113">描述用于设置单元格显示值格式的选项。</span><span class="sxs-lookup"><span data-stu-id="3c786-113">Describes the options for formatting cell display values.</span></span>  
  
 [<span data-ttu-id="3c786-114">연습: 바인딩되지 않은 Windows Forms DataGridView 컨트롤 만들기</span><span class="sxs-lookup"><span data-stu-id="3c786-114">Walkthrough: Creating an Unbound Windows Forms DataGridView Control</span></span>](walkthrough-creating-an-unbound-windows-forms-datagridview-control.md)  
 <span data-ttu-id="3c786-115">描述如何用数据手动填充控件。</span><span class="sxs-lookup"><span data-stu-id="3c786-115">Describes how to manually populate the control with data.</span></span>  
  
 [<span data-ttu-id="3c786-116">방법: Windows Forms DataGridView 컨트롤에 데이터 바인딩</span><span class="sxs-lookup"><span data-stu-id="3c786-116">How to: Bind Data to the Windows Forms DataGridView Control</span></span>](how-to-bind-data-to-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="3c786-117">介绍如何通过将数据绑定到包含从数据库中提取的信息的 `BindingSource`，使用数据填充控件。</span><span class="sxs-lookup"><span data-stu-id="3c786-117">Describes how to populate the control with data by binding it to a `BindingSource` that contains information pulled from a database.</span></span>  
  
 [<span data-ttu-id="3c786-118">방법: 데이터 바인딩된 Windows Forms DataGridView 컨트롤에서 열 자동 생성</span><span class="sxs-lookup"><span data-stu-id="3c786-118">How to: Autogenerate Columns in a Data-Bound Windows Forms DataGridView Control</span></span>](autogenerate-columns-in-a-data-bound-wf-datagridview-control.md)  
 <span data-ttu-id="3c786-119">描述如何基于绑定数据源自动生成列。</span><span class="sxs-lookup"><span data-stu-id="3c786-119">Describes how to automatically generate columns based on a bound data source.</span></span>  
  
 [<span data-ttu-id="3c786-120">방법: 자동으로 생성된 열을 Windows Forms DataGridView 컨트롤에서 제거</span><span class="sxs-lookup"><span data-stu-id="3c786-120">How to: Remove Autogenerated Columns from a Windows Forms DataGridView Control</span></span>](remove-autogenerated-columns-from-a-wf-datagridview-control.md)  
 <span data-ttu-id="3c786-121">介绍如何隐藏或删除从绑定数据源自动生成的列。</span><span class="sxs-lookup"><span data-stu-id="3c786-121">Describes how to hide or delete columns generated automatically from a bound data source.</span></span>  
  
 [<span data-ttu-id="3c786-122">방법: Windows Forms DataGridView 컨트롤에서 열 순서 변경</span><span class="sxs-lookup"><span data-stu-id="3c786-122">How to: Change the Order of Columns in the Windows Forms DataGridView Control</span></span>](how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="3c786-123">描述如何重新排列从绑定数据源自动生成的列。</span><span class="sxs-lookup"><span data-stu-id="3c786-123">Describes how to rearrange columns generated automatically from a bound data source.</span></span>  
  
 [<span data-ttu-id="3c786-124">방법: 데이터 바인딩된 Windows Forms DataGridView 컨트롤에 바인딩되지 않은 열 추가</span><span class="sxs-lookup"><span data-stu-id="3c786-124">How to: Add an Unbound Column to a Data-Bound Windows Forms DataGridView Control</span></span>](unbound-column-to-a-data-bound-datagridview.md)  
 <span data-ttu-id="3c786-125">介绍如何通过显示其他未绑定的列来补充绑定数据源中的数据。</span><span class="sxs-lookup"><span data-stu-id="3c786-125">Describes how to supplement data from a bound data source by displaying additional, unbound columns.</span></span>  
  
 [<span data-ttu-id="3c786-126">방법: Windows Forms DataGridView 컨트롤에 개체 바인딩</span><span class="sxs-lookup"><span data-stu-id="3c786-126">How to: Bind Objects to Windows Forms DataGridView Controls</span></span>](how-to-bind-objects-to-windows-forms-datagridview-controls.md)  
 <span data-ttu-id="3c786-127">介绍如何将控件绑定到任意对象的集合，以便每个对象显示在其自己的行中。</span><span class="sxs-lookup"><span data-stu-id="3c786-127">Describes how to bind the control to a collection of arbitrary objects so that each object is displayed in its own row.</span></span>  
  
 [<span data-ttu-id="3c786-128">방법: Windows Forms DataGridView 행에 바인딩된 개체에 액세스</span><span class="sxs-lookup"><span data-stu-id="3c786-128">How to: Access Objects Bound to Windows Forms DataGridView Rows</span></span>](how-to-access-objects-bound-to-windows-forms-datagridview-rows.md)  
 <span data-ttu-id="3c786-129">介绍如何检索绑定到控件的特定行的对象。</span><span class="sxs-lookup"><span data-stu-id="3c786-129">Describes how to retrieve an object bound to a particular row of the control.</span></span>  
  
 [<span data-ttu-id="3c786-130">연습: 두 개의 Windows Forms DataGridView 컨트롤을 사용하여 마스터/세부 폼 만들기</span><span class="sxs-lookup"><span data-stu-id="3c786-130">Walkthrough: Creating a Master/Detail Form Using Two Windows Forms DataGridView Controls</span></span>](creating-a-master-detail-form-using-two-datagridviews.md)  
 <span data-ttu-id="3c786-131">介绍如何显示两个相关数据库表中的数据，以便 `DataGridView` 控件中显示的值依赖于另一个控件中当前所选的行。</span><span class="sxs-lookup"><span data-stu-id="3c786-131">Describes how to display data from two related database tables so that the values shown in one `DataGridView` control depend on the currently selected row in another control.</span></span>  
  
 [<span data-ttu-id="3c786-132">방법: Windows Forms DataGridView 컨트롤에서 데이터 형식 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="3c786-132">How to: Customize Data Formatting in the Windows Forms DataGridView Control</span></span>](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="3c786-133">描述如何处理 <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> 事件以根据单元格的值更改单元格的外观。</span><span class="sxs-lookup"><span data-stu-id="3c786-133">Describes how to handle the <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> event to change the appearance of cells depending on their values.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="3c786-134">참조</span><span class="sxs-lookup"><span data-stu-id="3c786-134">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="3c786-135"><xref:System.Windows.Forms.DataGridView> 컨트롤에 대한 참조 설명서를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3c786-135">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>  
 <span data-ttu-id="3c786-136">提供 <xref:System.Windows.Forms.DataGridView.DataSource%2A> 属性的参考文档。</span><span class="sxs-lookup"><span data-stu-id="3c786-136">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.DataSource%2A> property.</span></span>  
  
 <xref:System.Windows.Forms.BindingSource>  
 <span data-ttu-id="3c786-137"><xref:System.Windows.Forms.BindingSource> 구성 요소에 대한 참조 설명서를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3c786-137">Provides reference documentation for the <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="3c786-138">관련 섹션</span><span class="sxs-lookup"><span data-stu-id="3c786-138">Related Sections</span></span>  
 [<span data-ttu-id="3c786-139">Windows Forms DataGridView 컨트롤의 데이터 입력</span><span class="sxs-lookup"><span data-stu-id="3c786-139">Data Entry in the Windows Forms DataGridView Control</span></span>](data-entry-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="3c786-140">사용자가 컨트롤에서 데이터를 추가 및 수정하는 방법을 변경하는 방법에 대해 설명하는 항목을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3c786-140">Provides topics that describe how to change the way users add and modify data in the control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c786-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3c786-141">See also</span></span>

- [<span data-ttu-id="3c786-142">DataGridView 컨트롤</span><span class="sxs-lookup"><span data-stu-id="3c786-142">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
- [<span data-ttu-id="3c786-143">Windows Forms DataGridView 컨트롤의 열 형식</span><span class="sxs-lookup"><span data-stu-id="3c786-143">Column Types in the Windows Forms DataGridView Control</span></span>](column-types-in-the-windows-forms-datagridview-control.md)
