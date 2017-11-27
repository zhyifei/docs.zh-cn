---
title: "如何：在 Windows 窗体上创建简单绑定控件"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data binding [Windows Forms], simple data binding
- Windows Forms controls, data binding
ms.assetid: 3bcaded8-0f1a-4cc0-8830-f59be253bf4e
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0b95892641000287f57840ec57cd65147b986829
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-simple-bound-control-on-a-windows-form"></a><span data-ttu-id="edcdf-102">如何：在 Windows 窗体上创建简单绑定控件</span><span class="sxs-lookup"><span data-stu-id="edcdf-102">How to: Create a Simple-Bound Control on a Windows Form</span></span>
<span data-ttu-id="edcdf-103">与*简单绑定*，你可以在控件中显示单个数据元素，如从数据集表中列的值。</span><span class="sxs-lookup"><span data-stu-id="edcdf-103">With *simple binding*, you can display a single data element, such as a column value from a dataset table, in a control.</span></span> <span data-ttu-id="edcdf-104">可以将控件的任何属性的简单绑定到数据值。</span><span class="sxs-lookup"><span data-stu-id="edcdf-104">You can simple-bind any property of a control to a data value.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="edcdf-105">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="edcdf-105">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="edcdf-106">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="edcdf-106">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="edcdf-107">有关详细信息，请参阅[在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。</span><span class="sxs-lookup"><span data-stu-id="edcdf-107">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-simple-bind-a-control"></a><span data-ttu-id="edcdf-108">简单绑定控件</span><span class="sxs-lookup"><span data-stu-id="edcdf-108">To simple-bind a control</span></span>  
  
1.  <span data-ttu-id="edcdf-109">连接到数据源。</span><span class="sxs-lookup"><span data-stu-id="edcdf-109">Connect to a data source.</span></span> <span data-ttu-id="edcdf-110">有关详细信息，请参阅[连接到数据源](../../../docs/framework/data/adonet/connecting-to-a-data-source.md)。</span><span class="sxs-lookup"><span data-stu-id="edcdf-110">For more information, see [Connecting to a Data Source](../../../docs/framework/data/adonet/connecting-to-a-data-source.md).</span></span>  
  
2.  <span data-ttu-id="edcdf-111">在表单中，选择控件，并显示**属性**窗口。</span><span class="sxs-lookup"><span data-stu-id="edcdf-111">In the form, select the control and display the **Properties** window.</span></span>  
  
3.  <span data-ttu-id="edcdf-112">展开**(DataBindings)**属性。</span><span class="sxs-lookup"><span data-stu-id="edcdf-112">Expand the **(DataBindings)** property.</span></span>  
  
     <span data-ttu-id="edcdf-113">最常绑定的属性将显示下**(DataBindings)**属性。</span><span class="sxs-lookup"><span data-stu-id="edcdf-113">The properties most often bound are displayed underneath the **(DataBindings)** property.</span></span> <span data-ttu-id="edcdf-114">例如，在大多数控件，**文本**最经常绑定属性。</span><span class="sxs-lookup"><span data-stu-id="edcdf-114">For example, in most controls, the **Text** property is most frequently bound.</span></span>  
  
4.  <span data-ttu-id="edcdf-115">如果属性你想要绑定不是一个经常绑定的属性，单击**省略号**按钮 (![VisualStudioEllipsesButton 屏幕快照](../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) 在**（高级）**框，以显示**格式设置和高级绑定**对话框中的完整列表与该控件的属性。</span><span class="sxs-lookup"><span data-stu-id="edcdf-115">If the property you want to bind is not one of the commonly bound properties, click the **Ellipsis** button (![VisualStudioEllipsesButton screenshot](../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) in the **(Advanced)** box to display the **Formatting and Advanced Binding** dialog box with a complete list of properties for that control.</span></span>  
  
5.  <span data-ttu-id="edcdf-116">选择你想要将绑定并单击下的下拉箭头的属性**绑定**。</span><span class="sxs-lookup"><span data-stu-id="edcdf-116">Select the property you want to bind and click the drop-down arrow under **Binding**.</span></span>  
  
     <span data-ttu-id="edcdf-117">此时将显示可用数据源的列表。</span><span class="sxs-lookup"><span data-stu-id="edcdf-117">A list of available data sources is displayed.</span></span>  
  
6.  <span data-ttu-id="edcdf-118">展开要绑定到的数据源，直到找到所需的单个数据元素。</span><span class="sxs-lookup"><span data-stu-id="edcdf-118">Expand the data source you want to bind to until you find the single data element you want.</span></span> <span data-ttu-id="edcdf-119">例如，如果你正在绑定到数据集表中的列值，请展开该数据集的名称，然后展开表名以显示列名。</span><span class="sxs-lookup"><span data-stu-id="edcdf-119">For example, if you are binding to a column value in a dataset's table, expand the name of the dataset, and then expand the table name to display column names.</span></span>  
  
7.  <span data-ttu-id="edcdf-120">单击要绑定到的元素的名称。</span><span class="sxs-lookup"><span data-stu-id="edcdf-120">Click the name of an element to bind to.</span></span>  
  
8.  <span data-ttu-id="edcdf-121">如果你正在处理**格式设置和高级绑定**对话框中，单击**确定**以返回到**属性**窗口。</span><span class="sxs-lookup"><span data-stu-id="edcdf-121">If you were working in the **Formatting and Advanced Binding** dialog box, click **OK** to return to the **Properties** window.</span></span>  
  
9. <span data-ttu-id="edcdf-122">如果你想要将绑定控件的其他属性，请重复步骤 3 至 7。</span><span class="sxs-lookup"><span data-stu-id="edcdf-122">If you want to bind additional properties of the control, repeat steps 3 through 7.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="edcdf-123">因为简单绑定控件显示仅包含单个数据元素，它是非常典型导航逻辑包括在 Windows 窗体控件与简单绑定控件。</span><span class="sxs-lookup"><span data-stu-id="edcdf-123">Because simple-bound controls show only a single data element, it is very typical to include navigation logic in a Windows Form with simple-bound controls.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="edcdf-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="edcdf-124">See Also</span></span>  
 <xref:System.Windows.Forms.Binding>  
 [<span data-ttu-id="edcdf-125">Windows 窗体数据绑定</span><span class="sxs-lookup"><span data-stu-id="edcdf-125">Windows Forms Data Binding</span></span>](../../../docs/framework/winforms/windows-forms-data-binding.md)  
 [<span data-ttu-id="edcdf-126">数据绑定和 Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="edcdf-126">Data Binding and Windows Forms</span></span>](../../../docs/framework/winforms/data-binding-and-windows-forms.md)
