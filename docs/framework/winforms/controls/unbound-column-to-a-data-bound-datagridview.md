---
title: 向数据绑定 DataGridView 控件添加未绑定列
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- columns [Windows Forms], unbound data
- data grids [Windows Forms], adding unbound columns
- DataGridView control [Windows Forms], unbound data
ms.assetid: f7bdc4d8-ba8e-421b-ad62-82d936f01372
ms.openlocfilehash: 807bbc121f33c35d70068571e76637c078ecb3da
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76747068"
---
# <a name="how-to-add-an-unbound-column-to-a-data-bound-windows-forms-datagridview-control"></a><span data-ttu-id="dc3de-102">방법: 데이터 바인딩된 Windows Forms DataGridView 컨트롤에 바인딩되지 않은 열 추가</span><span class="sxs-lookup"><span data-stu-id="dc3de-102">How to: Add an Unbound Column to a Data-Bound Windows Forms DataGridView Control</span></span>
<span data-ttu-id="dc3de-103"><xref:System.Windows.Forms.DataGridView> 컨트롤에서 표시하는 데이터는 대개 일종의 데이터 소스에서 가져오지만 데이터 소스에서 가져오지 않는 데이터 열을 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc3de-103">The data you display in the <xref:System.Windows.Forms.DataGridView> control will normally come from a data source of some kind, but you might want to display a column of data that does not come from the data source.</span></span> <span data-ttu-id="dc3de-104">이 열 유형을 바인딩되지 않은 열이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc3de-104">This kind of column is called an unbound column.</span></span> <span data-ttu-id="dc3de-105">바인딩되지 않은 열에서는 대부분 폼을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc3de-105">Unbound columns can take many forms.</span></span> <span data-ttu-id="dc3de-106">대부분 경우에 바인딩되지 않은 열은 데이터 행의 세부 정보에 액세스하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc3de-106">Frequently, they are used to provide access to the details of a data row.</span></span>  
  
 <span data-ttu-id="dc3de-107">下面的代码示例演示了如何创建 "**详细信息**" 按钮的未绑定列，以便在实现主/从方案时显示与父表中的特定行相关的子表。</span><span class="sxs-lookup"><span data-stu-id="dc3de-107">The following code example demonstrates how to create an unbound column of **Details** buttons to display a child table related to a particular row in a parent table when you implement a master/detail scenario.</span></span> <span data-ttu-id="dc3de-108">단추 클릭에 응답하려면 자식 테이블이 포함된 폼을 표시하는 <xref:System.Windows.Forms.DataGridView.CellClick?displayProperty=nameWithType> 이벤트 처리기를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="dc3de-108">To respond to button clicks, implement a <xref:System.Windows.Forms.DataGridView.CellClick?displayProperty=nameWithType> event handler that displays a form containing the child table.</span></span>  
  
 <span data-ttu-id="dc3de-109">Visual Studio에서는 이 작업이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc3de-109">There is support for this task in Visual Studio.</span></span>  <span data-ttu-id="dc3de-110">另请参阅[如何：使用设计器在 Windows 窗体 DataGridView 控件中添加和删除列](add-and-remove-columns-in-the-datagrid-using-the-designer.md)。</span><span class="sxs-lookup"><span data-stu-id="dc3de-110">Also see [How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer](add-and-remove-columns-in-the-datagrid-using-the-designer.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="dc3de-111">示例</span><span class="sxs-lookup"><span data-stu-id="dc3de-111">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#010](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#010)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#010](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#010)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="dc3de-112">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="dc3de-112">Compiling the Code</span></span>  
 <span data-ttu-id="dc3de-113">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="dc3de-113">This example requires:</span></span>  
  
- <span data-ttu-id="dc3de-114">`dataGridView1`이라는 <xref:System.Windows.Forms.DataGridView> 컨트롤</span><span class="sxs-lookup"><span data-stu-id="dc3de-114">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
- <span data-ttu-id="dc3de-115"><xref:System?displayProperty=nameWithType> 및 <xref:System.Windows.Forms?displayProperty=nameWithType> 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="dc3de-115">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc3de-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dc3de-116">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="dc3de-117">Windows Forms DataGridView 컨트롤에서 데이터 표시</span><span class="sxs-lookup"><span data-stu-id="dc3de-117">Displaying Data in the Windows Forms DataGridView Control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="dc3de-118">Windows Forms DataGridView 컨트롤의 데이터 디스플레이 모드</span><span class="sxs-lookup"><span data-stu-id="dc3de-118">Data Display Modes in the Windows Forms DataGridView Control</span></span>](data-display-modes-in-the-windows-forms-datagridview-control.md)
